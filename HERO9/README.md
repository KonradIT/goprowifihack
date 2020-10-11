## GoPro HERO9

Cameras covered: HERO9 Black

### First, a preface:

This camera does not implement all the requests that GoPro usually baked into the firmware. Shutter start works, shutter stop does not. But media download (`/gp/gpMediaList` and `:8080/videos/DCIM`) works, `/gp/gpControl/status` works, preview works (!!! it's super finnicky on mine). Open a champagne bottle for the old method, new cams use Bluetooth LE for control as it should've been since the Hero5. I'll catch a lot of flack for saying this probably but WiFi drains the battery, it's a one-to-one system, and for command calls it does not make any sense. GoPro also enabled gpControl over USB on the Hero8 and the Hero9 will have it as well! This repository have all the new cool BLE stuff, which will likely be on [Bluetooth/*](/Bluetooth) and [gopro-ble-py](http://github.com/konradit/gopro-ble-py) for code examples. Most cheap SBCs and microcontrollers can run a simple BLE stack (buy a RPI Zero for controlling GoPros, you won't regret it). 

* [Live Streaming](/HERO9/Livestreaming.md)
* [Media Browsing](/HERO9/Mediabrowsing.md)
* [Camera Status](/HERO9/CameraStatus.md)
* [Wifi Commands](/HERO9/HERO9-Commands.md)
* [GoPro Connect (Webcam mode)](/HERO9/GoPro-Connect.md)
* [Framerates/Resolution compatibility table for HERO9](/HERO9/Framerates-Resolutions.md)
