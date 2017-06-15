## Media files over WiFi for HERO5 Black/Session

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
* To get information about a video: http://10.5.5.9:8080/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4&t=videoinfo

Returns:

```
{"dur":"20","avc_profile":"100","profile":"50","tag_count":4,"tags":[1200,4330,5000,7400]}

```

* dur = video duration
* tag_count = number of hilight tags
* tags = array of tags in milliseconds

* To get the thumbnail of a video: http://10.5.5.9:8080/gp/gpMediaMetadata?p=XXXGOPRO/GOPRXXXX.MP4

* GoPro offers a cherokee html frontend: http://10.5.5.9:8080/videos
* Formats: Photo (JPG), HD video (MP4), Low resolution video (LRV), Video thumbnail(THM).

### Requirements:

* WiFi on
* Camera powered on
* Session cameras: must be in App mode, that is, powered via WoL command
* SD card must be inserted

More here: 
https://github.com/KonradIT/goprowifihack/issues/57#issuecomment-265921001
