#GoPro Wifi Hack

**The unofficial API for GoPro HERO cameras (The WiFi enabled models)**

*Last updated: 03/12/15 by Konrad Iturbe*


##Index

* **[Live streaming](https://github.com/KonradIT/goprowifihack#livestreaming)**
	* [GoPro HERO2/HERO3/HERO3+/HERO+](https://github.com/KonradIT/goprowifihack#liveprehero4)
	* [GoPro HERO4](https://github.com/KonradIT/goprowifihack#livehero4)
* **[HTTP Commands](https://github.com/KonradIT/goprowifihack#httpcommands)**
	* [GoPro HERO2/HERO3/HERO3+](https://github.com/KonradIT/goprowifihack#commandsprehero4)
	* [GoPro HERO4](https://github.com/KonradIT/goprowifihack#commandshero4)
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