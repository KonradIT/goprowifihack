#GoPro Wifi Hack

**The unofficial API for GoPro HERO cameras (The WiFi enabled models)**

*Last updated: 03/12/15 by Konrad Iturbe*


##Index

* **[Live streaming](https://github.com/KonradIT/goprowifihack#live-streaming)**
* **[HTTP Commands](https://github.com/KonradIT/goprowifihack#http-commands)**
	* [GoPro HERO2/HERO3/HERO3+](https://github.com/KonradIT/goprowifihack#commands---HERO2-HERO3-HERO3+)
	* [GoPro HERO4](https://github.com/KonradIT/goprowifihack#commands-hero4)
	* [GoPro HERO+/HERO+ LCD](https://github.com/KonradIT/goprowifihack#commandsdiscontinuedcameras)
* **[Media Browsing](https://github.com/KonradIT/goprowifihack#mediabrowsing)**
* **[Getting camera data](https://github.com/KonradIT/goprowifihack#gettingcameradata)**
	* [GoPro HERO2/HERO3/HERO3+](https://github.com/KonradIT/goprowifihack#dataforprehero4)
	* [GoPro HERO4](https://github.com/KonradIT/goprowifihack#datahero4)
* [Acknowledgements, license and general information](https://github.com/KonradIT/goprowifihack#Acknowledgementslicenseandgeneralinformation)

---
##An important note

If you see a URL which contains "PASSWORD" without the quotes, it means it needs the camera password, which you can obain here:  http://10.5.5.9/bacpac/sd

###Live streaming

GoPro HERO cameras have a functionality which streams what the camera sees to the GoPro App, the method the cameras use to stream the video varies from generation.

| Camera | Livestreaming methods |
|--------|-----------------------|
| GoPro HERO4 | First, HTTP Get this URL: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=restart and then you can get a UDP stream by using this URL: udp://10.5.5.9:8554 (you might have a hard time using this in your work...)|
| GoPro HERO2/HERO3/HERO3+/HERO+ | First, HTTP Get this URL:  http://10.5.5.9/bacpac/SH?t=PASSWORD&p=%01 and then you can use this HLS stream: http://10.5.5.9:8080/live/amba.m3u8 (the HSL stream can be used almost anywhere!) |

###HTTP Commands

####Commands - HERO2/HERO3/HERO3+:

The URL scheme:  http://10.5.5.9/param1/PARAM2?t=PASSWORD&p=%OPTION

* param1 = That defines if the action will be activated in the **camera** or **bacpac** (back in the HERO2 days the "bacpac" was the separate WiFi unit). 
* PARAM2 = A two character parameter which defines what the camera needs to do. Eg: SH for Shoot
* OPTION: The arguments for PARAM2

#####Basics:

* bacpac PW - 00 Turn GoPro OFF

* bacpac PW - 01 Turn GoPro ON

* bacpac RS - Reset bacpac

* bacpac SH - 01 Shutter

* bacpac SH - 00 Stop

* camera PV - 02 Preview ON

* camera PV - 00 Preview OFF

* camera TM - Set time, requires a longer string, each field is a byte with a % before it:
	
	* Last 2 digits of the year
	* Month (1 - January, 12 - December)
	* Day of the month (1 - 31)
	* Hour (24-hour format, starts from zero)
	* Minute
	* Second

#####Mode:

* camera CM - 00 Video Mode

* camera CM - 01 Photo Mode

* camera CM - 02 Burst Mode

* camera CM - 03 Timelapse Mode

* camera CM - 04 Timer Mode (hero2)

* camera CM - 05 Play HDMI

#####Orientation

* camera UP - 00 Orientation UP

* camera UP - 01 Orientation DOWN

#####Video resolutions HERO2 and HERO3 silver:

* camera VR - 00 WVGA 60

* camera VR - 01 WVGA 120

* camera VR - 02 720 30

* camera VR - 03 720 60

* camera VR - 04 960 30

* camera VR - 05 960 48

* camera VR - 06 1080 30

#####Video resolutions Black edition:

* camera VV 08 4kCin12

* camera VV 07 2.7kCin24

* camera VV 06 4k 15

* camera VV 05 2.7k 30

* camera VV 04 1440p 40

* camera VV 03 1080 60

* camera VR 05 1080 30

* camera VR 06 960 48

* camera VV 02 960 100

* camera VV 01 720 120

* camera VV 00 WVGA 240

#####Video resolutions HERO3+Black:

* camera VV 06 - 4K 

* camera VV 08 - 4K 17:9 

* camera FS 01 - 4K 15FPS 

* camera FS 00 - 4K 12FPS 

* camera VV 07 - 2K 

* camera VV 05 - 2.7k 

* camera FS 02 - 2.7k 24FPS 

* camera FS 04 - 2.7k 30FPS 

* camera VV 04 - 1440p  

* camera FS 05 - 1440 48FPS 

* camera VV 09 - 1080 SuperView   

* camera VV 03 - 1080  

* camera VV 02 -  960p   

* camera VV 0a - 720 SuperView   

* camera VV 01 - 720p

#####Frame rate:

* camera FS - 00 FPS12

* camera FS - 01 FPS15

* camera FS - 0b FPS12p5

* camera FS - 02 FPS24

* camera FS - 03 FPS25

* camera FS - 04 FPS30

* camera FS - 05 FPS48

* camera FS - 06 FPS50

* camera FS - 07 FPS60

* camera FS - 08 FPS100

* camera FS - 09 FPS120

* camera FS - 0a FPS240

#####Fov:

* camera FV - 00 wide

* camera FV - 01 medium

* camera FV - 02 narrow

#####Photo resolution HERO2 and HERO3 silver:

* camera PR - 00 11mpW

* camera PR - 01 8mpM

* camera PR - 02 5mpW

* camera PR - 03 5mpM

#####Timelapse Interval:

* camera TI - 00 0,5 sec

* camera TI - 01 1sec

* camera TI - 05 5sec

* camera TI - 0a 10sec

* camera TI - 1e 30sec

* camera TI - 3c 60sec

#####Volume:

* camera BS - 00 no sound

* camera BS - 01 70%

* camera BS - 02 100%

#####White Balance HERO3 "ONLY IF Protune ON"

* camera WB - 00 auto

* camera WB - 01 3000k

* camera WB - 02 5500k

* camera WB - 03 6500k

* camera WB - 04 CAMRAW

#####Continuous Shot (HERO3):

* camera CS - 00 Single

* camera CS - 03 3SPS

* camera CS - 05 5SPS

* camera CS - 0a 10SPS

#####Burst Rate HERO3:

* camera BU - 00 3/1s

* camera BU - 02 10/1s

* camera BU - 03 10/2s

* camera BU - 04 30/1s

* camera BU - 05 30/2s

* camera BU - 06 30/3s

#####Loop Video HERO3:

* camera LO - 00 OFF

* camera LO - 01 5min

* camera LO - 02 20Min

* camera LO - 03 60Min

* camera LO - 05 Max

#####Protune ON/OFF:

* camera PT - 01 ON

* camera PT - 00 OFF

#####Delete:

* camera DL - (no number) last

* camera DA - (no number) all

* camera DF - delete specific?

#####Photo resolution Black ed:

* camera PR - 05 12mpW

* camera PR - 04 7mpW

* camera PR - 06 7mpM

* camera PR - 03 5mpM

#####Leds:

* bacpac LB - 00 no leds

* camera LB - 01 2 leds

* camera LB - 02 4 leds

#####Spot Meter:

* camera EX - 00 OFF

* camera EX - 01 ON

#####One Button Mode:

* camera OB - 00 OFF

* camera OB - 01 ON

#####Protune Resolutions HERO2 and HERO3 silver:

* camera VR - 07 1080 30 Protune

* camera VR - 08 1080 24 Protune

* camera VR - 11 1080 25 Protune

* camera VR - 09 960 60 Protune

#####Protune Resolutions HERO3 black ONLY IF PROTUNE IS ON:

* camera VV 00 720 120T

* camera VV 02 960 100T

* camera VV 03 1080 60T

* camera VV 04 1440 48T

* camera VV 05 2.7k 30T

* camera VV 06 4k 15T

* camera VV 07 2.7KCin24T

* camera VV 08 4kCin12T

#####Auto Power Off:

* camera AO - 00 NEVER

* camera AO - 01 60s

* camera AO - 02 120s

* camera AO - 03 300s

#####Default Mode:

* camera DM - 00 Video

* camera DM - 01 Photo

* camera DM - 02 Burst

* camera DM - 03 Timelapse

#####OnScreen Display:

* camera OS - 00 OFF

* camera OS - 01 ON

#####Locate:

* camera LL - 01 Start

* camera LL - 00 Stop

#####Video Mode:

* camera VM - 00 NTSC

* camera VM - 01 PAL

####Commands - HERO4:

The HERO2/3/3+ commands also work with HERO4 but its not recommended to use them!

HERO4 do not need any password in the URL

####Protune

#####Controls:

**Video**

* off: http://10.5.5.9/gp/gpControl/setting/10/0
* on: http://10.5.5.9/gp/gpControl/setting/10/1

**Photo**
* off: http://10.5.5.9/gp/gpControl/setting/21/0
* on: http://10.5.5.9/gp/gpControl/setting/21/1

#####White Balance:

**Video**

* Auto: http://10.5.5.9/gp/gpControl/setting/11/0
* 3000k: http://10.5.5.9/gp/gpControl/setting/11/1
* 5500k: http://10.5.5.9/gp/gpControl/setting/11/2
* 6500k: http://10.5.5.9/gp/gpControl/setting/11/3
* Native: http://10.5.5.9/gp/gpControl/setting/11/4

**Photo**

* Auto: http://10.5.5.9/gp/gpControl/setting/23/0
* 3000k: http://10.5.5.9/gp/gpControl/setting/23/1
* 5500k: http://10.5.5.9/gp/gpControl/setting/23/2
* 6500k: http://10.5.5.9/gp/gpControl/setting/23/3
* Native: http://10.5.5.9/gp/gpControl/setting/23/4

#####Color:

**Video**

* GOPRO: http://10.5.5.9/gp/gpControl/setting/12/0
* Flat: http://10.5.5.9/gp/gpControl/setting/12/1

**Photo**

* GOPRO: http://10.5.5.9/gp/gpControl/setting/23/0
* Flat: http://10.5.5.9/gp/gpControl/setting/23/1

#####ISO:

**Video**

* 6400: http://10.5.5.9/gp/gpControl/setting/13/0
* 1600: http://10.5.5.9/gp/gpControl/setting/13/1
* 400: http://10.5.5.9/gp/gpControl/setting/13/2

**Photo**

* 800: http://10.5.5.9/gp/gpControl/setting/24/0
* 400: http://10.5.5.9/gp/gpControl/setting/24/1
* 200: http://10.5.5.9/gp/gpControl/setting/24/2
* 100: http://10.5.5.9/gp/gpControl/setting/24/3

#####Sharpness:

**Video**

* High: http://10.5.5.9/gp/gpControl/setting/14/0
* Med: http://10.5.5.9/gp/gpControl/setting/14/1
* Low: http://10.5.5.9/gp/gpControl/setting/14/2

**Photo**

* High: http://10.5.5.9/gp/gpControl/setting/25/0
* Med: http://10.5.5.9/gp/gpControl/setting/25/1
* Low: http://10.5.5.9/gp/gpControl/setting/25/2


#####EV:

**Video**

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

**Photo**

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

---

#####Primary modes:
* Video: http://10.5.5.9/gp/gpControl/command/mode?p=0
* Photo: http://10.5.5.9/gp/gpControl/command/mode?p=1
* MultiShot: http://10.5.5.9/gp/gpControl/command/mode?p=2

#####Secondary modes:

* Video (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=0
* TimeLapse Video (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=1
* Video + Photo (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=2
* Looping (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=3
* Single (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=0
* Continuous (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=1
* Night (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=2
* Burst (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=0
* Timelapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=1
* NightLapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=2


#####Power:

* Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep

#####Frame Rate:
* 120fps:	http://10.5.5.9/gp/gpControl/setting/3/0
* 90fps:	http://10.5.5.9/gp/gpControl/setting/3/3
* 60fps:	http://10.5.5.9/gp/gpControl/setting/3/5
* 48fps:	http://10.5.5.9/gp/gpControl/setting/3/7
* 30fps:	http://10.5.5.9/gp/gpControl/setting/3/8
* 24fps:	http://10.5.5.9/gp/gpControl/setting/3/10

#####Resolutions:
* 4K: http://10.5.5.9/gp/gpControl/setting/2/1
* 4K SuperView: http://10.5.5.9/gp/gpControl/setting/2/2
* 2.7K: http://10.5.5.9/gp/gpControl/setting/2/4
* 2.7K SuperView: http://10.5.5.9/gp/gpControl/setting/2/5
* 2.7K 4:3: http://10.5.5.9/gp/gpControl/setting/2/6
* 1440p: http://10.5.5.9/gp/gpControl/setting/2/7
* 1080p SuperView: http://10.5.5.9/gp/gpControl/setting/2/8
* 1080p: http://10.5.5.9/gp/gpControl/setting/2/9
* 960p: http://10.5.5.9/gp/gpControl/setting/2/10
* 720p SuperView: http://10.5.5.9/gp/gpControl/setting/2/11
* 720p: http://10.5.5.9/gp/gpControl/setting/2/12
* WVGA: http://10.5.5.9/gp/gpControl/setting/2/13

#####FOV

* Wide: http://10.5.5.9/gp/gpControl/setting/4/0
* Medium: http://10.5.5.9/gp/gpControl/setting/4/1
* Narrow: http://10.5.5.9/gp/gpControl/setting/4/2

#####Exposure time for NightPhoto:

* Auto: http://10.5.5.9/gp/gpControl/setting/19/0
* 2: http://10.5.5.9/gp/gpControl/setting/19/1
* 5: http://10.5.5.9/gp/gpControl/setting/19/2
* 10: http://10.5.5.9/gp/gpControl/setting/19/3
* 15: http://10.5.5.9/gp/gpControl/setting/19/4
* 20: http://10.5.5.9/gp/gpControl/setting/19/5
* 30: http://10.5.5.9/gp/gpControl/setting/19/6

#####Exposure time for NightLapse:

* Auto: http://10.5.5.9/gp/gpControl/setting/31/0
* 2: http://10.5.5.9/gp/gpControl/setting/31/1
* 5: http://10.5.5.9/gp/gpControl/setting/31/2
* 10: http://10.5.5.9/gp/gpControl/setting/31/3
* 15: http://10.5.5.9/gp/gpControl/setting/31/4
* 20: http://10.5.5.9/gp/gpControl/setting/31/5
* 30: http://10.5.5.9/gp/gpControl/setting/31/6

#####Interval for NightLapse

* Continuous: http://10.5.5.9/gp/gpControl/setting/30/0
* 4s: http://10.5.5.9/gp/gpControl/setting/30/1
* 5s: http://10.5.5.9/gp/gpControl/setting/30/2
* 10s: http://10.5.5.9/gp/gpControl/setting/30/3
* 15s: http://10.5.5.9/gp/gpControl/setting/30/4
* 20s: http://10.5.5.9/gp/gpControl/setting/30/5
* 30s: http://10.5.5.9/gp/gpControl/setting/30/6
* 1m: http://10.5.5.9/gp/gpControl/setting/30/7
* 2m: http://10.5.5.9/gp/gpControl/setting/30/8
* 5m: http://10.5.5.9/gp/gpControl/setting/30/9
* 30m: http://10.5.5.9/gp/gpControl/setting/30/10
* 60m: http://10.5.5.9/gp/gpControl/setting/30/11


#####Photo resolution:

* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 7MP Wide: http://10.5.5.9/gp/gpControl/setting/17/1
* 7MP Medi: http://10.5.5.9/gp/gpControl/setting/17/2
* 5MP Wide: http://10.5.5.9/gp/gpControl/setting/17/3

#####Low Light:
* ON: http://10.5.5.9/gp/gpControl/setting/8/1
* OFF: http://10.5.5.9/gp/gpControl/setting/8/0

#####Timelapse Interval (TIMELAPSE MODE on MultiShot):

* 0.5: http://10.5.5.9/gp/gpControl/setting/5/0
* 1: http://10.5.5.9/gp/gpControl/setting/5/1
* 2: http://10.5.5.9/gp/gpControl/setting/5/2
* 5: http://10.5.5.9/gp/gpControl/setting/5/3
* 10: http://10.5.5.9/gp/gpControl/setting/5/4
* 30: http://10.5.5.9/gp/gpControl/setting/5/5
* 60: http://10.5.5.9/gp/gpControl/setting/5/6

#####Continuous photo rate:

* 3: http://10.5.5.9/gp/gpControl/setting/18/0
* 5: http://10.5.5.9/gp/gpControl/setting/18/1
* 10: http://10.5.5.9/gp/gpControl/setting/18/2

#####Video Looping Duration:

* Max: http://10.5.5.9/gp/gpControl/setting/6/0
* 5Min: http://10.5.5.9/gp/gpControl/setting/6/1
* 20Min: http://10.5.5.9/gp/gpControl/setting/6/2
* 60Min: http://10.5.5.9/gp/gpControl/setting/6/3
* 120Min: http://10.5.5.9/gp/gpControl/setting/6/4

#####Video+Photo Interval:

* 5: http://10.5.5.9/gp/gpControl/setting/7/1
* 10: http://10.5.5.9/gp/gpControl/setting/7/2
* 30: http://10.5.5.9/gp/gpControl/setting/7/3
* 60Min: http://10.5.5.9/gp/gpControl/setting/7/4

#####Spot Meter:

**Video**

* off: http://10.5.5.9/gp/gpControl/setting/9/0
* on: http://10.5.5.9/gp/gpControl/setting/9/1

**Photo**

* off: http://10.5.5.9/gp/gpControl/setting/20/0
* on: http://10.5.5.9/gp/gpControl/setting/20/1

####Burst Rate:

* 3/1: http://10.5.5.9/gp/gpControl/setting/29/0
* 5/1: http://10.5.5.9/gp/gpControl/setting/29/1
* 10/1: http://10.5.5.9/gp/gpControl/setting/29/2
* 10/2: http://10.5.5.9/gp/gpControl/setting/29/3
* 10/3: http://10.5.5.9/gp/gpControl/setting/29/4
* 30/1: http://10.5.5.9/gp/gpControl/setting/29/5
* 30/2: http://10.5.5.9/gp/gpControl/setting/29/6
* 30/3: http://10.5.5.9/gp/gpControl/setting/29/7
* 30/6: http://10.5.5.9/gp/gpControl/setting/29/8

#####Shutter
* Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
* Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

#####Tag moment:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment

#####Delete file:

http://10.5.5.9/gp/gpControl/command/storage/delete?p=file (eg. /100GOPRO/G0010124.JPG)

#####List files

http://10.5.5.9:8080/gp/gpMediaList

#####Download thumbnail

http://10.5.5.9/gp/gpMediaMetadata?p=file (eg. /100GOPRO/G0010126.JPG)
