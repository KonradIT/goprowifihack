### Camera Status for HERO4

This URL contains a JSON with the camera parameters: http://10.5.5.9/gp/gpControl/status

Here is a snippet of how the status JSON looks like: (GoPro HERO4 Black, FW 5.00)

```
{"status":{
"1":1,"2":2,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":2,"29":"","30":"KonradHERO4Black","31":0,"32":0,"33":0,"34":4778,"35":7523,"36":432,"37":114,"38":5298,"39":114,"40":"%10%08%13%17%13%01","41":0,"42":0,"43":0,"44":0,"45":0,"46":0,"47":0,"48":1,"49":0,"54":31798784,"55":1,"56":4,"57":932443,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0,"65":0,"66":0,"67":0},
"settings":{"1":0,"2":9,"3":8,"4":0,"5":0,"6":1,"7":1,"8":1,"9":0,"10":0,"11":0,"12":0,"13":1,"14":0,"15":4,"16":0,"17":0,"18":0,"19":0,"20":0,"21":1,"22":7,"23":0,"24":0,"25":0,"26":4,"27":0,"28":0,"29":5,"30":0,"31":0,"32":0,"33":0,"34":0,"35":0,"36":0,"37":0,"38":0,"39":4,"49":0,"50":1,"51":1,"52":0,"53":0,"54":1,"55":2,"56":0,"57":0,"58":1,"59":1,"60":8,"61":1,"62":700000,"63":1,"64":1,"68":0,"69":0,"70":0,"72":1,"73":0,"74":1,"75":2,"76":3,"77":0,"78":0,"79":1,"80":1,"81":0,"82":0}}
```

As you can see, there are two objects, "status" and "settings".
## HERO4 BLACK/SILVER:
### Status object:

* 1 - Internal Battery is available:
  * 0 = No Battery
  * 1 = Battery is available
* 2 - Internal Battery Level:
  * 4 = Charging
  * 3 = Full
  * 2 = Halfway
  * 1 = Low
  * 0 = Empty
* 43 - Current Mode:
  * Video - 0
  * Photo - 1
  * MultiShot - 2
* 44 - Current SubMode
  * 0 = Video/Single Pic/Burst
  * 1 = TL Video/Continuous/TimeLapse
  * 2 = Video+Photo/NightPhoto/NightLapse
* 13 - Current Recording Video Duration
* 39 - Number of MultiShot pictures taken
* 31 - Number of clients connected to the camera [reference from HERO4 Session doc]
* 32 - Streaming feed status:
  * 0 = Not Streaming
  * 1 = Streaming
* 33 - SD card inserted:
  * 0 = SD card inserted
  * 2 = No SD Card present
* 34 - Remaining Photos
* 35 - Remaining Video Time
* 36 - Number of Batch Photos taken (Example: TimeLapse batches, burst batches, continouous photo batches...)
* 37 - Number of videos shot
* 38 - Number of ALL photos taken
* 39 - Number of ALL videos taken
* 8 = Recording/Processing status:
  * 0 = Not recording/Processing
  * 1 = Recording/processing
* 54 - Remaning free space on memorycard in bytes

### Settings object:
#### Video Mode based parameters:
* Current SUB-Mode Video - 68:
  * Video - 0
  * TimeLapse Video - 1
  * Video+Photo - 2
  * Looping - 3

* Video Resolution - 2:
  * 4K SuperView - 2
  * 4K - 1
  * 2.7K SuperView - 5
  * 2.7K - 4
  * 2.7K 4:3 - 6
  * 1440 - 7
  * 1080 SuperView - 8
  * 1080 - 9
  * 960 - 10
  * 720 SuperView - 11
  * 720 - 12
  * WVGA - 13

* Frame Rate - 3:
  * 240 - 0
  * 120 - 1
  * 100 - 2
  * 90 - 3
  * 80 - 4
  * 60 - 5
  * 50 - 6
  * 48 - 7
  * 30 - 8
  * 25 - 9
  * 24 - 10
  * 15 - 11
  * 12.5 - 12

* FOV video - 4:
  * Wide - 0
  * Medium - 1
  * Narrow - 2
  * Linear - 4

* TimeLapse Video Interval - 5:
  * 1/2 Seconds - 0
  * 1 Second - 1
  * 2 Seconds - 2
  * 5 Seconds - 3
  * 10 Seconds - 4
  * 30 Seconds - 5
  * 60 Seconds - 6

* Looping Video Interval - 6:
  * Max - 0
  * 5 Minutes - 1
  * 20 Minutes - 2
  * 60 Minutes - 3
  * 120 Minutes - 4

* Photo+Video Interval - 7:
  * 1 Photo / 5 Seconds - 1
  * 1 Photo / 10 Seconds - 2
  * 1 Photo / 30 Seconds - 3
  * 1 Photo / 60 Seconds - 4

* Low Light - 8:			
  * ON - 1
  * OFF - 0

* Spot Meter - 9:			
  * ON - 1
  * OFF - 0

* Protune - 10:
  * ON - 1
  * OFF - 0

* White Balance - 11:			
    * Auto - 0
    * 3000K - 1
    * 4000K - 5
	* 4800K - 6
    * 5500K - 2
	* 6000K - 7
    * 6500K - 3
    * Native - 4

* Color - 12:			
    * GoPro Color - 0
    * Flat - 1

* Manual Exposure (v4.00FW) - 73:
	* 1/24 - 3
	* 1/25 - 4
	* 1/30 - 5
	* 1/48 - 6
	* 1/50 - 7
	* 1/60 - 8
	* 1/80 - 9
	* 1/90 - 10
	* 1/96 - 11
	* 1/100 - 12
	* 1/120 - 13
	* 1/160 - 14
	* 1/180 - 15
	* 1/192 - 16
	* 1/200 - 17
	* 1/240 - 18
	* 1/320 - 19
	* 1/360 - 20
	* 1/400 - 21
	* 1/480 - 22
	* 1/960 - 23

* ISO Mode (v4.00FW) - 74:
	* Max - 0
	* Lock - 1

* ISO Limit - 13:			
    * 6400 - 0
    * 1600 - 1
    * 400 - 2
    * 3200 - 3
    * 800 - 4
    * 200 - 7
    * 100 - 8

* Sharpness - 14:		
    * High - 0
    * Medium - 1
    * Low - 2
    * ON (HERO4 Session) - 3
    * OFF (HERO4 Session) - 4

* EV Comp - 15:		
    * -2.0 - 8
    * -1.5 - 7
    * -1.0 - 6
    * -0.5 - 5
    * 0.0 - 4
    * 0.5 - 3
    * 1.0 - 2
    * 1.5 - 1
    * 2.0 - 0

#### Photo Mode based parameters:

* Photo Sub Mode - 69:
    * Single - 0
    * Continuous - 1
    * Night - 2

* Continuous Rate - 18:
    * 3 Frames / Second - 0
    * 5 Frames / Second - 1
    * 10 Frames / Second - 2

* Megapixels - 17:
    * 12MP Wide - 0
    * 7MP Wide - 1
    * 7MP Med - 2
    * 5MP Med - 3

* Shutter - 19:
    * Auto - 0
    * 2 Seconds - 1
    * 5 Seconds - 2
    * 10 Seconds - 3
    * 15 Seconds - 4
    * 20 Seconds - 5
    * 30 Seconds - 6

* Spot Meter - 20:
    * ON - 1
    * OFF - 0

* Protune - 21:
    * ON - 1
    * OFF - 0

* White Balance - 22:
    * Auto - 0
    * 3000K - 1
	* 4000K - 5
	* 4800K - 6
    * 5500K - 2
	* 6000K - 7
    * 6500K - 3
    * Native - 4

* Color - 23:
    * GoPro Color - 0
    * Flat - 1

* Sharpness - 25:
    * High - 0
    * Medium - 1
    * Low - 2

* EV Comp - 26:
    * -2.0 - 8
    * -1.5 - 7
    * -1.0 - 6
    * -0.5 - 5
    * 0.0 - 4
    * 0.5 - 3
    * 1.0 - 2
    * 1.5 - 1
    * 2.0 - 0

* ISO Min (4.00FW) - 75:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

* ISO Limit (ISO Max in 4.00FW) - 24:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

#### MultiShot Mode based parameters:

* Default Multi-Shot Sub Mode - 27:
    * Burst - 0
    * Time Lapse - 1
    * Night Lapse - 2

* Multi-Shot Sub Mode - 70:
    * Burst - 0
    * Time Lapse - 1
    * Night Lapse - 2

* NightLapse/NightPhoto Shutter Exposure - 31:
    * Auto - 0
    * 2 Seconds - 1
    * 5 Seconds - 2
    * 10 Seconds - 3
    * 15 Seconds - 4
    * 20 Seconds - 5
    * 30 Seconds - 6

* Burst Rate - 29:
    * 3 Photos / 1 Second - 0
    * 5 Photos / 1 Second - 1
    * 10 Photos / 1 Second - 2
    * 10 Photos / 2 Seconds - 3
    * 10 Photos / 3 Seconds - 4
    * 30 Photos / 1 Second - 5
    * 30 Photos / 2 Seconds - 6
    * 30 Photos / 3 Seconds - 7
    * 30 Photos / 6 Seconds - 8

* TimeLapse Interval - 30:
    * 1 Photo / 0.5 Sec - 0
    * 1 Photo / 1 Sec - 1
    * 1 Photo / 2 Sec - 2
    * 1 Photo / 5 Sec - 5
    * 1 Photo / 10 Sec - 10
    * 1 Photo / 30 Sec - 30
    * 1 Photo / 60 Sec - 60

* NightLapse Interval - 32:
    * Continuous - 0
    * 4 Seconds - 4
    * 5 Seconds - 5
    * 10 Seconds - 10
    * 15 Seconds - 15
    * 20 Seconds - 20
    * 30 Seconds - 30
    * 1 Minute - 60
    * 2 Minutes - 120
    * 5 Minutes - 300
    * 30 Minutes - 1800
    * 60 Minutes - 3600

* Megapixels - 28:
    * 12MP Wide - 0
    * 7MP Wide - 1
    * 7MP Med - 2
    * 5MP Med - 3

* Spot Meter - 33:
    * ON - 1
    * OFF - 0

* Protune - 34:
    * ON - 1
    * OFF - 0

* White Balance - 35:
    * Auto - 0
    * 3000K - 1
	* 4000K - 5
	* 4800K - 6
    * 5500K - 2
	* 6000K - 7
    * 6500K - 3
    * Native - 4

* Color - 36:
    * GoPro Color - 0
    * Flat - 1

* Sharpness - 38:
    * High - 0
    * Medium - 1
    * Low - 2

* EV Comp - 39:
    * -2.0 - 8
    * -1.5 - 7
    * -1.0 - 6
    * -0.5 - 5
    * 0.0 - 4
    * 0.5 - 3
    * 1.0 - 2
    * 1.5 - 1
    * 2.0 - 0

* ISO Min (4.00FW) - 76:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

* ISO Limit (ISO Max in 4.00FW) - 37:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

#### Other Settings:
* LCD Display - 72:
 * ON - 1
 * OFF - 0

* Orientation - 52:
  * Auto - 0
  * UP - 1
  * DOWN - 2

* Default Boot Mode - 53:
  * Video - 0
  * Photo - 1
  * MultiShot - 2

* Quick Capture - 54:
  * OFF - 0
  * ON - 1

* LED status - 55:
  * OFF - 0
  * 2 LEDs (H4 Black/Silver) FULL LEDs (HERO4 Session) - 1
  * 4 LEDs (H4 Black/Silver)- 2

* Volume for beeps - 56:
  * Mute - 2
  * 70% - 1
  * 100% - 0

* Video Format - 57:
  * NTSC - 0
  * PAL - 1

* On Screen data (HDMI/LCD BacPac/LCD) - 58:
  * ON - 1
  * OFF - 0

* LCD Brightness - 49:
  * High - 0
  * Medium - 1
  * Low - 2

* LCD Lock - 50:
  * On - 1
  * Off - 0
* LCD Timeout sleep - 51:
  * Never sleep - 0
  * 1min sleep - 1
  * 2min sleep - 2
  * 3min sleep - 3

* Auto Power Off - 59:
  * Never - 0
  * 1 min - 1
  * 2 mins - 2
  * 3 mins - 3
  * 5 mins - 4
