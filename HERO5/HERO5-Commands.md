###GoPro HERO5 Commands, Status and Notes

Firmware revision: HD5.02.01.50.00

Sample /status

```
{"status":{
"1":1,"2":4,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":18,"29":"","30":"GP24784461","31":2,"32":1,"33":0,"34":8899,"35":14012,"36":1,"37":8,"38":1,"39":8,"40":"%10%0A%16%10%12%16","41":0,"42":0,"43":0,"44":0,"45":0,"46":0,"47":1,"48":1,"49":0,"54":59225568,"55":1,"56":4,"57":668476,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0,"65":0,"66":0,"67":0,"68":1,"69":0,"70":54,"71":12,"72":17,"73":13},
"settings":{"1":0,"2":9,"3":5,"4":4,"5":0,"6":1,"7":1,"8":1,"9":0,"10":0,"11":0,"12":0,"13":1,"14":0,"15":4,"16":0,"17":0,"18":4,"19":0,"20":0,"21":0,"22":0,"23":0,"24":4,"25":0,"26":4,"27":0,"28":0,"29":5,"30":0,"31":0,"32":3601,"33":0,"34":0,"35":0,"36":0,"37":4,"38":0,"39":4,"50":0,"51":1,"52":0,"54":1,"57":0,"58":1,"59":4,"60":8,"61":1,"62":2500000,"63":7,"64":4,"68":0,"69":1,"70":0,"72":1,"73":0,"74":0,"75":3,"76":3,"77":0,"78":1,"79":1,"80":2,"81":2,"82":0,"83":1,"84":0,"85":6,"86":1,"87":100,"88":100,"89":12,"91":2}}
```
####Commands:

#####EIS (Video Stabilisation):
* On: http://10.5.5.9/gp/gpControl/setting/78/1
* Off: http://10.5.5.9/gp/gpControl/setting/78/0

#####RAW Image (Photo mode only)
* On: http://10.5.5.9/gp/gpControl/setting/82/1
* Off: http://10.5.5.9/gp/gpControl/setting/82/0

#####WDR Image (Wide Dynamic Range, photo mode only):
* On: http://10.5.5.9/gp/gpControl/setting/77/1
* Off: http://10.5.5.9/gp/gpControl/setting/77/0

#####Audio mode:
* Stereo only: http://10.5.5.9/gp/gpControl/setting/80/0
* Wind only: http://10.5.5.9/gp/gpControl/setting/80/1
* Auto: http://10.5.5.9/gp/gpControl/setting/80/2

#####Audio ProTune:
* On: http://10.5.5.9/gp/gpControl/setting/79/0
* Off: http://10.5.5.9/gp/gpControl/setting/79/1

#####Raw Audio mode:
* Low: http://10.5.5.9/gp/gpControl/setting/81/0
* Mid: http://10.5.5.9/gp/gpControl/setting/81/1
* High: http://10.5.5.9/gp/gpControl/setting/81/2
* Off: http://10.5.5.9/gp/gpControl/setting/81/3

#####FOV
* SuperView: http://10.5.5.9/gp/gpControl/4/3
* Linear: http://10.5.5.9/gp/gpControl/setting/4/4

#####Photo setting:
* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 12MP Linear: http://10.5.5.9/gp/gpControl/setting/17/10
* 12MP Medium: http://10.5.5.9/gp/gpControl/setting/17/8
* 12MP Narrow: http://10.5.5.9/gp/gpControl/setting/17/9

#####GPS Tag:

* On: http://10.5.5.9/gp/gpControl/setting/83/1
* Off: http://10.5.5.9/gp/gpControl/setting/83/0

#####Voice control:

* On: http://10.5.5.9/gp/gpControl/setting/86/1
* Off: http://10.5.5.9/gp/gpControl/setting/86/0

#####LEDs on HERO5 Black:

* Off: http://10.5.5.9/gp/gpControl/setting/91/0
* On: http://10.5.5.9/gp/gpControl/setting/91/2
* Front off: http://10.5.5.9/gp/gpControl/setting/91/1

#####Camera system language:


* English: http://10.5.5.9/gp/gpControl/setting/84/0
* Chinese: http://10.5.5.9/gp/gpControl/setting/84/1
* German: http://10.5.5.9/gp/gpControl/setting/84/2
* Italian: http://10.5.5.9/gp/gpControl/setting/84/3
* Spanish: http://10.5.5.9/gp/gpControl/setting/84/4
* Japanese: http://10.5.5.9/gp/gpControl/setting/84/5
* French: http://10.5.5.9/gp/gpControl/setting/84/6

#####Voice control language:


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
