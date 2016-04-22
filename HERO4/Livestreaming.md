###Livestreaming for HERO4

First, HTTP Get this URL: http://10.5.5.9/gp/gpControl/execute?p1=gpStream&a1=proto_v2&c1=restart and then you can get a UDP stream by using this URL: udp://10.5.5.9:8554 (you might have a hard time using this in your work...)

**NOTE**: If using ffplay (ffMPEG), try using the `nobuffer` flag, for a low latency stream.
More info can be found here: [https://www.reddit.com/r/gopro/comments/2md8hm/how_to_livestream_from_a_gopro_hero4/cr1b193](url)

**NOTE**: This works in the HERO4 Silver and Black, for HERO4 Session you might want to read [HERO4-Session.md](https://github.com/KonradIT/goprowifihack/blob/master/HERO4/HERO4-Session.md) on how to wake it up and enter streaming mode.
