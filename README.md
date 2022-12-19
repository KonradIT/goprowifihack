# GoPro Wifi Hack

**The unofficial API for GoPro cameras (The WiFi enabled models)**

This repository won't be updated regularly, and users are encouraged to switch to [OpenGoPro](https://gopro.github.io/OpenGoPro)

[Read why](https://medium.com/@konrad_it/sunsetting-my-unofficial-gopro-wireless-hacking-effort-a06a03c7fc1c)

## Choose the GoPro:

-   [GoPro HERO2 w/ WiFi BacPac](https://github.com/KonradIT/goprowifihack/blob/master/HERO2/README.md)
-   [GoPro HERO3 (Black/Silver/White) and HERO3+ (Silver/Black)](https://github.com/KonradIT/goprowifihack/blob/master/HERO3/README.md)
-   [GoPro HERO4 (Black/Silver/Session)](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/README.md)
-   [GoPro HERO+ (HERO+/HERO+ LCD) and GoPro HERO (2018)](https://github.com/KonradIT/goprowifihack/blob/master/HERO/README.md)
-   [GoPro HERO5 (Black/Session)](https://github.com/KonradIT/goprowifihack/blob/master/HERO5/README.md)
-   [GoPro HERO6 Black](https://github.com/KonradIT/goprowifihack/blob/master/HERO6/README.md)
-   [GoPro HERO7 (Black/Silver/White)](https://github.com/KonradIT/goprowifihack/blob/master/HERO7/README.md)
-   [GoPro Fusion](https://github.com/KonradIT/goprowifihack/blob/master/Fusion1/README.md)
-   [GoPro MAX](https://github.com/KonradIT/goprowifihack/blob/master/MAX/README.md)
-   [GoPro HERO9](https://github.com/KonradIT/goprowifihack/blob/master/HERO9/README.md)
-   [GoPro HERO10](https://github.com/KonradIT/goprowifihack/blob/master/HERO10/README.md)
-   [GoPro HERO11](https://github.com/KonradIT/goprowifihack/blob/master/HERO11/README.md)

_A note on HERO8:_ For GoPro Connect (Webcam Mode), use Hero9 commands; For other commands, use Hero7 commands.

---

This is a community effort to document the API calls between GoPro cameras and GoPro's Smartphone App via WiFi. It has 4 sections for each camera model:

-   WiFi commands: a list of WiFi commands you can use for the camera.
-   Livestreaming: methods of getting a live video feed off the camera.
-   Media Browsing: Instructions on getting media off the SD card via wifi.
-   Camera Status: List of camera status meanings

Note: HERO4 camera is now the _base_ for the future API, since the calls will be the same for HERO4 and above.

### Does GoPro offer an official API, SDK or mobile library?

They did offer a mobile library - [but they shut it down](https://news.ycombinator.com/item?id=16189633). This repository will continue to be updated until GoPro stops releasing cameras and ceases operations.

But... Now they offer BLE/WiFi API documentation, tutorials and examples over at [OpenGoPro](https://gopro.com/OpenGoPro).

## This vs OpenGoPro

This is an effort to document the **mobile app APIs** used by GoPro, internally called gpControl APIs or Smarty APIs. OpenGoPro V2 supports all commands over WiFi and USB, making this effort largely useless these days. Fortunately they've kept the BLE part 100% identical to what we documented over here.

This repository will just be updated to cover the gpControl APIs, if they change at all between future cameras, which might reveal new features and/or support endpoints not covered by OpenGoPro. Users are encouraged to switch to the OpenGoPro spec.

OpenGoPro supports Hero9 Black, Hero10 and Hero11 (at least officially - their BLE commands are compatible with older BLE-enabled cams given the proper characteristic). This repository covers nearly a decade of GoPro camera releases.

This repository will get updates only if the gpControl API is kept available, if the GoPro App ceases to use gpControl and switches to OpenGoPro, what's the point?

### Libraries:

[3rd Party Library/API wrappers list](https://github.com/KonradIT/goprowifihack/blob/master/Libraries.md)

### Bluetooth:

Bluetooth is used to turn camera on after WiFi AP is disabled in deep sleep, as well as for turning on/off wifi.

But on Hero9, it's used for status retrieval, all commands and changing settings, turning on,

### Acknowledgements/credits

-   Konrad Iturbe - main developer
-   dough29 - HERO2 research
-   EvilWombat - general and HERO3
-   3v1n0 - HERO4 research
-   Maelstrom Napalm - HERO4 research
-   fraannk - HERO4 research
-   Sonof8Bits - Python script
-   krystof-k - Bluetooth API and wake up commands
-   [Mark Kirschenbaum](https://gethypoxic.com/blogs/technical/gopro-hero5-interfaces) - Bluetooth commands info
-   [GitHub contributors](https://github.com/KonradIT/goprowifihack/graphs/contributors)
-   and finally GoPro for allowing us to tinker with their cameras and not shutting down this unofficial API like instagram or snapchat, that means a lot.
