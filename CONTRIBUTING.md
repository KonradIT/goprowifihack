## Contributing to goprowifihack;

Thank you for wanting to contribute to this project, please read the brief rules and guidelines:

### Issues:

Something from here does not work/has changed? Have a suggestion or problem? Post an issue.
* Please search if your issue has been already posted ([solved issues](https://github.com/KonradIT/goprowifihack/issues?q=is%3Aclosed+is%3Aissue) | [currently active issues](https://github.com/KonradIT/goprowifihack/issues?q=is%3Aissue+is%3Aclosed))
* When filing an issue, please submit a descriptive title and fill the prewritten assignments. Example issue:
  * Do:
    * TITLE: Shutter command does not work with GoPro HERO5 Session on new firmware update
    * Body: 
        ```
        Problem: The HERO5 Session does not respond to the shutter command (/shutter?p=1) with the new firmware 
        (firmware version here).
        Details: HTTP GET ERROR
        GoPro Camera: GoPro HERO5 Session
        Firmware: XXX
        Steps to reproduce: call /shutter?p=1 with curl
        happens every time: Y
        ...
        ```
  * Don't:
    * TITLE: HERO5
    * body: something does not work
* When submitting a /gp/gpControl snippet (I may ask you to submit this text to help me debug) please delete the fields serial_number and ap_mac. [Example here](https://github.com/KonradIT/goprowifihack/blob/master/HERO5/gpControl-HERO5Black.json#L19960)
* Make sure you test and re test everything. Some stuff might work at the second try.

### Pull Requests:

* If you're contributing to a api document, please adhere to the text layout.
* If you're submitting a gpControl.json remove the ap_mac and serial_number fields.

### Documenting a new camera/feature:

I don't always get the newest cameras when they are launched, if you have a GoPro camera that is not covered by this API and you want to add support to it follow these steps:

* First check if the existing commands work, use the [base API](/HERO4/) to check if the camera reacts to the commands.
  * If it does:
    * In your browser, navigate to http://10.5.5.9/gp/gpControl and copy the text, paste it into pastebin.com and [submit the link](https://github.com/KonradIT/goprowifihack/new/master#issues)
    * You can submit the new changes to a folder called [yourcameraname] in / with the files Wifi-Commands.md, Livestreaming.md, etc... Adhere to the existing document layout.
    * Document everything and submit it to the pull requests, this allows the community to better understand how the camera works.
  * If it does not:
    * Use a wireless network packet sniffer to capture the packages that are sent from the mobile app to the GoPro and vice versa. Android users might find [Packet Capture](https://play.google.com/store/apps/details?id=app.greyshirts.sslcapture) helpful as it does not require root access.
    * Submit the new commands and status to a folder with the base name of your camera (HERO6, not HERO6 Black).
    * If a request requires authentication (either a camera password or a token) write it as TOKEN or PASSWORD, do not submit URLs with your password/token!
    * Test each command to see if you can reproduce it from a computer. 

### Project vision:

This is a API wiki, not an API library or wrapper, there are other projects for that. We want to have all the cameras covered as well as drones and media services.

### Contact:

If you want to contact the author directly: [mail me!](mailto:mail@chernowii.com)
