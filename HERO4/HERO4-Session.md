###HERO4 Session Specific Notes and Commands

The GoPro HERO4 Session is a simplified version of the popular HERO camera. Because of this the camera only responds to GET requests when is in APP mode, to turn the camera to APP mode send a magic packet (WoL) with these parameters: MAC ADDRESS OF THE CAMERA, 10.5.5.9 as IP ADDRESS, Subnet Mask 255.255.255.0, Port 9. For the Hero4 Session, this magic packet has to be sent when your project wants to operate with the camera.

And to check that you have access to the camera, GET the status 31 of the camera and make sure its not 0 (more info on CameraStatus.md)

###Protune on HERO4 Session

As per 2.00 firmware version, the GoPro HERO4 Session allows Protune controls for Video mode, but some parameters vary from HERO4 Black/Silver cameras. 

#####Controls:

* off: http://10.5.5.9/gp/gpControl/setting/10/0
* on: http://10.5.5.9/gp/gpControl/setting/10/1

#####White Balance:

* Auto: http://10.5.5.9/gp/gpControl/setting/11/0
* 3000k: http://10.5.5.9/gp/gpControl/setting/11/1
* 5500k: http://10.5.5.9/gp/gpControl/setting/11/2
* 6500k: http://10.5.5.9/gp/gpControl/setting/11/3
* Native: http://10.5.5.9/gp/gpControl/setting/11/4

#####Color:

* GOPRO: http://10.5.5.9/gp/gpControl/setting/12/0
* Flat: http://10.5.5.9/gp/gpControl/setting/12/1

#####ISO:

* 1600: http://10.5.5.9/gp/gpControl/setting/13/1
* 400: http://10.5.5.9/gp/gpControl/setting/13/2

#####Sharpness:

* ON: http://10.5.5.9/gp/gpControl/setting/14/3
* OFF: http://10.5.5.9/gp/gpControl/setting/14/4

#####EV:

Value | URL
-----|-------
+2   |  http://10.5.5.9/gp/gpControl/setting/15/0
+1.5 |  http://10.5.5.9/gp/gpControl/setting/15/1
+1   |  http://10.5.5.9/gp/gpControl/setting/15/2
+0.5 |  http://10.5.5.9/gp/gpControl/setting/15/3
0    |  http://10.5.5.9/gp/gpControl/setting/15/4
-0.5 |  http://10.5.5.9/gp/gpControl/setting/15/5
-1   |  http://10.5.5.9/gp/gpControl/setting/15/6
-1.5 |  http://10.5.5.9/gp/gpControl/setting/15/7
-2   |  http://10.5.5.9/gp/gpControl/setting/15/8

##Streaming

The GoPro HERO4 Session on Firmware 2.00 works a bit differently when it 
comes to streaming. You still use the same methods explained in [the 
Livestreaming doc](Livestreaming.md) but you need to HTTP GET the status 
URL http://10.5.5.9/gp/gpControl/status until the status:31 (number of clients connected) is set to a value above 0 (>=1). 
Then the feed will be live in UDP port 8554. Refer to [this python 
script](http://github.com/KonradIT/GoProStream) on a real world example.
