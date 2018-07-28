### GoPro HERO5 Commands, Status and Notes

## Specific commands, for the rest of the commands go [here](/HERO4/WifiCommands.md)

Firmware revision: HD5.02.02.00.00

Sample /status

```
{"status":{
"1":1,"2":3,"3":0,"4":0,"6":0,"8":0,"9":0,"10":0,"11":0,"13":0,"14":0,"15":0,"16":0,"17":1,"19":0,"20":0,"21":0,"22":0,"23":0,"24":0,"26":0,"27":0,"28":86,"29":"","30":"GP24784461","31":0,"32":0,"33":0,"34":4155,"35":6542,"36":3,"37":4,"38":3,"39":4,"40":"%11%02%12%12%38%3A","41":0,"42":0,"43":0,"44":0,"45":0,"46":1,"47":1,"48":1,"49":0,"54":27655117,"55":1,"56":4,"57":146925,"58":0,"59":0,"60":500,"61":2,"62":0,"63":0,"64":0,"65":0,"66":0,"67":0,"68":0,"69":1,"70":84,"71":12,"72":16,"73":13},
"settings":{"1":0,"2":9,"3":8,"4":4,"5":0,"6":1,"7":1,"8":1,"9":0,"10":0,"11":0,"12":0,"13":1,"14":0,"15":4,"16":0,"17":10,"18":4,"19":0,"20":0,"21":1,"22":0,"23":0,"24":4,"25":0,"26":4,"27":0,"28":10,"29":5,"30":0,"31":0,"32":3601,"33":0,"34":0,"35":0,"36":0,"37":4,"38":0,"39":4,"50":0,"51":1,"52":0,"54":1,"57":0,"58":1,"59":6,"60":8,"61":1,"62":2500000,"63":7,"64":4,"68":0,"69":1,"70":0,"72":1,"73":0,"74":0,"75":3,"76":3,"77":0,"78":0,"79":0,"80":2,"81":3,"82":0,"83":1,"84":0,"85":0,"86":1,"87":40,"88":100,"89":12,"91":2}}
```
#### Commands:

##### EIS (Video Stabilisation):
* On: http://10.5.5.9/gp/gpControl/setting/78/1
* Off: http://10.5.5.9/gp/gpControl/setting/78/0

##### RAW (.GPR RAW PHOTO)

###### Photo (Photo Mode)
* On: http://10.5.5.9/gp/gpControl/setting/82/1
* Off: http://10.5.5.9/gp/gpControl/setting/82/0

###### NightPhoto (Photo Mode)
* On: http://10.5.5.9/gp/gpControl/setting/98/1
* Off: http://10.5.5.9/gp/gpControl/setting/98/0

###### TimeLapse (MultiShot Mode):
* On: http://10.5.5.9/gp/gpControl/setting/94/1
* Off: http://10.5.5.9/gp/gpControl/setting/94/0

###### NightLapse (MultiShot Mode):
* On: http://10.5.5.9/gp/gpControl/setting/99/1
* Off: http://10.5.5.9/gp/gpControl/setting/99/0

##### WDR (Wide Dynamic Range):

###### Photo (Photo Mode):

* On: http://10.5.5.9/gp/gpControl/setting/77/1
* Off: http://10.5.5.9/gp/gpControl/setting/77/0

###### TimeLapse (MultiShot Mode):

* On: http://10.5.5.9/gp/gpControl/setting/93/1
* Off: http://10.5.5.9/gp/gpControl/setting/93/0

##### Protune Shutter for Photo Mode:

* Auto: http://10.5.5.9/gp/gpControl/setting/97/0
* 1/125: http://10.5.5.9/gp/gpControl/setting/97/1
* 1/250: http://10.5.5.9/gp/gpControl/setting/97/2
* 1/500: http://10.5.5.9/gp/gpControl/setting/97/3
* 1/1000: http://10.5.5.9/gp/gpControl/setting/97/4
* 1/2000: http://10.5.5.9/gp/gpControl/setting/97/5

##### Audio on Video:

* On: http://10.5.5.9/gp/gpControl/setting/96/1
* Off: http://10.5.5.9/gp/gpControl/setting/96/0

##### Audio mode:
* Stereo only: http://10.5.5.9/gp/gpControl/setting/80/0
* Wind only: http://10.5.5.9/gp/gpControl/setting/80/1
* Auto: http://10.5.5.9/gp/gpControl/setting/80/2

##### Audio ProTune:
* On: http://10.5.5.9/gp/gpControl/setting/79/0
* Off: http://10.5.5.9/gp/gpControl/setting/79/1

##### Raw Audio mode:
* Low: http://10.5.5.9/gp/gpControl/setting/81/0
* Mid: http://10.5.5.9/gp/gpControl/setting/81/1
* High: http://10.5.5.9/gp/gpControl/setting/81/2
* Off: http://10.5.5.9/gp/gpControl/setting/81/3

##### FOV
* SuperView: http://10.5.5.9/gp/gpControl/4/3
* Linear: http://10.5.5.9/gp/gpControl/setting/4/4

##### Photo setting:
* 12MP Wide: http://10.5.5.9/gp/gpControl/setting/17/0
* 12MP Linear: http://10.5.5.9/gp/gpControl/setting/17/10
* 12MP Medium: http://10.5.5.9/gp/gpControl/setting/17/8
* 12MP Narrow: http://10.5.5.9/gp/gpControl/setting/17/9

##### GPS Tag:

* On: http://10.5.5.9/gp/gpControl/setting/83/1
* Off: http://10.5.5.9/gp/gpControl/setting/83/0

##### Voice control:

* On: http://10.5.5.9/gp/gpControl/setting/86/1
* Off: http://10.5.5.9/gp/gpControl/setting/86/0

##### LEDs on HERO5 Black:

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

##### Streaming settings:

###### Bit rate:

* 2.5 Mbps: http://10.5.5.9/gp/gpControl/setting/62/2500000
* 4 Mbps: http://10.5.5.9/gp/gpControl/setting/62/4000000

##### Resolution:

* 720: http://10.5.5.9/gp/gpControl/setting/64/7
* 720 3:4 Subsample: http://10.5.5.9/gp/gpControl/setting/64/8
* 720 1:2 Subsample: http://10.5.5.9/gp/gpControl/setting/64/9

#### Pairing:

For Hero 5 Black/Session:

Initiate pairing in Connections > New > GoPro App

http://10.5.5.9/gp/gpControl/command/wireless/pair/complete?success=1&deviceName=DESKTOP

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
