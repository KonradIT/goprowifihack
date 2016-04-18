#GoPro Wifi Hack

**The unofficial API for GoPro HERO cameras (The WiFi enabled models)**

*Last updated: 04/18/16 by Konrad Iturbe*


##Choose the camera model:

| [![](https://i.imgur.com/1vwqEIQ.png)](https://github.com/KonradIT/goprowifihack/blob/master/HERO2/README.md) | [![](https://i.imgur.com/9LGo43Z.png)](https://github.com/KonradIT/goprowifihack/blob/master/HERO3/README.md)   |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| [GoPro HERO2 w/ WiFi BacPac](https://github.com/KonradIT/goprowifihack/blob/master/HERO2/README.md)           | [GoPro HERO3/3+ Black, Silver and White](https://github.com/KonradIT/goprowifihack/blob/master/HERO3/README.md) |
| [![](http://i.imgur.com/zpPN0Q2.png?1)](https://github.com/KonradIT/goprowifihack/blob/master/HERO/README.md) | [![](https://i.imgur.com/77h7uHe.jpg)](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/README.md)  |
| [GoPro HERO+ and HERO+ LCD](https://github.com/KonradIT/goprowifihack/blob/master/HERO/README.md)  | [GoPro HERO4 Black, Silver and Session](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/README.md)  |

---

##Read this first:

If you see a URL which contains "PASSWORD" without the quotes, it means it needs the camera password, which you can obtain here:  http://10.5.5.9/camera/sd (may only apply for HERO2/HERO3/HERO3+)

###But, GoPro already has an API!

Yes, but they released it late. This repository exists since November 11, 2013 and has been providing an up to date and free GoPro API for all WiFi Enabled models. This will continue to be the same. GoPro released their closed source and paid API in April 14, 2016. By the time, both companies and hobbyists have been using this API to get their products and services working with GoPro cameras.

This API will be updated as I get access to newly released cameras, if you are a company, I highly recommend to enroll in the GoPro developer program.

###How it works/how it happened

The way GoPro interfaced with their cameras over WiFi has changed a lot since they released the GoPro HERO2 with WiFi BacPac Addon, the first WiFi-enabled camera from GoPro, in 2011/12. Back then there was no official API so users began to research using wireless packet analyzers what was going on between the smartphone GoPro app and the GoPro HERO2, this continued with the HERO3 too. The problem was that if a company/hobbyist wanted to integrate the GoPro camera system into their service/product the information was scarce due to the lack of an official API and getting lost in the pages of forums, also sometimes it was outdated or not compatible with newer models. So I made this repo to recollect some of the HERO2/HERO3 API, and with Wireshark I also completed all the missing commands, updated the API to the newer firmware versions and got access to the newer cameras and documented the API for the new releases, soon it became a central place to get the API and is used by a lot of companies and individuals. In April 2016 GoPro released a subscription based Developer Program which gives access to the official GoPro API. This AI will be the older, free and open source GoPro API where everyone can contribute.

If you got a new camera and its not covered here, [contact me](mailto:mail@chernowii.com), I always try to get the new GoPro cameras but my resources are limited.

The API is divided into cameras which work differently from a API view. To ensure your product/service works with ALL WiFi enabled GoPro cameras make sure to use all the camera folders from the table above. The livestreaming page explains how to get a live feed from the GoPro, the WiFi commands page lists the HTTP-GET URLs to control most aspects of a GoPro camera.
The Camera Status page shows how to get the current parameters of the GoPro such as Photo resolution, battery left...

###Acknowledgements/credits

* Konrad Iturbe - main developer
* dough29 - HERO2 research
* EvilWombat - general and HERO3
* 3v1n0 - HERO4 research
* Maelstrom Napalm - HERO4 research
* fraannk - HERO4 research
* [GitHub contributors](https://github.com/KonradIT/goprowifihack/graphs/contributors)
* and finally GoPro for allowing us to tinker with their cameras and not shutting down this unofficial API like instagram or snapchat, that means a lot.
