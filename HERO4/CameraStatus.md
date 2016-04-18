###Camera Status for HERO4

This URL contains a JSON with the camera parameters: http://10.5.5.9/gp/gpContrl/status

Here is a snippet of how the status JSON looks like: (GoPro HERO4 Black, FW 3.00)

```
{"status":{
"1":1,"2":2,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":2,"29":"","30":"GoProHERO4Black","31":0,"32":0,"33":0,"34":750,"35":664,"36":11,"37":9,"38":1100,"39":9,"40":"%10%04%12%0D%0A%0B","41":0,"42":0,"43":0,"44":0,"45":0,"46":0,"47":0,"48":0,"49":0,"54":2806912,"55":1,"56":4,"57":105870,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0},
"settings":{"1":0,"2":9,"3":8,"4":1,"5":0,"6":1,"7":1,"8":1,"9":0,"10":0,"11":0,"12":0,"13":4,"14":0,"15":4,"16":0,"17":1,"18":2,"19":5,"20":0,"21":1,"22":2,"23":0,"24":1,"25":0,"26":4,"27":0,"28":1,"29":6,"30":2,"31":5,"32":0,"33":0,"34":1,"35":2,"36":0,"37":0,"38":0,"39":5,"40":0,"41":13,"42":8,"43":0,"44":8,"45":8,"46":0,"47":0,"48":0,"49":0,"50":1,"51":3,"52":0,"53":0,"54":1,"55":0,"56":2,"57":0,"58":1,"59":1,"60":8,"61":1,"62":700000,"63":1,"64":1,"65":0,"66":0,"67":0,"68":0,"69":0,"70":1,"71":0,"72":1}}
```

As you can see, there are two objects, "status" and "settings".
##HERO4 BLACK/SILVER:
###Status object:

* 43 - Current Mode.
  * 0 = Video Mode
  * 1 = Photo mode
  * 3 = MultiShot mode

###Settings object:
####Video Mode based parameters:
* 68 - Current SUB-Mode Video.
  * Video - 0
  * TimeLapse Video - 1
  * Video+Photo -2
  * Looping -3
* 2 - Video Resolution:
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
* 3 - Frame Rate:
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
* 4 - FOV video:
  * Wide - 2
  * Medium - 1
  * Narrow - 2
* 5 - TimeLapse Video Interval:
  * 1/2 Seconds - 0
  * 1 Second - 1
  * 2 Seconds - 2
  * 5 Seconds - 3
  * 10 Seconds - 4
  * 30 Seconds - 5
  * 60 Seconds - 6
* 6 - Looping Video Interval:
  * Max - 0
  * 5 Minutes - 1
  * 20 Minutes - 2
  * 60 Minutes - 3
  * 120 Minutes - 4

* 7 - Photo+Vide Interval			
  * 1 Photo / 5 Seconds - 1
  * 1 Photo / 10 Seconds - 2
  * 1 Photo / 30 Seconds - 3
  * 1 Photo / 60 Seconds - 4

* 8 - Low Light			
  * ON - 1
  * OFF - 0

* 9 - Spot Meter			
  * ON - 1
  * OFF - 0

* 10 - Protune			
  * ON - 1
  * OFF - 0

* 11 - White Balance			
    * Auto - 0
    * 3000K - 1
    * 5500K - 2
    * 6500K - 3
    * Native - 4

* 12 - Color			
    * GoPro Color - 0
    * Flat - 1

* 13 - ISO Limit			
    * 6400 - 0
    * 1600 - 1
    * 400 - 2
    * 3200 - 3
    * 800 - 4

* 14 - Sharpness			
    * High - 0
    * Medium - 1
    * Low - 2

* 15 - EV Comp			
    * -2.0 - 8
    * -1.5 - 7
    * -1.0 - 6
    * -0.5 - 5
    * 0.0 - 4
    * 0.5 - 3
    * 1.0 - 2
    * 1.5 - 1
    * 2.0 - 0

####Photo Mode based parameters:

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
    * 5500K - 2
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

* ISO Limit - 24:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3
####MultiShot Mode based parameters:

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
    * 5500K - 2
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

* ISO Limit - 37:
    * 800 - 0
    * 400 - 1
    * 200 - 2
    * 100 - 3

####Other Settings:
