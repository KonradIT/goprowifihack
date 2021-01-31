## GoPro Bluetooth API - what we know

The findings below are based on using the PacketLogger from Xcode developer tools inspecting the activity of the original GoPro app and combining it with the other information provided within this repository.
Starting with the GoPro HERO8, the app allows to control the camera just using Bluetooth and without the need to switch on the WiFi. 

The investigations below where made using a GoPro HERO8 Black, but I used the found services and characteristics successfull on
* HERO4 Silver
* HERO5 Session
* HERO7 Black
* HERO8 Black

### Services and characteristics

The initial step was of course to look for devices using the two service UUIDs mentioned on other documents of this repositoy
* 0000fea5-0000-1000-8000-00805f9b34fb
* 0000fea6-0000-1000-8000-00805f9b34fb

Once a device is detected we can just ask it to discover the services and the characteristcs.
Just trying to read from each characteristic provides some quite interesting information

UUID | Content
-----|--------
B5F90002-AA8D-11E3-9046-0002A5D5C51B | WiFi SSID
B5F90003-AA8D-11E3-9046-0002A5D5C51B | WiFi password
2A19 | Battery level in %
2A25 | Serial number
2A26 | Firmware version

But this information is kind of static. The battery level for example will not change. And this is anyway not how the original GoPro app is doing it.

Instead the original app is using a behavior like
* activate notifications
* send a request
* wait for the notification of the request and read it
* deactivate the notifications

For this is is quite usefull to know the handles and UUIDs of the different related characteristics. Especially as other documents use one or the other in der descriptions. At the beginning this drived me crazy as I had no idea where this 2f in the gatttool examples was coming from. Luckily I figured out that this is the handle for the send command characteristic where I need to used the UUID in my Swift code for example.

In an article I found the following command for the gatttool the gives you a list of handles and the related UUIDs
```shell
char-desc 2F 3C
```
like
```
handle: 0x002f, uuid: b5f90072-aa8d-11e3-9046-0002a5d5c51b
handle: 0x0030, uuid: 00002803-0000-1000-8000-00805f9b34fb
handle: 0x0031, uuid: b5f90073-aa8d-11e3-9046-0002a5d5c51b
handle: 0x0032, uuid: 00002902-0000-1000-8000-00805f9b34fb
handle: 0x0033, uuid: 00002803-0000-1000-8000-00805f9b34fb
handle: 0x0034, uuid: b5f90074-aa8d-11e3-9046-0002a5d5c51b
handle: 0x0035, uuid: 00002803-0000-1000-8000-00805f9b34fb
handle: 0x0036, uuid: b5f90075-aa8d-11e3-9046-0002a5d5c51b
handle: 0x0037, uuid: 00002902-0000-1000-8000-00805f9b34fb
handle: 0x0038, uuid: 00002803-0000-1000-8000-00805f9b34fb
handle: 0x0039, uuid: b5f90076-aa8d-11e3-9046-0002a5d5c51b
handle: 0x003a, uuid: 00002803-0000-1000-8000-00805f9b34fb
handle: 0x003b, uuid: b5f90077-aa8d-11e3-9046-0002a5d5c51b
handle: 0x003c, uuid: 00002902-0000-1000-8000-00805f9b34fb
```
When checking this list and again combining it with information from [GOPRO HERO5 INTERFACES](https://gethypoxic.com/blogs/technical/gopro-hero5-interfaces) page and the investigations from the PacketLogger, we can figure out some dependencies
Handle | UUID | Comments
-------|------|---------
0x002f (47) | b5f90072-aa8d-11e3-9046-0002a5d5c51b | Command request
0x0031 (49) | b5f90073-aa8d-11e3-9046-0002a5d5c51b | Command response
0x0032 (50) | 00002902-0000-1000-8000-00805f9b34fb | Command notifications
0x0034 (52) | b5f90074-aa8d-11e3-9046-0002a5d5c51b | Setting request
0x0036 (54) | b5f90075-aa8d-11e3-9046-0002a5d5c51b | Setting response
0x0037 (55) | 00002902-0000-1000-8000-00805f9b34fb | Setting notification
0x0039 (57) | b5f90076-aa8d-11e3-9046-0002a5d5c51b | Information request
0x003b (59) | b5f90077-aa8d-11e3-9046-0002a5d5c51b | Information response
0x003c (60) | 00002902-0000-1000-8000-00805f9b34fb | Information notification


### Activate and deactivate notifications
As mentioned above, the original GoPro app used to enable and disable the notification for each request.
In the PacketLogger I can see something like this when triggering a recording
```
ATT Send         Write Request - Handle:0x0032 - Value: 0100  
ATT Send         Write Request - Handle:0x002F - Value: 0301 0101  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 0201 00  
ATT Send         Write Request - Handle:0x0032 - Value: 0000  
```
The write request for handle 0x0032 do trigger the notifications. In the first place I thought I need to create a write request for this handle and the content 0100 or 0000 like I used to do for the 0x002F handle, bit this was wrong.
The characteristic of the 0x0032 handle was not discovered on the device.

In the end I saw, that the commands that are sent on handle 0x002F (Command request), causing a notification on handle 0x0031 (Command response). So I gave it a try and used the command to activate notifications for this handle and enabled the notification for 0x0031. And this produced the write log entries as seen above.

In my Swift code this looks like
```swift
if (characteristic.uuid.uuidString == "B5F90073-AA8D-11E3-9046-0002A5D5C51B") {
  peripheral.setNotifyValue(true, for: characteristic)
}
```
This behavior is used for commands and settings. The camera information notifications however are just switched on after connecting and then they remain on. But only activating the notifications like above isn't enough.
With some testing I found out that that you need to send the following request with the ID 0x53 to the 0x0039 to the (Infrmation request) characteristic to trigger information updates to be sent. Once this request is sent, you will get a notification whenever some of the status elements of the camera is chaning. Like the battery level. During recording you will get an update every second with the recording time and most of the time even the free space. Also recording status is included. 


### Notification response
The basic strcure of a notification response is quite simple
* Response length
* Request ID 
* Response status/error
* Response content

but except of the request ID, all of them have additional aspects to consider.

#### Response length
This is the overall length of the response not including the length itself.
For a simple response that fits in one package, it can be taken as is.
For example the following response 
```
08 93 00 08 01 01 0A 01 01  
```
So the length is 0x08 (8) bytes means there are 8 more bytes following as content of the response.

The length becomes more complex when the response does not fit in one package.
This is indicated by a 0x20 (32) on the first byte. In this case the length is actually the second byte.
e.g. 
```
20 79 F5 F3 0A 3D …
```
The length is 0x79 (121) in the second byte. So 121 more byte of response data will follow.

And if the content of the response is even longer than 255 bytes, then you will see like 0x21 as the first bye.
In this case the 1 of 21 as part of the length.
e.g. 
```
21 5D 13 00 01 01 …
```
Taking 21 5D the length is 01 5D (349). So far i didn't see any response bigger than 0x01FF (511). But in general this can be applied even up to 0x0FFF (4095).

If we have one of the multi package responses, than the follow up packages have a kind of an indicator on the first byte ranging from 0x80 to 0x8F. If this isn't enough for the response, then it starts all over again with 0x80.
```
215D 1300 0101 0102 0104 0301 0004 01FF…  
8001 0009 0100 0A01 000B 0100 0D04 0000…  
8100 0000 0011 0101 1301 0014 0100 1504…  
8216 0100 1701 0018 0100 1A01 001B 0100…  
8300 1E0A 4865 726F 3842 6C61 636B 1F01…  
8421 0100 2204 0000 3E90 2304 0000 4468…  
8500 0025 0400 0000 0426 0400 0000 0027…  
8604 2812 2531 3525 3031 2530 3325 3038…  
8730 3429 0100 2A01 002D 0100 3104 0000…  
8800 0000 0006 D7B7 0037 0101 3801 0039…  
894B 3A01 003B 0400 0000 003C 0400 0001…  
8A3E 0400 0000 003F 0100 4001 4841 0100…  
8B01 6444 0100 4501 0046 015F 4701 0C48…  
8C18 4A01 004B 0100 4C01 014D 0101 4E01…  
8D51 0101 5201 0153 0101 5501 0056 0100…  
8E01 0C5A 0100 5B01 005C 0100 5D04 0000…  
8F00 0100 005F 0400 0200 0060 0400 0003…  
8000 0000 6204 0600 0000 6304 0000 16CD…  
8100 0065 0100 6601 00  
```
From the follow up packages you only need to cut off the initial indicator byte and append the rest of the package to the overall response content.

#### Response status
From what I saw in the different responses, I used to consider the status to indicate an error because of the following behavior
```
ATT Send         Write Request - Handle:0x002F - Value: 013C  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 023C 01  
```
and
```
ATT Send         Write Request - Handle:0x002F - Value: 013C  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 2055 3C00 0400 0000 320B 4845 524F 3820…  
```
As you can see the response content is missing when the status byte is 0x01 (error). So the service seems to be not ready to respond. But there is response content if the status byte is 0x00 (no error).

#### Response content
I experienced two different types of response content
- key value list
- string list

So far I didn't find an indicator on the response itself to identify the type of the response content. You need to know what you are dealing with when processing the content.

##### Key value list
Each entry in this list is consiting of three item actually
- parameter id
- parameter length
- parameter content

The parameter ID is matching with the status items mentioned for example in [Camera Status for HERO4](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/CameraStatus.md).
I also compiled a list of known parameters below.
e.g
```
0D 04 00 00 00 CE 36 08 00 00 06 C4 21 FD
```
Value | Comments
-------|---------
0D | ID 13 = Current recording duration
04 | Length = 4 bytes
000000CE | 206 seconds
36 | ID 54 = Remaning free space 
08 | Length = 4 bytes
000006C421FD | 113517053 kilobytes = 108GB

##### string list
For the string list it is just the length and the conten. e.g.
```
0B 48 45 52 4F 38 20 42 6C 61 63 6B 04 30 78 30 35 0F 48 44 38 2E 30 0F 48 44 38 2E 30 31 2E 30 32 2E 35 30 2E 30 30
```
Value | Comments
-------|---------
0B | Length = 11 bytes
4845524F3820426C61636B04307830350F4844382E30 | HERO8 Black
0F | Length = 15 bytes
4844382E30312E30322E35302E3030 | HD8.01.02.50.00

There is not ID for the different items in the string list. So you need to know what is available on which position of the list.


### Requests
A lot of the requests don't have a response in the notification. In this case the only relevant part of the response is the status/error byte.
As far as I can see the request IDs are the same as for the WiFi API.

The following requests have been discovered.

#### Command requests

Length | Request ID | Parameter | Desctiption | Notification 
-------|------------|-----------|-------------|-------------
03 (3) | 01 (1) | Length: 1 byte<ul><li>0: stop recording</li><li>1: start recording</li></ul> | Trigger recording | None
03 (3) | 02 (2) | Length: 1 byte<ul><li>0: Video</li><li>1: Photo</li><li>Multi shot</li></ul> | Switch mode | None
01 (1) | 04 (4) | None | Force power off | None
01 (1) | 05 (5) | None | Power off / sleep | None
09 (9) | 0D (13) | Length: 7 byte<ul><li>year e.g. 2021 -> 07E5</li><li>month e.g. 1 -> 01</li><li>day e.g. 4 -> 04</li><li>hour e.g. 10 -> 0A</li><li>minute e.g. 4 -> 04</li><li>second e.g. 19 -> 13</li></ul> | Set date and time | None
01 (1) | 18 (24) | None | Set highlight tag | None
03 (3) | 16 (22) | Length: 1 byte<ul><li>0: stop locating</li><li>1: start locating</li></ul> | Trigger locating beep | None
01 (1) | 3C (60) | None | Get camera info | String list <ul><li>?</li><li>Camera name e.g. HERO5 Session</li><li>? e.g. 0x05</li><li>Firmware version e.g. HD5.03.02.51.00</li><li>Serial number</li><li>WiFi SSID</li><li>Mac address</li><li>?</li></ul>




#### Information requests

Length | Request ID | Parameter | Desctiption | Notification 
-------|------------|-----------|-------------|-------------
01 (1) | 12 (18) | None | Get camera settings | Parameter list. Check [Camera Status for HERO4](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/CameraStatus.md) for example.
01 (1) | 13 (19) | None | Get camera status | Parameter list. See status codes below
01 (1) | 52 (82) | None | Get camera settings | Parameter list. See settings codes below.<br>I don't know what's the difference to 0x12!
01 (1) | 53 (83) | None | Activate information updates | None


#### Settings requests

Length | Request ID | Parameter | Desctiption | Notification 
-------|------------|-----------|-------------|-------------
03 (3) | 5B (91) | Length: 1 byte<ul><li>00: all off</li><li>1: front</li><li>2: all</li></ul> | LED lights | None
03 (3) | 57 (87) | Length: 1 byte<ul><li>00 (0): off</li><li>28 (40): low</li><li>46 (70): medium</li><li>64 (100): high</li></ul> | Beep | None
03 (3) | 36 (54) | Length: 1 byte<ul><li>0: off</li><li>1: on</li></ul> | Quick capture | None
03 (3) | 98 (152) | Length: 1 byte<ul><li>0: video</li><li>1: photo</li><li>2: multi shot</li><li>7: last used</li></ul> | Default mode | None
03 (3) | 3B (59) | Length: 1 byte<ul><li>0: never</li><li>4: 5 minutes</li><li>6: 15 minutes</li><li>7: 30 minutes</li></ul> | Auto sleep | None
03 (3) | 33 (51) | Length: 1 byte<ul><li>0: never</li><li>1: 1 minute</li><li>2: 2 minutes</li><li>3: 3 minutes</li></ul> | Auto sleep | None
03 (3) | 67 (103) | Length: 1 byte<ul><li>3: off</li><li>6: on</li></ul> | Auto lock | None
03 (3) | 58 (88) | Length: 1 byte<br>value in percent 00-64 (0-100) | LCD brightness | None
03 (3) | 70 (112) | Length: 1 byte<ul><li>00 (0): all</li><li>05 (5): landscape</li><li>FF (255): locked</li></ul> | Orientation | None
03 (3) | 53 (83) | Length: 1 byte<ul><li>0: off</li><li>1: on</li></ul> | GPS | None
03 (3) | 53 (134) | Length: 1 byte<ul><li>0: 60Hz (NTSC)</li><li>1: 50Hz (PAL)</li></ul> | Anti flicker | None
03 (3) | 6A (106) | Length: 1 byte<ul><li>0: compatible</li><li>1: high efficiency</li></ul> | Video compression | None

### Status codes
ID | Description | Content
---|-------------|--------
01 (1) | Battery | Length: 1 byte<ul><li>0: no battery</li><li>2: battery available</li></ul> 
02 (2) | Battery status | Length: 1 byte<ul><li>0: empty</li><li>1: low</li><li>2: halfway</li><li>3: full</li><li>4: charging</li></ul> 
08 (8) | Recording status | Length: 1 byte<ul><li>0: not recording</li><li>1: recording</li></ul> 
0D (13) | Current recording time | Length: 4 byte<br>time in seconds 
25 (37) | Number of videos | Length: 4 byte
2B (43) | Current mode | Length: 1 byte<ul><li>0: video</li><li>1: photo</li><li>2: multishot</li></ul> 
2C (44) | Free space | Length: 8 byte<br>size in kilobytes
46 (70) | Battery level | Length: 1 byte<br>value in %

### Full example
This is kind of a full example of requests from the logger.

Initialize camera connection
```
ATT Send         Write Request - Handle:0x0032 - Value: 0100  
ATT Send         Write Request - Handle:0x002F - Value: 013C  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 2055 3C00 0400 0000 320B 4845 524F 3820…  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 806B 0430 7830 350F 4844 382E 3031 2E30…  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 812E 3030 0E43 3333 3331 3335 3032 3234…  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 8248 6572 6F38 426C 6163 6B0C 6436 3332…  
ATT Receive      Handle Value Notification - Handle:0x0031 - Value: 8335 6537 3301 0001 0101 00  
ATT Send         Write Request - Handle:0x0032 - Value: 0000  

ATT Send         Write Request - Handle:0x003C - Value: 0100  
ATT Send         Write Request - Handle:0x0039 - Value: 0112  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 2101 1200 0201 0903 0109 0501 0006 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8001 0113 0100 1801 001E 0400 0000 001F…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8100 0000 0A25 0100 2901 092A 0105 2B01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 822D 0105 2F01 0430 0103 3301 0136 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8304 0000 0000 3D04 0000 0000 3E04 0000…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8404 4104 0000 0000 4204 0000 0000 4304…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 854B 0100 4C01 004F 0100 5301 0154 0102…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8601 0057 0100 5801 505B 0102 5F01 0160…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8708 6701 0368 0100 6901 006A 0100 6B01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8870 01FF 7201 0173 0102 7401 0175 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8901 047A 0100 7B01 007C 0100 7D01 007E…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8A0C 8101 0282 0101 8301 0384 010C 8501…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8B87 0102 8901 008B 0103 9001 0C91 0100…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8C01 0095 0102 9801 0099 0100  
ATT Send         Write Request - Handle:0x003C - Value: 0000  

ATT Send         Write Request - Handle:0x003C - Value: 0100  
ATT Send         Write Request - Handle:0x0039 - Value: 0113  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 215D 1300 0101 0102 0104 0301 0004 01FF…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8001 0009 0100 0A01 000B 0100 0D04 0000…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8100 0000 0011 0101 1301 0014 0100 1504…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8216 0100 1701 0018 0100 1A01 001B 0100…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8300 1E0A 4865 726F 3842 6C61 636B 1F01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8421 0100 2204 0000 3E90 2304 0000 4468…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8500 0025 0400 0000 0426 0400 0000 0027…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8604 2812 2531 3525 3031 2530 3325 3038…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8730 3429 0100 2A01 002D 0100 3104 0000…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8800 0000 0006 D7B7 0037 0101 3801 0039…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 894B 3A01 003B 0400 0000 003C 0400 0001…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8A3E 0400 0000 003F 0100 4001 4841 0100…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8B01 6444 0100 4501 0046 015F 4701 0C48…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8C18 4A01 004B 0100 4C01 014D 0101 4E01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8D51 0101 5201 0153 0101 5501 0056 0100…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8E01 0C5A 0100 5B01 005C 0100 5D04 0000…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8F00 0100 005F 0400 0200 0060 0400 0003…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8000 0000 6204 0600 0000 6304 0000 16CD…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8100 0065 0100 6601 00  
ATT Send         Write Request - Handle:0x003C - Value: 0000  

ATT Send         Write Request - Handle:0x003C - Value: 0100  
ATT Send         Write Request - Handle:0x0039 - Value: 0153  
ATT Send         Write Request - Handle:0x0039 - Value: 0152  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 2101 5200 0201 0903 0109 0501 0006 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8001 0113 0100 1801 001E 0400 0000 001F…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8100 0000 0A25 0100 2901 092A 0105 2B01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 822D 0105 2F01 0430 0103 3301 0136 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8304 0000 0000 3D04 0000 0000 3E04 0000…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8404 4104 0000 0000 4204 0000 0000 4304…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 854B 0100 4C01 004F 0100 5301 0154 0102…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8601 0057 0100 5801 505B 0102 5F01 0160…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8708 6701 0368 0100 6901 006A 0100 6B01…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8870 01FF 7201 0173 0102 7401 0175 0101…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8901 047A 0100 7B01 007C 0100 7D01 007E…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8A0C 8101 0282 0101 8301 0384 010C 8501…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8B87 0102 8901 008B 0103 9001 0C91 0100…  
ATT Receive      Handle Value Notification - Handle:0x003B - Value: 8C01 0095 0102 9801 0099 0100  
```

Start/stop recording
```
ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x0032 - Value: 0100  
ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x002F - Value: 0301 0101  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x0031 - Value: 0201 00  
ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x0032 - Value: 0000  

ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 2015 9300 0801 010A 0101 3608 0000 0000…  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 803D 0100  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 0893 000D 0400 0000 01  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 1293 000D 0400 0000 0236 0800 0000 0006…  

ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x0032 - Value: 0100  
ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x002F - Value: 0301 0100  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x0031 - Value: 0201 00  
ATT Send         0x005B  00:00:00:00:00:00  Write Request - Handle:0x0032 - Value: 0000  

ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 2024 9300 2304 0000 4224 2504 0000 000A…  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 8000 0A36 0800 0000 0006 9DB2 0063 0400…  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 8000 0A36 0800 0000 0006 9DB2 0063 0400…  
ATT Receive      0x005B  00:00:00:00:00:00  Handle Value Notification - Handle:0x003B - Value: 803C 7E3D 0102 4001 3F  
```
