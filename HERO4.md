##HERO4 commands, live preview and more.

Lots of people contributed to the HERO4 wifi reverse engineering, thank you!

##Commands:

###Protune
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

* 6400: http://10.5.5.9/gp/gpControl/setting/13/0
* 1600: http://10.5.5.9/gp/gpControl/setting/13/1
* 400: http://10.5.5.9/gp/gpControl/setting/13/2

#####Sharpness:

* High: http://10.5.5.9/gp/gpControl/setting/14/0
* Med: http://10.5.5.9/gp/gpControl/setting/14/1
* Low: http://10.5.5.9/gp/gpControl/setting/14/2

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

---

####Primary modes:
* Video: http://10.5.5.9/gp/gpControl/command/mode?p=0
* Photo: http://10.5.5.9/gp/gpControl/command/mode?p=1
* MultiShot: http://10.5.5.9/gp/gpControl/command/mode?p=2

####Secondary modes:

* Video (VIDEO): http://10.5.5.9/gp/gpControl/setting/68/0
* TimeLapse Video (VIDEO): http://10.5.5.9/gp/gpControl/setting/68/1
* Video + Photo (VIDEO): http://10.5.5.9/gp/gpControl/setting/68/2
* Looping (VIDEO): http://10.5.5.9/gp/gpControl/setting/68/3
* Single (PHOTO): http://10.5.5.9/gp/gpControl/setting/69/0
* Continuous (PHOTO): http://10.5.5.9/gp/gpControl/setting/69/1
* Night (PHOTO): http://10.5.5.9/gp/gpControl/setting/69/2
* Burst (MultiShot): http://10.5.5.9/gp/gpControl/setting/70/0
* Timelapse (MultiShot): http://10.5.5.9/gp/gpControl/setting/70/1
* NightLapse (MultiShot): http://10.5.5.9/gp/gpControl/setting/70/2


###Power:

* Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep

###Frame Rate:
* 120fps:	http://10.5.5.9/gp/gpControl/setting/3/0
* 90fps:	http://10.5.5.9/gp/gpControl/setting/3/3
* 60fps:	http://10.5.5.9/gp/gpControl/setting/3/5
* 48fps:	http://10.5.5.9/gp/gpControl/setting/3/7
* 30fps:	http://10.5.5.9/gp/gpControl/setting/3/8
* 24fps:	http://10.5.5.9/gp/gpControl/setting/3/10

###Resolutions:
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

###Exposure time for NightPhoto:

* Auto: http://10.5.5.9/gp/gpControl/setting/19/0
* 2: http://10.5.5.9/gp/gpControl/setting/19/1
* 5: http://10.5.5.9/gp/gpControl/setting/19/2
* 10: http://10.5.5.9/gp/gpControl/setting/19/3
* 15: http://10.5.5.9/gp/gpControl/setting/19/4
* 20: http://10.5.5.9/gp/gpControl/setting/19/5
* 30: http://10.5.5.9/gp/gpControl/setting/19/6

###Exposure time for NightLapse:

* Auto: http://10.5.5.9/gp/gpControl/setting/31/0
* 2: http://10.5.5.9/gp/gpControl/setting/31/1
* 5: http://10.5.5.9/gp/gpControl/setting/31/2
* 10: http://10.5.5.9/gp/gpControl/setting/31/3
* 15: http://10.5.5.9/gp/gpControl/setting/31/4
* 20: http://10.5.5.9/gp/gpControl/setting/31/5
* 30: http://10.5.5.9/gp/gpControl/setting/31/6

###Photo resolution:

* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 7MP Wide: http://10.5.5.9/gp/gpControl/setting/17/1
* 7MP Medi: http://10.5.5.9/gp/gpControl/setting/17/2
* 5MP Wide: http://10.5.5.9/gp/gpControl/setting/17/3

###Field Of View:
* Wide: http://10.5.5.9/gp/gpControl/setting/4/0
* Medium: http://10.5.5.9/gp/gpControl/setting/4/1
* Narrow: http://10.5.5.9/gp/gpControl/setting/4/2

###Low Light:
* ON: http://10.5.5.9/gp/gpControl/setting/8/1
* OFF: http://10.5.5.9/gp/gpControl/setting/8/0

###Timelapse Interval (TIMELAPSE MODE on MultiShot):

* 0.5: http://10.5.5.9/gp/gpControl/setting/5/0
* 1: http://10.5.5.9/gp/gpControl/setting/5/1
* 2: http://10.5.5.9/gp/gpControl/setting/5/2
* 5: http://10.5.5.9/gp/gpControl/setting/5/3
* 10: http://10.5.5.9/gp/gpControl/setting/5/4
* 30: http://10.5.5.9/gp/gpControl/setting/5/5
* 60: http://10.5.5.9/gp/gpControl/setting/5/6

###Continuous photo rate:

* 3: http://10.5.5.9/gp/gpControl/setting/18/0
* 5: http://10.5.5.9/gp/gpControl/setting/18/1
* 10: http://10.5.5.9/gp/gpControl/setting/18/2

###Video Looping Duration:

* Max: http://10.5.5.9/gp/gpControl/setting/6/0
* 5Min: http://10.5.5.9/gp/gpControl/setting/6/1
* 20Min: http://10.5.5.9/gp/gpControl/setting/6/2
* 60Min: http://10.5.5.9/gp/gpControl/setting/6/3
* 120Min: http://10.5.5.9/gp/gpControl/setting/6/4

###Video+Photo Interval:

* 5: http://10.5.5.9/gp/gpControl/setting/7/1
* 10: http://10.5.5.9/gp/gpControl/setting/7/2
* 30: http://10.5.5.9/gp/gpControl/setting/7/3
* 60Min: http://10.5.5.9/gp/gpControl/setting/7/4

###Spot Meter:

* off: http://10.5.5.9/gp/gpControl/setting/9/0
* on: http://10.5.5.9/gp/gpControl/setting/9/1


###Shutter
* Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
* Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

###Streaming:
* Start Streaming http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=start
* Restart Streaming http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=restart
* Stop Streaming http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=stop

Video can be streamed by using `aplay` or `ffplay` on `udp://:8554`, connection must be kept alive using [hero4-udp-keep-alive-send.py](https://gist.github.com/3v1n0/38bcd4f7f0cb3c279bad#file-hero4-udp-keep-alive-send-py) script.

####Tag moment:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment

