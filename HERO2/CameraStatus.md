###Camera Status for HERO2

GET the contents of this: http://10.5.5.9/camera/se

Table for meaning of the contents:

byte | value
-----|--------
1    | ?
2 | Current mode. 0-4 matches set CM. 7 - in menu.
3 | ?
4 | Start up mode : 0 = video - 1 = photo - 2 = burst - 3 = timelapse
5 | Spot meter : 0 = Off - 1 = On
6 | Current timelapse interval
7 | Automatic power off : 0 = never - 1 = 60sec - 2 = 120sec - 3 = 300sec
8 | Current view angle
9 | Current photo mode
10 | Current video mode
11 | ?
12 | ?
13 | ?
14 | Recording minutes
15 | Recording seconds
16 | ?
17 | Current beep volume
18 | 2 = 4 LEDS - 1 = 2 LEDS - 0 = LEDS off
19 | bit 1 : 1 = preview on - 0 = preview off / bit 2 : ? / bit 3 : 0 = up - 1 = down / bit 4 : 1 = one button on - 0 = one button off / bit 5 : 1 = OSD on - 0 = OSD off / bit 6 : 0 = NTSC - 1 = PAL / bit 7 : 1 = Locate(beeping) / bit 8 : ?
20 | Battery %
21 | ?
22 | Photos available (hi byte) or 255 = no SD Card
23 | Photos available (lo byte)
24 | Photo count (hi byte)
25 | Photo count (lo byte)
26 | Video Time Remaining in minutes (hi byte)
27 | Video Time Left (lo byte)
28 | Video count (hi byte)
29 | Video count (lo byte)
30 | Recording
31 | ?
