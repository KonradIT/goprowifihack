## Media files over WiFi for HERO5 Black/Session

### Media List:

* A JSON list of the contents of the SD card: http://10.5.5.9:8080/gp/gpMediaList

This returns:

```
{
  "id": "id",
  "media": [
    {
      "d": "131GOPRO",
      "fs": [
        {
          "n": "GOPR8204.MP4",
          "mod": "1495712610",
          "ls": "-1",
          "s": "54447740"
        },
        {
          "n": "GOPR8205.MP4",
          "mod": "1495729970",
          "ls": "-1",
          "s": "146317687"
        },
        {
          "n": "GOPR8206.MP4",
          "mod": "1495730200",
          "ls": "-1",
          "s": "99545292"
        },
```

### Media Information:

#### Video:

* To get information about a video: http://10.5.5.9:8080/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4&t=videoinfo

	* dur = video duration
	* tag_count = number of hilight tags
	* tags = array of tags in milliseconds

Returns:

```
{"dur":"20","avc_profile":"100","profile":"50","tag_count":4,"tags":[1200,4330,5000,7400]}

```

* To get even more information about a video: http://10.5.5.9/gp/gpMediaMetadata?p=/XXXGOPRO/GOPRXXXX.MP4&t=v4info
	* w = width
	* h = height
	* eis = EIS enabled
	
Returns:

```

{"cre":"1532960473","s":"77722399","us":"0","eis":"1","pta":"0","ao":"auto","tr":"0","mp":"0","gumi":"626e8c5bcde3c8ba1aa1c7220f811b5e","ls":"4601641","cl":"0","hc":"1","hi":[66],"dur":"14","w":"1920","h":"1080","fps":"90000","fps_denom":"3003","prog":"1","subsample":"0"}

```
#### Photo:

* To get information about a photo: http://10.5.5.9/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.JPG&t=v4info
	* w = width
	* h = height
	* eis = EIS enabled
	* wdr = WDR enabled
	* raw = RAW enabled
	
Returns:

```

{"cre":"1532735778","s":"2036141","hc":"0","us":"0","eis":"0","wdr":"0","raw":"0","tr":"0","gumi":"30029ffca2fb9f9a005f4cf424e6c662","w":"4000","h":"3000"}

```
* To get EXIF information of a photo: http://10.5.5.9/gp/gpMediaMetadata?p=/XXXGOPRO/GOPRXXXX.JPG&t=exif

### Media Thumbnail:

* To get the thumbnail of a video: http://10.5.5.9/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4
* To get the thumbnail of a photo: http://10.5.5.9/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.JPG

### Other info:

* GoPro offers a cherokee html frontend: http://10.5.5.9:8080/videos/DCIM
* Formats: Photo (JPG), HD video (MP4), Low resolution video (LRV), Video thumbnail(THM).

### Requirements:

* WiFi on
* Camera powered on
* Session cameras: must be in App mode, that is, powered via WoL command
* SD card must be inserted

More here: 
https://github.com/KonradIT/goprowifihack/issues/57#issuecomment-265921001
