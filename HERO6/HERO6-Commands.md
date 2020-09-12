### GoPro HERO6 Commands, Status and Notes

Firmware revision: HD6.01.01.51.00

Sample /status

```
{"status":{
"1":1,"2":3,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":86,"29":"","30":"GP24784461","31":0,"32":0,"33":0,"34":4155,"35":6542,"36":3,"37":4,"38":3,"39":4,"40":"%11%02%12%12%38%3A","41":0,"42":0,"43":0,"44":0,"45":0,"46":1,"47":1,"48":1,"49":0,"54":27655117,"55":1,"56":4,"57":146925,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0,"65":0,"66":0,"67":0,"68":0,"69":1,"70":84,"71":12,"72":16,"73":13},
"settings":{"1":0,"2":9,"3":8,"4":4,"5":0,"6":1,"7":1,"8":1,"9":0,"10":0,"11":0,"12":0,"13":1,"14":0,"15":4,"16":0,"17":10,"18":4,"19":0,"20":0,"21":1,"22":0,"23":0,"24":4,"25":0,"26":4,"27":0,"28":10,"29":5,"30":0,"31":0,"32":3601,"33":0,"34":0,"35":0,"36":0,"37":4,"38":0,"39":4,"50":0,"51":1,"52":0,"54":1,"57":0,"58":1,"59":6,"60":8,"61":1,"62":2500000,"63":7,"64":4,"68":0,"69":1,"70":0,"72":1,"73":0,"74":0,"75":3,"76":3,"77":0,"78":0,"79":0,"80":2,"81":3,"82":0,"83":1,"84":0,"85":0,"86":1,"87":40,"88":100,"89":12,"91":2}}
```

## Basic controls:

##### Shutter
* Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
* Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

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
* Video + Photo (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=2
* Looping (VIDEO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=0&sub_mode=3
* Single (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=1
* Night (PHOTO): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=1&sub_mode=2
* Burst (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=0
* Timelapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=1
* NightLapse (MultiShot): http://10.5.5.9/gp/gpControl/command/sub_mode?mode=2&sub_mode=2

##### Tag moment:

* Sends tag command: http://10.5.5.9/gp/gpControl/command/storage/tag_moment

##### Locate:

* On: http://10.5.5.9/gp/gpControl/command/system/locate?p=1
* Off: http://10.5.5.9/gp/gpControl/command/system/locate?p=0

##### Power:

* Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep
* Power On: Send a Wake On Lan command with the parameters: IP address: 10.5.5.9, Subnet Mask 255.255.255.0, Port 9.

##### Digital Zoom:

http://10.5.5.9/gp/gpControl/command/digital_zoom?range_pcnt=[PERCENTAGE FROM 0 to 100]

##### Pairing new device:

#### Pairing:

Initiate pairing in Connections > New > GoPro App

http://10.5.5.9/gp/gpControl/command/wireless/pair/complete?success=1&deviceName=DESKTOP

## Capture Mode settings:

#### Video:

##### Resolutions:
* 4K: http://10.5.5.9/gp/gpControl/setting/2/1
* 4K 4:3: http://10.5.5.9/gp/gpControl/setting/2/18
* 2.7K: http://10.5.5.9/gp/gpControl/setting/2/4
* 2.7K 4:3: http://10.5.5.9/gp/gpControl/setting/2/6
* 1440p: http://10.5.5.9/gp/gpControl/setting/2/7
* 1080p: http://10.5.5.9/gp/gpControl/setting/2/9
* 960p: http://10.5.5.9/gp/gpControl/setting/2/10
* 720p: http://10.5.5.9/gp/gpControl/setting/2/12

##### Frame Rate:
* 240fps:	http://10.5.5.9/gp/gpControl/setting/3/0
* 120fps:	http://10.5.5.9/gp/gpControl/setting/3/1
* 100fps:	http://10.5.5.9/gp/gpControl/setting/3/2
* 90fps:	http://10.5.5.9/gp/gpControl/setting/3/3
* 80fps:	http://10.5.5.9/gp/gpControl/setting/3/4
* 60fps:	http://10.5.5.9/gp/gpControl/setting/3/5
* 50fps:	http://10.5.5.9/gp/gpControl/setting/3/6
* 48fps:	http://10.5.5.9/gp/gpControl/setting/3/7
* 30fps:	http://10.5.5.9/gp/gpControl/setting/3/8
* 25fps:	http://10.5.5.9/gp/gpControl/setting/3/9

##### FOV

* Wide: http://10.5.5.9/gp/gpControl/setting/4/0
* Medium: http://10.5.5.9/gp/gpControl/setting/4/1
* Narrow: http://10.5.5.9/gp/gpControl/setting/4/2
* SuperView: http://10.5.5.9/gp/gpControl/4/3
* Linear: http://10.5.5.9/gp/gpControl/setting/4/4

##### Low Light:
* ON: http://10.5.5.9/gp/gpControl/setting/8/1
* OFF: http://10.5.5.9/gp/gpControl/setting/8/0

##### Video Looping Duration:

* Max: http://10.5.5.9/gp/gpControl/setting/6/0
* 5Min: http://10.5.5.9/gp/gpControl/setting/6/1
* 20Min: http://10.5.5.9/gp/gpControl/setting/6/2
* 60Min: http://10.5.5.9/gp/gpControl/setting/6/3
* 120Min: http://10.5.5.9/gp/gpControl/setting/6/4

##### Video+Photo Interval:

* 5: http://10.5.5.9/gp/gpControl/setting/7/1
* 10: http://10.5.5.9/gp/gpControl/setting/7/2
* 30: http://10.5.5.9/gp/gpControl/setting/7/3
* 60Min: http://10.5.5.9/gp/gpControl/setting/7/4

##### Video Timelapse Interval:

* 0.5: http://10.5.5.9/gp/gpControl/setting/5/0
* 1: http://10.5.5.9/gp/gpControl/setting/5/1
* 2: http://10.5.5.9/gp/gpControl/setting/5/2
* 5: http://10.5.5.9/gp/gpControl/setting/5/3
* 10: http://10.5.5.9/gp/gpControl/setting/5/4
* 30: http://10.5.5.9/gp/gpControl/setting/5/5
* 60: http://10.5.5.9/gp/gpControl/setting/5/6


##### EIS (Video Stabilisation):
* On: http://10.5.5.9/gp/gpControl/setting/78/1
* Off: http://10.5.5.9/gp/gpControl/setting/78/0

##### ProTune:
* off: http://10.5.5.9/gp/gpControl/setting/10/0
* on: http://10.5.5.9/gp/gpControl/setting/10/1

##### White Balance:

* Auto: http://10.5.5.9/gp/gpControl/setting/11/0
* 3000k: http://10.5.5.9/gp/gpControl/setting/11/1
* 4000k: http://10.5.5.9/gp/gpControl/setting/11/5
* 4800k: http://10.5.5.9/gp/gpControl/setting/11/6
* 5500k: http://10.5.5.9/gp/gpControl/setting/11/2
* 6000k: http://10.5.5.9/gp/gpControl/setting/11/7
* 6500k: http://10.5.5.9/gp/gpControl/setting/11/3
* Native: http://10.5.5.9/gp/gpControl/setting/11/4

##### Color:

* GOPRO: http://10.5.5.9/gp/gpControl/setting/12/0
* Flat: http://10.5.5.9/gp/gpControl/setting/12/1

##### Min ISO:

* 6400: http://10.5.5.9/gp/gpControl/setting/102/0
* 1600: http://10.5.5.9/gp/gpControl/setting/102/1
* 400: http://10.5.5.9/gp/gpControl/setting/102/2
* 3200: http://10.5.5.9/gp/gpControl/setting/102/3
* 800: http://10.5.5.9/gp/gpControl/setting/102/4
* 200: http://10.5.5.9/gp/gpControl/setting/102/7
* 100: http://10.5.5.9/gp/gpControl/setting/102/8

##### ISO Limit:

* 6400: http://10.5.5.9/gp/gpControl/setting/13/0
* 1600: http://10.5.5.9/gp/gpControl/setting/13/1
* 400: http://10.5.5.9/gp/gpControl/setting/13/2
* 3200: http://10.5.5.9/gp/gpControl/setting/13/3
* 800: http://10.5.5.9/gp/gpControl/setting/13/4
* 200: http://10.5.5.9/gp/gpControl/setting/13/7
* 100: http://10.5.5.9/gp/gpControl/setting/13/8

##### ISO Mode/Lock:

* Max: http://10.5.5.9/gp/gpControl/setting/74/0
* Lock: http://10.5.5.9/gp/gpControl/setting/74/1

##### Sharpness:

* High: http://10.5.5.9/gp/gpControl/setting/14/0
* Med: http://10.5.5.9/gp/gpControl/setting/14/1
* Low: http://10.5.5.9/gp/gpControl/setting/14/2

##### Manual Video Exposure:

* Auto Mode: http://10.5.5.9/gp/gpControl/setting/73/0

EV compensation is enabled ONLY in Auto mode.

* For 24FPS:
	* 1/24: http://10.5.5.9/gp/gpControl/setting/73/3
	* 1/48: http://10.5.5.9/gp/gpControl/setting/73/6
	* 1/96: http://10.5.5.9/gp/gpControl/setting/73/11
* For 30FPS:
	* 1/30: http://10.5.5.9/gp/gpControl/setting/73/5
	* 1/60: http://10.5.5.9/gp/gpControl/setting/73/8
	* 1/120: http://10.5.5.9/gp/gpControl/setting/73/13
* For 48FPS:
	* 1/48: http://10.5.5.9/gp/gpControl/setting/73/6
	* 1/96: http://10.5.5.9/gp/gpControl/setting/73/11
	* 1/192: http://10.5.5.9/gp/gpControl/setting/73/16
* For 60FPS:
	* 1/60: http://10.5.5.9/gp/gpControl/setting/73/8
	* 1/120: http://10.5.5.9/gp/gpControl/setting/73/13
	* 1/240: http://10.5.5.9/gp/gpControl/setting/73/18
* For 90FPS:
	* 1/90: http://10.5.5.9/gp/gpControl/setting/73/10
	* 1/180: http://10.5.5.9/gp/gpControl/setting/73/15
	* 1/360: http://10.5.5.9/gp/gpControl/setting/73/20
* For 120FPS:
	* 1/120: http://10.5.5.9/gp/gpControl/setting/73/13
	* 1/240: http://10.5.5.9/gp/gpControl/setting/73/18
	* 1/480: http://10.5.5.9/gp/gpControl/setting/73/22
* For 240FPS:
	* 1/120: http://10.5.5.9/gp/gpControl/setting/73/18
	* 1/240: http://10.5.5.9/gp/gpControl/setting/73/22
	* 1/480: http://10.5.5.9/gp/gpControl/setting/73/23

##### EV Steps:

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

* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 12MP Linear: http://10.5.5.9/gp/gpControl/setting/17/10
* 12MP Medium: http://10.5.5.9/gp/gpControl/setting/17/8
* 12MP Narrow: http://10.5.5.9/gp/gpControl/setting/17/9

##### Exposure time for NightPhoto:

* Auto: http://10.5.5.9/gp/gpControl/setting/19/0
* 2: http://10.5.5.9/gp/gpControl/setting/19/1
* 5: http://10.5.5.9/gp/gpControl/setting/19/2
* 10: http://10.5.5.9/gp/gpControl/setting/19/3
* 15: http://10.5.5.9/gp/gpControl/setting/19/4
* 20: http://10.5.5.9/gp/gpControl/setting/19/5
* 30: http://10.5.5.9/gp/gpControl/setting/19/6

###### RAW Photo:
* On: http://10.5.5.9/gp/gpControl/setting/82/1
* Off: http://10.5.5.9/gp/gpControl/setting/82/0

###### RAW NightPhoto:
* On: http://10.5.5.9/gp/gpControl/setting/98/1
* Off: http://10.5.5.9/gp/gpControl/setting/98/0

###### HDR Photo:

* On: http://10.5.5.9/gp/gpControl/setting/100/1
* Off: http://10.5.5.9/gp/gpControl/setting/100/0

##### ProTune:

* off: http://10.5.5.9/gp/gpControl/setting/21/0
* on: http://10.5.5.9/gp/gpControl/setting/21/1

##### White Balance:

* Auto: http://10.5.5.9/gp/gpControl/setting/22/0
* 3000k: http://10.5.5.9/gp/gpControl/setting/22/1
* 2300K: http://10.5.5.9/gp/gpControl/setting/22/8
* 2800K: http://10.5.5.9/gp/gpControl/setting/22/9
* 3200K: http://10.5.5.9/gp/gpControl/setting/22/10
* 4000k: http://10.5.5.9/gp/gpControl/setting/22/5
* 4500K: http://10.5.5.9/gp/gpControl/setting/22/11
* 4800k: http://10.5.5.9/gp/gpControl/setting/22/6
* 5500k: http://10.5.5.9/gp/gpControl/setting/22/2
* 6000k: http://10.5.5.9/gp/gpControl/setting/22/7
* 6500k: http://10.5.5.9/gp/gpControl/setting/22/3
* Native: http://10.5.5.9/gp/gpControl/setting/22/4

##### Color:

* GOPRO: http://10.5.5.9/gp/gpControl/setting/23/0
* Flat: http://10.5.5.9/gp/gpControl/setting/23/1

##### ISO Limit:

* 800: http://10.5.5.9/gp/gpControl/setting/24/0
* 400: http://10.5.5.9/gp/gpControl/setting/24/1
* 200: http://10.5.5.9/gp/gpControl/setting/24/2
* 100: http://10.5.5.9/gp/gpControl/setting/24/3

##### ISO Min:

* 800: http://10.5.5.9/gp/gpControl/setting/75/0
* 400: http://10.5.5.9/gp/gpControl/setting/75/1
* 200: http://10.5.5.9/gp/gpControl/setting/75/2
* 100: http://10.5.5.9/gp/gpControl/setting/75/3

##### Sharpness:

* High: http://10.5.5.9/gp/gpControl/setting/25/0
* Med: http://10.5.5.9/gp/gpControl/setting/25/1
* Low: http://10.5.5.9/gp/gpControl/setting/25/2

##### EV Steps:

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

##### Protune Shutter:

* Auto: http://10.5.5.9/gp/gpControl/setting/97/0
* 1/125: http://10.5.5.9/gp/gpControl/setting/97/1
* 1/250: http://10.5.5.9/gp/gpControl/setting/97/2
* 1/500: http://10.5.5.9/gp/gpControl/setting/97/3
* 1/1000: http://10.5.5.9/gp/gpControl/setting/97/4
* 1/2000: http://10.5.5.9/gp/gpControl/setting/97/5

---

#### MultiShot:

##### Photo Resolution for MultiShot Modes:

* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 12MP Linear: http://10.5.5.9/gp/gpControl/setting/17/10
* 12MP Medium: http://10.5.5.9/gp/gpControl/setting/17/8
* 12MP Narrow: http://10.5.5.9/gp/gpControl/setting/17/9

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

###### RAW Photo TimeLapse:
* On: http://10.5.5.9/gp/gpControl/setting/94/1
* Off: http://10.5.5.9/gp/gpControl/setting/94/0

###### RAW Photo NightLapse:
* On: http://10.5.5.9/gp/gpControl/setting/99/1
* Off: http://10.5.5.9/gp/gpControl/setting/99/0

##### WDR TimeLapse:

* On: http://10.5.5.9/gp/gpControl/setting/93/1
* Off: http://10.5.5.9/gp/gpControl/setting/93/0

##### ProTune:

* off: http://10.5.5.9/gp/gpControl/setting/34/0
* on: http://10.5.5.9/gp/gpControl/setting/34/1

##### White Balance:

* Auto: http://10.5.5.9/gp/gpControl/setting/35/0
* 2300K: http://10.5.5.9/gp/gpControl/setting/35/8
* 2800K: http://10.5.5.9/gp/gpControl/setting/35/9
* 3000k: http://10.5.5.9/gp/gpControl/setting/35/1
* 3200K: http://10.5.5.9/gp/gpControl/setting/35/10
* 4000k: http://10.5.5.9/gp/gpControl/setting/35/5
* 4500K: http://10.5.5.9/gp/gpControl/setting/35/11
* 4800k: http://10.5.5.9/gp/gpControl/setting/35/6
* 5500k: http://10.5.5.9/gp/gpControl/setting/35/2
* 6000k: http://10.5.5.9/gp/gpControl/setting/35/7
* 6500k: http://10.5.5.9/gp/gpControl/setting/35/3
* Native: http://10.5.5.9/gp/gpControl/setting/35/4

##### Color:

* GOPRO: http://10.5.5.9/gp/gpControl/setting/36/0
* Flat: http://10.5.5.9/gp/gpControl/setting/36/1

##### ISO Limit:

* 800: http://10.5.5.9/gp/gpControl/setting/37/0
* 400: http://10.5.5.9/gp/gpControl/setting/37/1
* 200: http://10.5.5.9/gp/gpControl/setting/37/2
* 100: http://10.5.5.9/gp/gpControl/setting/37/3

##### ISO Min:

* 800: http://10.5.5.9/gp/gpControl/setting/76/0
* 400: http://10.5.5.9/gp/gpControl/setting/76/1
* 200: http://10.5.5.9/gp/gpControl/setting/76/2
* 100: http://10.5.5.9/gp/gpControl/setting/76/3

##### Sharpness:

* High: http://10.5.5.9/gp/gpControl/setting/38/0
* Med: http://10.5.5.9/gp/gpControl/setting/38/1
* Low: http://10.5.5.9/gp/gpControl/setting/38/2

##### EV Steps:

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

## General Camera Settings:

##### Orientation:

* Up: http://10.5.5.9/gp/gpControl/setting/52/1
* Down: http://10.5.5.9/gp/gpControl/setting/52/2
* Gyro based: http://10.5.5.9/gp/gpControl/setting/52/0

##### Quick Capture:
* On: http://10.5.5.9/gp/gpControl/setting/54/1
* Off: http://10.5.5.9/gp/gpControl/setting/54/0

##### GPS Tag:

* On: http://10.5.5.9/gp/gpControl/setting/83/1
* Off: http://10.5.5.9/gp/gpControl/setting/83/0

##### Voice control:

* On: http://10.5.5.9/gp/gpControl/setting/86/1
* Off: http://10.5.5.9/gp/gpControl/setting/86/0

##### LEDs on HERO6 Black:

* Off: http://10.5.5.9/gp/gpControl/setting/91/0
* On: http://10.5.5.9/gp/gpControl/setting/91/2
* Front off: http://10.5.5.9/gp/gpControl/setting/91/1

##### Camera system language:

* English: http://10.5.5.9/gp/gpControl/setting/84/0
* Chinese: http://10.5.5.9/gp/gpControl/setting/84/1
* German: http://10.5.5.9/gp/gpControl/setting/84/2
* Italian: http://10.5.5.9/gp/gpControl/setting/84/3
* Spanish: http://10.5.5.9/gp/gpControl/setting/84/4
* Japanese: http://10.5.5.9/gp/gpControl/setting/84/5
* French: http://10.5.5.9/gp/gpControl/setting/84/6

##### Voice control language:

* English - US: http://10.5.5.9/gp/gpControl/setting/85/0
* English - UK: http://10.5.5.9/gp/gpControl/setting/85/1
* English - AUS: http://10.5.5.9/gp/gpControl/setting/85/2
* German: http://10.5.5.9/gp/gpControl/setting/85/3
* French: http://10.5.5.9/gp/gpControl/setting/85/4
* Italian: http://10.5.5.9/gp/gpControl/setting/85/5
* Spanish: http://10.5.5.9/gp/gpControl/setting/85/6
* Spanish - NA: http://10.5.5.9/gp/gpControl/setting/85/7
* Chinese: http://10.5.5.9/gp/gpControl/setting/85/8
* Japanese: http://10.5.5.9/gp/gpControl/setting/85/9

##### Beeps:
* Off: http://10.5.5.9/gp/gpControl/setting/56/2
* 0.7: http://10.5.5.9/gp/gpControl/setting/56/1
* Full: http://10.5.5.9/gp/gpControl/setting/56/0

##### Video Format:
* NTSC: http://10.5.5.9/gp/gpControl/setting/57/0
* PAL: http://10.5.5.9/gp/gpControl/setting/57/1

##### LCD Display:
* On: http://10.5.5.9/gp/gpControl/setting/72/1
* Off: http://10.5.5.9/gp/gpControl/setting/72/0

##### On Screen Display:
* On: http://10.5.5.9/gp/gpControl/setting/58/1
* Off: http://10.5.5.9/gp/gpControl/setting/58/0

##### LCD Brightness:
* High: http://10.5.5.9/gp/gpControl/setting/49/0
* Medium: http://10.5.5.9/gp/gpControl/setting/49/1
* Low: http://10.5.5.9/gp/gpControl/setting/49/2

##### LCD Lock:
 * On: http://10.5.5.9/gp/gpControl/setting/50/1
 * Off: http://10.5.5.9/gp/gpControl/setting/50/0

##### LCD Timeout sleep:

* LCD Never sleep: http://10.5.5.9/gp/gpControl/setting/51/0
* LCD 1min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/1
* LCD 2min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/2
* LCD 3min sleep timeout: http://10.5.5.9/gp/gpControl/setting/51/3

##### Auto Off:
* Never: http://10.5.5.9/gp/gpControl/setting/59/0
* 1m: http://10.5.5.9/gp/gpControl/setting/59/1
* 2m: http://10.5.5.9/gp/gpControl/setting/59/2
* 3m: http://10.5.5.9/gp/gpControl/setting/59/3
* 5m: http://10.5.5.9/gp/gpControl/setting/59/4

##### Auto Lock Screen:

* 7 sec timeout: http://10.5.5.9/gp/gpControl/setting/103/5
* off: http://10.5.5.9/gp/gpControl/setting/103/3

##### Turn on by saying "GoPro Turn On":

* ON: http://10.5.5.9/gp/gpControl/setting/104/1
* OFF: http://10.5.5.9/gp/gpControl/setting/104/0

##### Set date and time

* http://10.5.5.9/gp/gpControl/command/setup/date_time?p=%11%0b%10%11%29%2c

The hex string at the end is the same as for [HERO3](https://github.com/KonradIT/goprowifihack/blob/master/HERO3/WifiCommands.md#basics), so in the example: 11 = (20)17, 0b = 11 (November), 10 = 16, 11 = 17, 29 = 41, 2c = 44.
Example bash code for date string, see https://github.com/ztzhang/GoProWifiCommand/issues/3.

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



##### WiFi AP Settings:

* Turn WiFi OFF: http://10.5.5.9/gp/gpControl/setting/63/0
* Switch WiFi to App/Smartphone mode: http://10.5.5.9/gp/gpControl/setting/63/1
* Switch WiFi to GoPro RC: http://10.5.5.9/gp/gpControl/setting/63/2
* Switch WiFi to GoPro Smart Remote RC: http://10.5.5.9/gp/gpControl/setting/63/4

## Media Commands:

##### Delete file:

http://10.5.5.9/gp/gpControl/command/storage/delete?p=file (eg. /100GOPRO/G0010124.JPG)

##### Delete Last media taken:

http://10.5.5.9/gp/gpControl/command/storage/delete/last

##### Reformat SD Card (CAUTION!):

http://10.5.5.9/gp/gpControl/command/storage/delete/all

##### Tag moment in video file:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment/playback?p=XXXGOPRO/XXXXXX.MP4&tag=Miliseconds

XXXGOPRO is the folder, XXXXXX.MP4 is the video and Miliseconds are the miliseconds offset from the start of the video.

For example:

http://10.5.5.9/gp/gpControl/command/storage/tag_moment/playback?p=103GOPRO/GOPR1359.MP4&tag=2000

will make a HiLight Tag on 2 seconds of the video GOPR1359.MP4

##### Extracting a clip from a video (GoPro Clips):

**To start a video conversion:** 

http://10.5.5.9/gp/gpControl/command/transcode/request?source=DCIM/[XXXGOPRO]/GOPRXXXX.MP4&res=VIDEO_RESOLUTION&fps_divisor=FPS&in_ms=In_MS&out_ms=Out_MS

Parameters:

* VIDEO_RESOLUTION:
	* 1080 = 0
	* 960 = 1
	* 720 = 2
	* WVGA = 3
	* 640p = 4
	* 432x240 (live preview resolution) = 5
	* 320x240 = 6
* FPS: (Divide FPS by)
	* 1/1 = 0 (Leave it as is)
	* 1/2 = 1
	* 1/3 = 2
	* 1/4 = 3
	* 1/8 = 4

Output:

```
{"status":{"id":STATUS_ID,"source":"DCIM\XXXGOPRO\GOPRXXXX.MP4","status":0,"failure_reason":0,"estimate":1,"completion":0,"output":""}}
```

If you did it right.

```status``` values:

* 0 = Started
* 1 = In Progress
* 2 = Finished
* 3 = Cancelled
* 4 = Conversion failed
	
```failure_reason``` values:

* 0 = No fail
* 1 = Bad file
* 2 = Bad parameters
* 3 = No space left on the device
* 4 = Camera is busy converting something else

**To get the status of a conversion:**

http://10.5.5.9/gp/gpControl/command/transcode/status?id=STATUS_ID (from the previous command)

Output:

```
{"status":{"id":STATUS_ID,"source":"DCIM\XXXGOPRO\GOPRXXXX.MP4","status":2,"failure_reason":0,"estimate":1,"completion":0,"output":"DCIM/XXXGOPRO/GOPRXXXX.MP4"}}
```

You can now download the output url, add http://10.5.5.9/videos/ to it.

**To cancel a conversion:**

http://10.5.5.9/gp/gpControl/command/transcode/cancel?id=STATUS_ID

### Bluetooth Pairing:

**Allows the camera to be paired to a GoPro Bluetooth metadata device**

* List whitelisted (paired) devices: http://10.5.5.9/gp/gpControl/command/ble/whitelist/list
* Scan for devices: http://10.5.5.9/gp/gpControl/command/ble/scan?p=1
* List scanned devices: http://10.5.5.9/gp/gpControl/command/ble/scan/list

Returns (example):

```
{
  "list_id": 1,
  "total": 1,
  "index": 0,
  "index_count": 1,
  "device_array": [
    {
      "address": "device_address",
      "address_type": 0,
      "rssi": -92,
      "name": "",
      "profile_uuid16": [
        "9ffe"
      ]
    },
    ...
  ]
}
```
* Start pairing process: http://10.5.5.9/gp/gpControl/command/ble/pairing_available and http://10.5.5.9/gp/gpControl/command/ble/pairing_phase?p=1
* Get pairing status: http://10.5.5.9/gp/gpControl/command/ble/pair/status

Returns:

```

{"pairing_status":0}
```
* Pair with device: http://10.5.5.9/gp/gpControl/command/ble/pair/start?device=DEVICE_ID&address_type=ADDRESS_TYPE

	* DEVICE_ID = "address" from "device_array" in list
	* ADDRESS_TYPE = "address_type" from "device_array" in list


#### Connecting to a WiFi network:

* Scan for available networks: http://10.5.5.9/gp/gpControl/command/wireless/ssid/scan?p=1
* Return JSON of available networks: http://10.5.5.9/gp/gpControl/command/wireless/ssid/list

the JSON structure is:

```
{
  "scan_id": 1,
  "total": 5,
  "index": 0,
  "index_count": 5,
  "ssid_array": [
    {
      "ssid": "MyHomeNetwork",
      "auth_type": 1,
      "bars": 0
    },
    ...
  ]
}
```

* Save the network: http://10.5.5.9/gp/gpControl/command/wireless/ssid/save?ssid=WIFI_SSID&auth_type=AUTH_TYPE&pw=SSID_PASSWORD
	* WIFI_SSID = ssid
	* AUTH_TYPE = auth_type from the /list JSON, an integer (1 in the example)
	* SSID_PASSWORD = SSID password
* Connect to network: http://10.5.5.9/gp/gpControl/command/wireless/ssid/select?ssid=WIFI_SSID&auth_type=AUTH_TYPE&pw=SSID_PASSWORD

##### Audio Input: (does not work as of 02.02.00.00)
* None: http://10.5.5.9/gp/gpControl/setting/95/0
* Standard Mic: http://10.5.5.9/gp/gpControl/setting/95/1
* Standard Mic+: http://10.5.5.9/gp/gpControl/setting/95/2
* Powered Mic: http://10.5.5.9/gp/gpControl/setting/95/3
* Powered Mic+: http://10.5.5.9/gp/gpControl/setting/95/4
* Line In: http://10.5.5.9/gp/gpControl/setting/95/5
