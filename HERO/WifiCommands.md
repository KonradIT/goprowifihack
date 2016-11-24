###Wifi Commands for HERO4

Cameras covered: GoPro HERO+, HERO+ LCD

#####Default Boot Mode:
* Video: http://10.5.5.9/gp/gpControl/setting/53/0
* Photo: http://10.5.5.9/gp/gpControl/setting/53/1
* MultiShot: http://10.5.5.9/gp/gpControl/setting/53/2

#####Primary modes:
* Video: http://10.5.5.9/gp/gpControl/command/mode?p=0
* Photo: http://10.5.5.9/gp/gpControl/command/mode?p=1
* MultiShot: http://10.5.5.9/gp/gpControl/command/mode?p=2

#####Secondary modes:

* Video (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=0
* Looping (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=3
* Single (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=0
* Burst (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=0
* Timelapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=1


#####Power:

* Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep
* Power On: To power ON use WoL with these parameters: MAC ADDRESS OF THE CAMERA, 10.5.5.9 as IP ADDRESS, Subnet Mask 255.255.255.0, Port 9.

####Code Pairing:

GoPro HERO+ cameras need a code authentication in order to connect to a
device for the first time, this is done in the GoPro app when you firt
connect your GoPro, a 4 digit PIN is displayed on the camera and that
PIN needs to be entered in the GoPro app. [Video explaining GoPro pairing process with a HERO4](https://www.youtube.com/watch?v=4BH59qEeQUg)

First make sure to connect go GOPRO-BP-(numbers) password: "goprohero"
and call this URL:

https://10.5.5.9/gpPair?c=start&pin=XXXX&mode=0

XXXX is the 4 digit PIN on the GoPro front screen.

And to finish pairing:

https://10.5.5.9/gpPair?c=finish&pin=XXXX&mode=0

####Set GoPro WiFi name/password:

* GoPro Name: http://10.5.5.9gp/gpControl/command/wireless/ap/ssid?ssid=GOPRONAME
* GoPro Name and Password: http://10.5.5.9gp/gpControl/command/wireless/ap/ssid?ssid=GOPRONAME&pw=GOPROPASS

GOPRONAME = GoPro new WiFi name

GOPROPASS = GoPro new WiFi password

####Video:

#####Resolutions:
* 1080p: http://10.5.5.9/gp/gpControl/setting/2/9
* 720p SuperView: http://10.5.5.9/gp/gpControl/setting/2/11
* 720p: http://10.5.5.9/gp/gpControl/setting/2/12

#####Frame Rate (HERO4 Black/Session):
* 60fps:	http://10.5.5.9/gp/gpControl/setting/3/5
* 50fps:	http://10.5.5.9/gp/gpControl/setting/3/6
* 30fps:	http://10.5.5.9/gp/gpControl/setting/3/8
* 25fps:	http://10.5.5.9/gp/gpControl/setting/3/9

#####FOV

* Wide: http://10.5.5.9/gp/gpControl/setting/4/0

#####Low Light:
* ON: http://10.5.5.9/gp/gpControl/setting/8/1
* OFF: http://10.5.5.9/gp/gpControl/setting/8/0

#####Video Looping Duration:

* Max: http://10.5.5.9/gp/gpControl/setting/6/0
* 5Min: http://10.5.5.9/gp/gpControl/setting/6/1
* 20Min: http://10.5.5.9/gp/gpControl/setting/6/2
* 60Min: http://10.5.5.9/gp/gpControl/setting/6/3
* 120Min: http://10.5.5.9/gp/gpControl/setting/6/4

#####Spot Meter:

* off: http://10.5.5.9/gp/gpControl/setting/9/0
* on: http://10.5.5.9/gp/gpControl/setting/9/1

---

####Photo:

#####Photo resolution for Photo Modes (incl. SubModes):

* 8MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0


#####Spot Meter:

* off: http://10.5.5.9/gp/gpControl/setting/20/0
* on: http://10.5.5.9/gp/gpControl/setting/20/1

---

####MultiShot:


#####Photo resolution for MultiShot Modes (incl. SubModes):

* 8MP Wide: http://10.5.5.9/gp/gpControl/setting/28/0

#####Timelapse Interval (TIMELAPSE MODE on MultiShot):

* 0.5: http://10.5.5.9/gp/gpControl/setting/30/0
* 1: http://10.5.5.9/gp/gpControl/setting/30/1
* 2: http://10.5.5.9/gp/gpControl/setting/30/2
* 5: http://10.5.5.9/gp/gpControl/setting/30/5
* 10: http://10.5.5.9/gp/gpControl/setting/30/10
* 30: http://10.5.5.9/gp/gpControl/setting/30/30
* 60: http://10.5.5.9/gp/gpControl/setting/30/60

#####Spot Meter:

* off: http://10.5.5.9/gp/gpControl/setting/33/0
* on: http://10.5.5.9/gp/gpControl/setting/33/1

####Burst Rate:

* 10/2: http://10.5.5.9/gp/gpControl/setting/29/3

---

#####Shutter
* Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
* Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

#####Orientation:

* Up: http://10.5.5.9/gp/gpControl/setting/52/1
* Down: http://10.5.5.9/gp/gpControl/setting/52/2
* Gyro based: http://10.5.5.9/gp/gpControl/setting/52/0

#####Quick Capture:
* On: http://10.5.5.9/gp/gpControl/setting/54/1
* Off: http://10.5.5.9/gp/gpControl/setting/54/0

#####LED Blink:
* 2: http://10.5.5.9/gp/gpControl/setting/55/1
* 4: http://10.5.5.9/gp/gpControl/setting/55/2
* Off: http://10.5.5.9/gp/gpControl/setting/55/0

#####Beeps:
* Off: http://10.5.5.9/gp/gpControl/setting/56/2
* 0.7: http://10.5.5.9/gp/gpControl/setting/56/1
* Full: http://10.5.5.9/gp/gpControl/setting/56/0

#####Video Format:
* NTSC: http://10.5.5.9/gp/gpControl/setting/57/0
* PAL: http://10.5.5.9/gp/gpControl/setting/57/1

#####LCD Display:
* On: http://10.5.5.9/gp/gpControl/setting/72/1
* Off: http://10.5.5.9/gp/gpControl/setting/72/0

#####On Screen Display:
* On: http://10.5.5.9/gp/gpControl/setting/58/1
* Off: http://10.5.5.9/gp/gpControl/setting/58/0

#####LCD Brightness:
* High: http://10.5.5.9/gp/gpControl/setting/49/0
* Medium: http://10.5.5.9/gp/gpControl/setting/49/1
* Low: http://10.5.5.9/gp/gpControl/setting/49/2

#####LCD Lock:
 * On: http://10.5.5.9/gp/gpControl/setting/50/1
 * Off: http://10.5.5.9/gp/gpControl/setting/50/0

#####LCD Timeout sleep:

* LCD Never sleep: http://10.5.5.9/gp/gpControl/setting/51/0
* LCD 1min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/1
* LCD 2min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/2
* LCD 3min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/3

#####Auto Off:
* Never: http://10.5.5.9/gp/gpControl/setting/59/0
* 1m: http://10.5.5.9/gp/gpControl/setting/59/1
* 2m: http://10.5.5.9/gp/gpControl/setting/59/2
* 3m: http://10.5.5.9/gp/gpControl/setting/59/3
* 5m: http://10.5.5.9/gp/gpControl/setting/59/4

####Streaming tweaks:

#####Stream BitRate:

* 250 Kbps: http://10.5.5.9/gp/gpControl/setting/62/250000
* 400 Kbps: http://10.5.5.9/gp/gpControl/setting/62/400000
* 600 Kbps: http://10.5.5.9/gp/gpControl/setting/62/600000
* 700 Kbps: http://10.5.5.9/gp/gpControl/setting/62/700000
* 800 Kbps: http://10.5.5.9/gp/gpControl/setting/62/800000
* 1 Mbps: http://10.5.5.9/gp/gpControl/setting/62/1000000
* 1.2 Mbps: http://10.5.5.9/gp/gpControl/setting/59/1200000
* 1.6 Mbps: http://10.5.5.9/gp/gpControl/setting/59/1600000
* 2 Mbps: http://10.5.5.9/gp/gpControl/setting/59/2000000
* 2.4 Mbps: http://10.5.5.9/gp/gpControl/setting/59/2400000

#####Stream Window Size:

* Default: http://10.5.5.9/gp/gpControl/setting/64/0
* 240: http://10.5.5.9/gp/gpControl/setting/64/1
* 240, 3:4: http://10.5.5.9/gp/gpControl/setting/64/2
* 240 1:2: http://10.5.5.9/gp/gpControl/setting/64/3
* 480: http://10.5.5.9/gp/gpControl/setting/64/4
* 480 3:4: http://10.5.5.9/gp/gpControl/setting/64/5
* 480 1:2: http://10.5.5.9/gp/gpControl/setting/64/6

#####Tag moment:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment

#####Pair with used RC:

http://10.5.5.9/setting/63/2

#####Locate

* On: http://10.5.5.9/gp/gpControl/command/system/locate?p=1
* Off: http://10.5.5.9/gp/gpControl/command/system/locate?p=0

#####Delete file:

http://10.5.5.9/gp/gpControl/command/storage/delete?p=file (eg. /100GOPRO/G0010124.JPG)

#####Delete Last media taken:

http://10.5.5.9/gp/gpControl/command/storage/delete/last

#####Reformat SD Card (CAUTION!):

http://10.5.5.9/gp/gpControl/command/storage/delete/all
