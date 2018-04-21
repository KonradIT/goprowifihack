### Wifi Commands for Fusion

##### Default Boot Mode:
* Video: http://10.5.5.9/gp/gpControl/setting/53/0
* Photo: http://10.5.5.9/gp/gpControl/setting/53/1
* MultiShot: http://10.5.5.9/gp/gpControl/setting/53/2

##### Primary modes:
* Video: http://10.5.5.9/gp/gpControl/command/mode?p=0
* Photo: http://10.5.5.9/gp/gpControl/command/mode?p=1
* MultiShot: http://10.5.5.9/gp/gpControl/command/mode?p=2

##### Secondary modes:

* Video (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=0
* TimeLapse Video (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=1
* Single (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=0
* Night (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=2
* Burst (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=0
* Timelapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=1
* NightLapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=2


##### Power:

* Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep
* Power On: To power ON use WoL with these parameters: MAC ADDRESS OF THE CAMERA, 10.5.5.9 as IP ADDRESS, Subnet Mask 255.255.255.0, Port 9. For the Hero4 Session, this magic packet has to be sent when your project wants to operate with the camera.

#### Video:

##### Resolutions:
* 5.2K: http://10.5.5.9/gp/gpControl/setting/2/14
* 3K: http://10.5.5.9/gp/gpControl/setting/2/15

##### Frame Rate:
* 60fps:	http://10.5.5.9/gp/gpControl/setting/3/5
* 50fps:	http://10.5.5.9/gp/gpControl/setting/3/6
* 30fps:	http://10.5.5.9/gp/gpControl/setting/3/8
* 25fps:	http://10.5.5.9/gp/gpControl/setting/3/9

##### Video Timelapse Interval:

* 0.5: http://10.5.5.9/gp/gpControl/setting/5/0
* 1: http://10.5.5.9/gp/gpControl/setting/5/1
* 2: http://10.5.5.9/gp/gpControl/setting/5/2
* 5: http://10.5.5.9/gp/gpControl/setting/5/3
* 10: http://10.5.5.9/gp/gpControl/setting/5/4
* 30: http://10.5.5.9/gp/gpControl/setting/5/5
* 60: http://10.5.5.9/gp/gpControl/setting/5/6

##### ProTune:
* off: http://10.5.5.9/gp/gpControl/setting/10/0
* on: http://10.5.5.9/gp/gpControl/setting/10/1

##### ISO Limit:

* 6400: http://10.5.5.9/gp/gpControl/setting/13/0
* 1600: http://10.5.5.9/gp/gpControl/setting/13/1
* 400: http://10.5.5.9/gp/gpControl/setting/13/2

##### ISO Mode:

* Max: http://10.5.5.9/gp/gpControl/setting/74/0
* Lock: http://10.5.5.9/gp/gpControl/setting/74/1

##### EV Compensation:

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

---

#### Photo:

##### Photo resolution for Photo Modes (incl. SubModes):

* 18MP: http://10.5.5.9/gp/gpControl/setting/17/12

##### Exposure time for NightPhoto:

* Auto: http://10.5.5.9/gp/gpControl/setting/19/0
* 2: http://10.5.5.9/gp/gpControl/setting/19/1
* 5: http://10.5.5.9/gp/gpControl/setting/19/2
* 10: http://10.5.5.9/gp/gpControl/setting/19/3
* 15: http://10.5.5.9/gp/gpControl/setting/19/4
* 20: http://10.5.5.9/gp/gpControl/setting/19/5
* 30: http://10.5.5.9/gp/gpControl/setting/19/6

##### ProTune:

* off: http://10.5.5.9/gp/gpControl/setting/21/0
* on: http://10.5.5.9/gp/gpControl/setting/21/1

##### ISO Limit:

* 800: http://10.5.5.9/gp/gpControl/setting/24/0
* 400: http://10.5.5.9/gp/gpControl/setting/24/1
* 200: http://10.5.5.9/gp/gpControl/setting/24/2
* 100: http://10.5.5.9/gp/gpControl/setting/24/3

##### EV Compensation:

Value | URL
-----|-------
+2   |  http://10.5.5.9/gp/gpControl/setting/26/0
+1.5 |  http://10.5.5.9/gp/gpControl/setting/26/1
+1   |  http://10.5.5.9/gp/gpControl/setting/26/2
+0.5 |  http://10.5.5.9/gp/gpControl/setting/26/3
0    |  http://10.5.5.9/gp/gpControl/setting/26/4
-0.5 |  http://10.5.5.9/gp/gpControl/setting/26/5
-1   |  http://10.5.5.9/gp/gpControl/setting/26/6
-1.5 |  http://10.5.5.9/gp/gpControl/setting/26/7
-2   |  http://10.5.5.9/gp/gpControl/setting/26/8

##### RAW Photo:

* On: http://10.5.5.9/gp/gpControl/setting/82/1
* Off: http://10.5.5.9/gp/gpControl/setting/82/0
---

#### MultiShot:

##### MultiShot resolution:

* 18MP: http://10.5.5.9/gp/gpControl/setting/28/12

##### Exposure time for NightLapse:

* Auto: http://10.5.5.9/gp/gpControl/setting/31/0
* 2: http://10.5.5.9/gp/gpControl/setting/31/1
* 5: http://10.5.5.9/gp/gpControl/setting/31/2
* 10: http://10.5.5.9/gp/gpControl/setting/31/3
* 15: http://10.5.5.9/gp/gpControl/setting/31/4
* 20: http://10.5.5.9/gp/gpControl/setting/31/5
* 30: http://10.5.5.9/gp/gpControl/setting/31/6

##### Interval for NightLapse

* Continuous: http://10.5.5.9/gp/gpControl/setting/32/0
* 4s: http://10.5.5.9/gp/gpControl/setting/32/4
* 5s: http://10.5.5.9/gp/gpControl/setting/32/5
* 10s: http://10.5.5.9/gp/gpControl/setting/32/10
* 15s: http://10.5.5.9/gp/gpControl/setting/32/15
* 20s: http://10.5.5.9/gp/gpControl/setting/32/20
* 30s: http://10.5.5.9/gp/gpControl/setting/32/30
* 1m: http://10.5.5.9/gp/gpControl/setting/32/60
* 2m: http://10.5.5.9/gp/gpControl/setting/32/120
* 5m: http://10.5.5.9/gp/gpControl/setting/32/300
* 30m: http://10.5.5.9/gp/gpControl/setting/32/1800
* 60m: http://10.5.5.9/gp/gpControl/setting/32/3600

##### Timelapse Interval (TIMELAPSE MODE on MultiShot):

* 0.5: http://10.5.5.9/gp/gpControl/setting/30/0
* 1: http://10.5.5.9/gp/gpControl/setting/30/1
* 2: http://10.5.5.9/gp/gpControl/setting/30/2
* 5: http://10.5.5.9/gp/gpControl/setting/30/5
* 10: http://10.5.5.9/gp/gpControl/setting/30/10
* 30: http://10.5.5.9/gp/gpControl/setting/30/30
* 60: http://10.5.5.9/gp/gpControl/setting/30/60

##### Burst Rate:

* 3/1: http://10.5.5.9/gp/gpControl/setting/29/0
* 5/1: http://10.5.5.9/gp/gpControl/setting/29/1
* 10/1: http://10.5.5.9/gp/gpControl/setting/29/2
* 10/2: http://10.5.5.9/gp/gpControl/setting/29/3
* 10/3: http://10.5.5.9/gp/gpControl/setting/29/4
* 30/1: http://10.5.5.9/gp/gpControl/setting/29/5
* 30/2: http://10.5.5.9/gp/gpControl/setting/29/6
* 30/3: http://10.5.5.9/gp/gpControl/setting/29/7
* 30/6: http://10.5.5.9/gp/gpControl/setting/29/8

##### ProTune:

* off: http://10.5.5.9/gp/gpControl/setting/34/0
* on: http://10.5.5.9/gp/gpControl/setting/34/1

##### ISO Limit:

* 800: http://10.5.5.9/gp/gpControl/setting/37/0
* 400: http://10.5.5.9/gp/gpControl/setting/37/1
* 200: http://10.5.5.9/gp/gpControl/setting/37/2
* 100: http://10.5.5.9/gp/gpControl/setting/37/3

##### EV Compensation:

Value | URL
-----|-------
+2   |  http://10.5.5.9/gp/gpControl/setting/39/0
+1.5 |  http://10.5.5.9/gp/gpControl/setting/39/1
+1   |  http://10.5.5.9/gp/gpControl/setting/39/2
+0.5 |  http://10.5.5.9/gp/gpControl/setting/39/3
0    |  http://10.5.5.9/gp/gpControl/setting/39/4
-0.5 |  http://10.5.5.9/gp/gpControl/setting/39/5
-1   |  http://10.5.5.9/gp/gpControl/setting/39/6
-1.5 |  http://10.5.5.9/gp/gpControl/setting/39/7
-2   |  http://10.5.5.9/gp/gpControl/setting/39/8


---

##### Shutter
* Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
* Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

---

##### Quick Capture:
* On: http://10.5.5.9/gp/gpControl/setting/54/1
* Off: http://10.5.5.9/gp/gpControl/setting/54/0

##### GPS Tag:

* On: http://10.5.5.9/gp/gpControl/setting/83/1
* Off: http://10.5.5.9/gp/gpControl/setting/83/0

##### Voice control:

* On: http://10.5.5.9/gp/gpControl/setting/86/1
* Off: http://10.5.5.9/gp/gpControl/setting/86/0

##### LEDs:

* Off: http://10.5.5.9/gp/gpControl/setting/91/0
* On: http://10.5.5.9/gp/gpControl/setting/91/2
* Front off: http://10.5.5.9/gp/gpControl/setting/91/1

##### Beeps:
* Off: http://10.5.5.9/gp/gpControl/setting/56/2
* 0.7: http://10.5.5.9/gp/gpControl/setting/56/1
* Full: http://10.5.5.9/gp/gpControl/setting/56/0

##### Video Format:
* NTSC: http://10.5.5.9/gp/gpControl/setting/57/0
* PAL: http://10.5.5.9/gp/gpControl/setting/57/1

##### Auto Off:
* Never: http://10.5.5.9/gp/gpControl/setting/59/0
* 1m: http://10.5.5.9/gp/gpControl/setting/59/1
* 2m: http://10.5.5.9/gp/gpControl/setting/59/2
* 3m: http://10.5.5.9/gp/gpControl/setting/59/3
* 5m: http://10.5.5.9/gp/gpControl/setting/59/4

#### Streaming tweaks:

##### Stream BitRate :
Supports any number ( like 7000000), but limited by wifi throughput, packet loss and video glitches may appear.
**Correct parameter ID is 62!**

* 250 Kbps: http://10.5.5.9/gp/gpControl/setting/62/250000
* 400 Kbps: http://10.5.5.9/gp/gpControl/setting/62/400000
* 600 Kbps: http://10.5.5.9/gp/gpControl/setting/62/600000
* 700 Kbps: http://10.5.5.9/gp/gpControl/setting/62/700000
* 800 Kbps: http://10.5.5.9/gp/gpControl/setting/62/800000
* 1 Mbps: http://10.5.5.9/gp/gpControl/setting/62/1000000
* 1.2 Mbps: http://10.5.5.9/gp/gpControl/setting/62/1200000
* 1.6 Mbps: http://10.5.5.9/gp/gpControl/setting/62/1600000
* 2 Mbps: http://10.5.5.9/gp/gpControl/setting/62/2000000
* 2.4 Mbps: http://10.5.5.9/gp/gpControl/setting/62/2400000

##### Stream Window Size:
Sizes with 720 height are tested on Hero 5 Black.

* Default: http://10.5.5.9/gp/gpControl/setting/64/0
* 240: http://10.5.5.9/gp/gpControl/setting/64/1
* 240, 3:4: http://10.5.5.9/gp/gpControl/setting/64/2
* 240 1:2: http://10.5.5.9/gp/gpControl/setting/64/3
* 480: http://10.5.5.9/gp/gpControl/setting/64/4
* 480 3:4: http://10.5.5.9/gp/gpControl/setting/64/5
* 480 1:2: http://10.5.5.9/gp/gpControl/setting/64/6
* **720 (1280x720)** : http://10.5.5.9/gp/gpControl/setting/64/7
* **720 3:4 (960x720)** http://10.5.5.9/gp/gpControl/setting/64/8
* **720 1:2 (640x720)** http://10.5.5.9/gp/gpControl/setting/64/9


##### Tag moment:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment

##### Tag moment in video file:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment/playback?p=XXXGOPRO/XXXXXX.MP4&tag=Miliseconds

XXXGOPRO is the folder, XXXXXX.MP4 is the video and Miliseconds are the miliseconds offset from the start of the video.

For example:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment/playback?p=103GOPRO/GOPR1359.MP4&tag=2000

will make a HiLight Tag on 2 seconds of the video GOPR1359.MP4


##### WiFi AP Settings:

* Turn WiFi OFF: http://10.5.5.9/gp/gpControl/setting/63/0
* Switch WiFi to App/Smartphone mode: http://10.5.5.9/gp/gpControl/setting/63/1
* Switch WiFi to GoPro RC: http://10.5.5.9/gp/gpControl/setting/63/2
* Switch WiFi to GoPro Smart Remote RC: http://10.5.5.9/gp/gpControl/setting/63/4

##### Locate

* On: http://10.5.5.9/gp/gpControl/command/system/locate?p=1
* Off: http://10.5.5.9/gp/gpControl/command/system/locate?p=0

##### Delete file:

http://10.5.5.9/gp/gpControl/command/storage/delete?p=file (eg. /100GOPRO/G0010124.JPG)

##### Delete Last media taken:

http://10.5.5.9/gp/gpControl/command/storage/delete/last

##### Reformat SD Card (CAUTION!):

http://10.5.5.9/gp/gpControl/command/storage/delete/all

##### Set date and time

* http://10.5.5.9/gp/gpControl/command/setup/date_time?p=%11%0b%10%11%29%2c

The hex string at the end is the same as for [HERO3](https://github.com/KonradIT/goprowifihack/blob/master/HERO3/WifiCommands.md#basics), so in the example: 11 = (20)17, 0b = 11 (November), 10 = 16, 11 = 17, 29 = 41, 2c = 44.
Example bash code for date string, see https://github.com/ztzhang/GoProWifiCommand/issues/3.
