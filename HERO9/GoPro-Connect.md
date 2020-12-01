## What is GoPro Connect (Webcam mode)?

Simply put, it exposes the same APIs available when using the camera via WiFi but over USB Ethernet.

## Commands:

Start recording/taking a photo works (see: https://twitter.com/konrad_it/status/1309092303651434498)

**NOTE**: Issue these commands over IP ending on the *.51* octet.

- Webcam mode START: http://172.XX.XXX.51/gp/gpWebcam/START
	- Resolutions:
	- 1080p: http://172.XX.XXX.51/gp/gpWebcam/START?res=1080
	- 720p: http://172.XX.XXX.51/gp/gpWebcam/START?res=720
	- 480p: http://172.XX.XXX.51/gp/gpWebcam/START?res=480
- Webcam mode STOP: http://172.XX.XXX.51/gp/gpWebcam/STOP
- Wide FOV: http://172.XX.XXX.51/gp/gpWebcam/SETTINGS?fov=0
- Linear FOV: http://172.XX.XXX.51/gp/gpWebcam/SETTINGS?fov=4
- Narrow FOV: http://172.XX.XXX.51/gp/gpWebcam/SETTINGS?fov=6

## Media browsing:

JSON media list exposed under http://172.XX.XXX.51/gp/gpMediaList 

Thumbail endpoint works as well.

## Live preview

After Webcam mode START, a live stream will be started and streamed out on UDP port 8554.


VLC command: ```vlc -vvv --network-caching=300 --sout-x264-preset=ultrafast --sout-x264-tune=zerolatency --sout-x264-vbv-bufsize 0 --sout-transcode-threads 4 --no-audio udp://@:8554```

Many thanks to Daryl Stimm from GoPro for making most of the info here public. 