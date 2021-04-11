## Commands:

**NOTE**: SETTINGS will follow those in [Wifi Commands](/HERO9/HERO9-Commands.md)

- LiveStreaming mode START: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=start
- LiveStreaming mode STOP: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=stop
- LiveStreaming mode RESTART: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&c1=restart

## Media browsing:

JSON media list exposed under http://10.5.5.9/gp/gpMediaList 

Thumbail endpoint works as well.

## Live preview

After LiveStreaming mode START, a live stream will be started and streamed out on UDP port 8554.

**NOTE**: The UDP streaming is directed to the IP who sent the API by HTTP GET, instead of broadcasting. And you need to constantly GET (every 25s or so) to keep the streaming alive.


ffmpeg command: ```ffplay udp://10.5.5.9:8554```
