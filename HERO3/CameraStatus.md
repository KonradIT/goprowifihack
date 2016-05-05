###Camera Status for HERO3

####GoPro HERO3/3+

GET the contents of this: http://10.5.5.9/camera/sx

See the available framerates for each resolution [here](/HERO3/Framerates-Resolutions.md)

Table for meaning of the contents:

byte | value
-----|--------
   0 |
   1 | Current mode: 0 = VIDEO, 1 = PHOTO, 2 = BURST, 3 = TIMELAPSE
   2 |
   3 |
   4 | SPOTMETER: 0 = OFF, 1 = ON
   5 | BURST TIMELAPSE: 0 = 0.5 SEC, 1 = 1 SEC, 2 = 2 SEC, 5 = 5 SEC, 10 = 10 SEC, 40 = 30 SEC, 60 = 60 SEC
   6 | (bit 0) ISO: 0 = 6400, 1 = 1600, 2 = 400 / (bit 2) SHARPNESS: 0 = HIGH , 1 = MEDIUM, 2 = LOW
   7 | FOV: 0 = WIDE, 1 = MEDIUM, 2 = NARROW
   8 | PHOTORES: 0 = 11_MP_WIDE, 1 = 8_MP_MED, 2 = 5_MP_WIDE, 3 = 5_MP_MED, 4 = 7_MP_WIDE, 5 = 12_MP_WIDE, 6 = 7_MP_MED
   9 | VIDEOMODE_GP2
  10 |
  11 |
  12 |
  13 | Video progress (hi byte)
  14 | Video progress (lo byte)
  15 |
  16 | VOLUME: 0 = OFF, 1 = 70%, 2 = 100%
  17 | LED: 0 = OFF, 1 = LED2, 2 = LED4
  18 | (bit 2) ORIENTATION: 0 = up, 1 = down, (bit 5) VIDEOREGION: 0 = NTSF, 1 = PAL
  19 |
  20 |
  21 | Photo remaining (hi byte)
  22 | Photo remaining (lo byte)
  23 | Photo count (hi byte)
  24 | Photo count (lo byte)
  25 | Video remaining (hi byte)
  26 | Video remaining (lo byte)
  27 | Video count (hi byte)
  28 | Video count (lo byte)
  29 | Recording
  30 | (bit 1) PROTUNE: 0 = OFF, 1 = ON / (bit 6): AUTO LOW LIGHT: 0 = OFF, 1 = ON / (bit 7) COLOR: 0 = COLOR, 1 = FLAT
  31 |
  32 | BURSTRATE: 0 = 3_1_SEC, 1 = 5_1_SEC, 2 = 10_1_SEC, 3 = 10_2_SEC, 4 = 30_1_SEC, 5 = 30_2_SEC, 6 = 30_3_SEC
  33 | PHOTO CONTINUOUS RATE: 0 = SINGLE, 3 = 3 FPS, 5 = 5 FPS, 10 = 10 FPS
  34 | WHITEBALANCE: 0 = AUTO, 1 = 3000K, 2 = 5500K, 3 = 6500K, 4 = CAM RAW
  35 |
  36 | VIDEO PHOTO INTERVAL: 0 = OFF, 1 = 5S, 2 = 10S, 3 = 30S, 4 = 60S
  37 | LOOPVIDEO: 0 = OFF, 1 = 5 MIN, 2 = 20 MIN, 3 = 60 MIN, 4 = 120 MIN, 5 = MAX
  38 |
  39 |
  40 |
  41 |
  42 |
  43 |
  44 |
  45 |
  46 |
  47 |
  48 |
  49 |
  50 | Video resolution: 0 = WVGA, 1 = 720, 2 = 960, 3 = 1080, 4 = 1440, 5 = 2.7K, 6 = 4K, 7 = 2.7K (SUPERVIEW), 8 = 4K (SUPERVIEW), 9 = 1080 (SUPERVIEW), 10 = 720 (SUPERVIEW)
  51 | FPS: 0 = 12, 1 = 15, 2 = 24, 3 = 25, 4 = 30, 5 = 48, 6 = 50, 7 = 60, 8 = 100,  9 = 120, 10 = 240,
  52 |
  53 | EXPOSURE: 6 = 2.0, 7 = 1.5, 8 = 1.0, 9 = 0.5, 10 = 0, 11 = +0.5, 12 = +1.0, 13 = +1.5, 14 = +2.0
  54 |
  55 |
  56 |
  57 | Battery
  58 |
  59 |
