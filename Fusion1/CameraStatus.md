### Camera Status for Fusion

This URL contains a JSON with the camera parameters: http://10.5.5.9/gp/gpControl/status

Here is a snippet of how the status JSON looks like: (GoPro Fusion 1)

```
{"status":{
"1":1,"2":3,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"13":0,"17":1,"19":4,"20":1,"21":39725,"22":0,"23":0,"24":0,"26":0,"27":0,"28":82,"29":"","30":"GP24503410","31":0,"32":0,"33":0,"34":5572,"35":3262,"36":14,"37":3,"38":14,"39":3,"40":"%11%0C%1D%17%10%0D","41":0,"42":0,"43":0,"44":0,"45":0,"46":0,"47":0,"48":0,"49":0,"54":28777664,"55":1,"56":4,"57":578901,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0,"65":0,"66":0,"67":0,"68":0,"69":1,"70":93,"71":12,"72":16,"73":21,"74":0,"76":0,"80":0,"81":1,"82":1},
"settings":{"1":0,"2":14,"3":9,"5":0,"10":1,"13":2,"15":4,"16":0,"17":12,"19":1,"21":1,"24":1,"26":8,"27":0,"28":12,"29":0,"30":0,"31":0,"32":3601,"34":1,"37":0,"39":4,"54":0,"57":1,"60":8,"61":1,"62":2500000,"64":10,"68":0,"69":0,"70":2,"74":0,"82":1,"83":0,"84":0,"85":0,"86":0,"87":0,"88":100,"91":2,"92":12,"95":0}}
```

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
  * 3K - 15
  * 5.2K - 14

* Frames Per Second - 3:
    * 60 - 5
    * 50 - 6
    * 30 - 8
    * 25 - 9

* Interval - 5:
    * 0.5 Seconds - 0
    * 1 Second - 1
    * 2 Seconds - 2
    * 5 Seconds - 3
    * 10 Seconds - 4
    * 30 Seconds - 5
    * 60 Seconds - 6

* Protune - 10:
    * ON - 1
    * OFF - 0

* ISO Mode - 74:
    * Max - 0
    * Lock - 1

* ISO Limit - 13:
    * 6400 - 0
    * 1600 - 1
    * 400 - 2

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
    * Night - 2

* Megapixels - 17: 
    * 18MP - 12

* Shutter - 19: 
    * Auto - 0
    * 30 Seconds - 6
    * 20 Seconds - 5
    * 15 Seconds - 4
    * 10 Seconds - 3
    * 5 Seconds - 2
    * 2 Seconds - 1

* Protune - 21: 
    * ON - 1
    * OFF - 0

* ISO Limit - 24: 
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

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

* RAW - 82: 
    * ON - 1
    * OFF - 0


#### MultiShot Mode based parameters:

* Multi-Shot Sub Mode - 70:

    * Time Lapse Photo - 1
    * Night Lapse - 2
    * Burst - 0

* Shutter - 31:

    * Auto - 0
    * 2 Seconds - 1
    * 5 Seconds - 2
    * 10 Seconds - 3
    * 15 Seconds - 4
    * 20 Seconds - 5
    * 30 Seconds - 6

* Rate - 29:

    * 30 Photos / 6 Seconds - 8
    * 30 Photos / 3 Seconds - 7
    * 30 Photos / 2 Seconds - 6
    * 30 Photos / 1 Second - 5
    * 10 Photos / 3 Seconds - 4
    * 10 Photos / 2 Seconds - 3
    * 10 Photos / 1 Second - 2
    * 5 Photos / 1 Second - 1
    * 3 Photos / 1 Second - 0

* Interval - 30:

    * 1 Photo / 0.5 Sec - 0
    * 1 Photo / 1 Sec - 1
    * 1 Photo / 2 Sec - 2
    * 1 Photo / 5 Sec - 5
    * 1 Photo / 10 Sec - 10
    * 1 Photo / 30 Sec - 30
    * 1 Photo / 60 Sec - 60

* Interval - 32:

    * Auto - 3601
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

    * 18MP - 12

* Protune - 34:

    * ON - 1
    * OFF - 0

* ISO Limit - 37:

    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

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

* ISO Limit - 37:

    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

#### Other Settings:


* Quick Capture - 54:
  * OFF - 0
  * ON - 1

* LED status - 91:
  * OFF - 0
  * LEDs on - 2

* Volume for beeps - 56:
  * Mute - 2
  * 70% - 1
  * 100% - 0

* GPS - 83:
  * ON- 1
  * OFF - 0

* Video Format - 57:
  * NTSC - 0
  * PAL - 1