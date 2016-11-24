###Livestreaming for HERO+/HERO+ LCD

First, HTTP Get this URL: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&a1=proto_v2&c1=restart and then you can get a UDP stream by using this URL: udp://10.5.5.9:8554 (you might have a hard time using this in your work...)

**NOTE**: If using ffplay (ffMPEG), try using the `nobuffer` flag, for a low latency stream.
More info can be found here: https://www.reddit.com/r/gopro/comments/2md8hm/how_to_livestream_from_a_gopro_hero4/cr1b193

Since working with UDP protocols and system calls, I recommend using @SonOf8Bits' easy to use GoPro HERO4 Streaming client written in Python: https://github.com/Sonof8Bits/GoProStreaming

###Advanced streaming parameters

For changing the specs of the live stream such as Bitrate, go to [the livestreaming tweaks page](https://github.com/KonradIT/goprowifihack/blob/master/HERO/WifiCommands.md#streaming-tweaks)
