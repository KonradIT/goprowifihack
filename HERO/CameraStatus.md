### Camera Status for HERO+ / HERO+ LCD

This URL contains a JSON with the camera parameters: http://10.5.5.9/gp/gpControl/status

Here is a snippet of how the status JSON looks like: (GoPro HERO+, FW 1.50)

```
{"status":{
"1":1,"2":3,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":0,"29":"","30":"goproheroplus","31":0,"32":0,"33":0,"34":8926,"35":9840,"36":0,"37":0,"38":0,"39":0,"40":"%10%0B%13%0B%34%3B","41":0,"42":0,"43":0,"44":3,"45":0,"46":0,"47":0,"48":0,"49":0,"54":32013910016,"55":1,"56":4,"57":0,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0},
"settings": {"1":0,"2":9,"3":5,"4":0,"5":1,"6":2,"7":0,"8":1,"9":0,"10":0,"11":0,"12":0,"13":0,"14":4,"15":0,"16":0,"17":0,"18":0,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"25":0,"26":0,"27":0,"28":0,"29":3,"30":1,"31":0,"32":10,"33":0,"34":0,"35":0,"36":0,"37":0,"38":0,"39":0,"40":0,"41":0,"42":0,"43":0,"44":0,"45":0,"46":0,"47":0,"48":0,"49":100,"50":0,"51":1,"52":1,"53":0,"54":1,"55":3,"56":0,"57":0,"58":0,"59":0,"60":8,"61":1,"62":700000,"63":1,"64":2,"65":0,"66":0,"67":0,"68":3,"69":0,"70":1,"71":0,"72":0}}
```

As you can see, there are two objects, "status" and "settings".
### Status object:

* 1 - Internal Battery is available:
  * 0 = No Battery
  * 1 = Battery is available
* 2 - Internal Battery Level:
  * 3 = Full
  * 2 = Halfway
  * 1 = Low
  * 4 = Charging
* 43 - Current Mode:
  * Video - 0
  * Photo - 1
  * MultiShot - 2
* 44 - Current SubMode
  * 0 = Video/Single Pic/Burst
  * 1 = TimeLapse
  * 3 = Looping
* 13 - Current Recording Video Duration
* 39 - Number of MultiShot pictures taken
* 31 - Number of clients connected to the camera
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

### Settings object:
#### Video Mode based parameters:
* Current SUB-Mode Video - 68:
  * Video - 0
  * Looping - 3

* Video Resolution - 2:
  * 1080 - 9
  * 720 SuperView - 11
  * 720 - 12

* Frame Rate - 3:
  * 60 - 5
  * 50 - 6
  * 30 - 8
  * 25 - 9

* FOV video - 4:
  * Wide - 0

* Looping Video Interval - 6:
  * Max - 0
  * 5 Minutes - 1
  * 20 Minutes - 2
  * 60 Minutes - 3
  * 120 Minutes - 4

* Low Light - 8:			
  * ON - 1
  * OFF - 0

* Spot Meter - 9:			
  * ON - 1
  * OFF - 0

#### Photo Mode based parameters:

* Photo Sub Mode - 69:
    * Single - 0

* Megapixels - 17:
    * 8MP Wide - 0


* Spot Meter - 20:
    * ON - 1
    * OFF - 0

#### MultiShot Mode based parameters:

* Default Multi-Shot Sub Mode - 27:
    * Burst - 0
    * Time Lapse - 1

* Multi-Shot Sub Mode - 70:
    * Burst - 0
    * Time Lapse - 1

* Burst Rate - 29:
    * 10 Photos / 2 Seconds - 3

* TimeLapse Interval - 30:
    * 1 Photo / 0.5 Sec - 0
    * 1 Photo / 1 Sec - 1
    * 1 Photo / 2 Sec - 2
    * 1 Photo / 5 Sec - 5
    * 1 Photo / 10 Sec - 10
    * 1 Photo / 30 Sec - 30
    * 1 Photo / 60 Sec - 60

* Megapixels - 28:
    * 8MP Wide - 0

* Spot Meter - 33:
    * ON - 1
    * OFF - 0

#### Other Settings:

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
  * Back LED - 1
  * Front LED - 2
  * Both LEDs - 3

* Volume for beeps - 56:
  * Mute - 2
  * 70% - 1
  * 100% - 0

* Video Format - 57:
  * NTSC - 0
  * PAL - 1

* LCD Display - 72: (HERO+ LCD)
 * ON - 1
 * OFF - 0
 
* LCD Brightness - 49: (HERO+ LCD)
  * High - 0
  * Medium - 1
  * Low - 2

* LCD Lock - 50: (HERO+ LCD)
  * On - 1
  * Off - 0
  
* LCD Timeout sleep - 51: (HERO+ LCD)
  * Never sleep - 0
  * 1min sleep - 1
  * 2min sleep - 2
  * 3min sleep - 3

