### Media Browsing on HERO4

**NOTE: We still cannot get front lens media**

* A JSON list of the contents of the SD card: http://10.5.5.9:8080/gp/gpMediaListEx

* To get information about a video: http://10.5.5.9:8080/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4&t=videoinfo

	* dur = video duration
	* tag_count = number of hilight tags
	* tags = array of tags in milliseconds

Returns:

```
{"dur":"20","avc_profile":"100","profile":"50","tag_count":4,"tags":[1200,4330,5000,7400]}

```

* To get the thumbnail of a video: http://10.5.5.9:8080/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4

* GoPro offers a cherokee html frontend: http://10.5.5.9:8080/videos
* Formats: Photo (JPG), HD video (MP4), Low resolution video (LRV), Video thumbnail(THM).

### Requirements:

* WiFi on
* Camera powered on
* Session cameras: must be in App mode, that is, powered via WoL command
* SD card must be inserted

