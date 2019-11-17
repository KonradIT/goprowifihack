### GoPro MAX Commands, Status and Notes

## Basic controls:

##### Shutter

- Trigger: http://10.5.5.9/gp/gpControl/command/shutter?p=1
- Stop (Video/Timelapse): http://10.5.5.9/gp/gpControl/command/shutter?p=0

##### Default Boot Mode:

- Video: http://10.5.5.9/gp/gpControl/setting/53/0
- Photo: http://10.5.5.9/gp/gpControl/setting/53/1
- MultiShot: http://10.5.5.9/gp/gpControl/setting/53/2

##### Primary modes:

- Video: http://10.5.5.9/gp/gpControl/command/set_mode?p=1000
- Photo: http://10.5.5.9/gp/gpControl/command/set_mode?p=1001
- MultiShot: http://10.5.5.9/gp/gpControl/command/set_mode?p=1002

##### Tag moment:

- Sends tag command: http://10.5.5.9/gp/gpControl/command/storage/tag_moment

##### Locate:

- On: http://10.5.5.9/gp/gpControl/command/system/locate?p=1
- Off: http://10.5.5.9/gp/gpControl/command/system/locate?p=0

##### Power:

- Power Off: http://10.5.5.9/gp/gpControl/command/system/sleep
- Power On: Send a Wake On Lan command with the parameters: IP address: 10.5.5.9, Subnet Mask 255.255.255.0, Port 9.

### Video

##### Resolution

- 5.6K: http://10.5.5.9/gp/gpControl/setting/2/21
- 1440: http://10.5.5.9/gp/gpControl/setting/2/7
- 1080: http://10.5.5.9/gp/gpControl/setting/2/9

##### Frames Per Second

- 60: http://10.5.5.9/gp/gpControl/setting/3/5
- 50: http://10.5.5.9/gp/gpControl/setting/3/6
- 30: http://10.5.5.9/gp/gpControl/setting/3/8
- 25: http://10.5.5.9/gp/gpControl/setting/3/9
- 24: http://10.5.5.9/gp/gpControl/setting/3/10

##### Interval for TimeLapse Video:

- 60 Seconds: http://10.5.5.9/gp/gpControl/setting/5/6
- 30 Seconds: http://10.5.5.9/gp/gpControl/setting/5/5
- 10 Seconds: http://10.5.5.9/gp/gpControl/setting/5/4
- 5 Seconds: http://10.5.5.9/gp/gpControl/setting/5/3
- 2 Seconds: http://10.5.5.9/gp/gpControl/setting/5/2
- 1 Second: http://10.5.5.9/gp/gpControl/setting/5/1
- 0.5 Seconds: http://10.5.5.9/gp/gpControl/setting/5/0

##### Interval

- 60 Seconds: http://10.5.5.9/gp/gpControl/setting/30/60
- 30 Seconds: http://10.5.5.9/gp/gpControl/setting/30/30
- 10 Seconds: http://10.5.5.9/gp/gpControl/setting/30/10
- 5 Seconds: http://10.5.5.9/gp/gpControl/setting/30/5
- 2 Seconds: http://10.5.5.9/gp/gpControl/setting/30/2
- 1 Second: http://10.5.5.9/gp/gpControl/setting/30/1
- 0.5 Seconds: http://10.5.5.9/gp/gpControl/setting/30/0

##### Low Light

- ON: http://10.5.5.9/gp/gpControl/setting/8/1
- OFF: http://10.5.5.9/gp/gpControl/setting/8/0

##### ISO Max

- 6400: http://10.5.5.9/gp/gpControl/setting/13/0
- 3200: http://10.5.5.9/gp/gpControl/setting/13/3
- 1600: http://10.5.5.9/gp/gpControl/setting/13/1
- 1200: http://10.5.5.9/gp/gpControl/setting/13/5
- 1000: http://10.5.5.9/gp/gpControl/setting/13/6
- 800: http://10.5.5.9/gp/gpControl/setting/13/4
- 400: http://10.5.5.9/gp/gpControl/setting/13/2
- 200: http://10.5.5.9/gp/gpControl/setting/13/7
- 100: http://10.5.5.9/gp/gpControl/setting/13/8

##### Default Photo Sub Mode

- Single: http://10.5.5.9/gp/gpControl/setting/16/0
- Continuous: http://10.5.5.9/gp/gpControl/setting/16/1
- Night: http://10.5.5.9/gp/gpControl/setting/16/2

##### Spot Meter

- ON: http://10.5.5.9/gp/gpControl/setting/20/1
- OFF: http://10.5.5.9/gp/gpControl/setting/20/0

##### ISO Max

- 3200: http://10.5.5.9/gp/gpControl/setting/24/5
- 1600: http://10.5.5.9/gp/gpControl/setting/24/4
- 800: http://10.5.5.9/gp/gpControl/setting/24/0
- 400: http://10.5.5.9/gp/gpControl/setting/24/1
- 200: http://10.5.5.9/gp/gpControl/setting/24/2
- 100: http://10.5.5.9/gp/gpControl/setting/24/3

##### Multi-shot Spot Meter

- ON: http://10.5.5.9/gp/gpControl/setting/33/1
- OFF: http://10.5.5.9/gp/gpControl/setting/33/0

##### ISO Max

- 3200: http://10.5.5.9/gp/gpControl/setting/37/5
- 1600: http://10.5.5.9/gp/gpControl/setting/37/4
- 800: http://10.5.5.9/gp/gpControl/setting/37/0
- 400: http://10.5.5.9/gp/gpControl/setting/37/1
- 200: http://10.5.5.9/gp/gpControl/setting/37/2
- 100: http://10.5.5.9/gp/gpControl/setting/37/3

##### Screensaver

- 1 MIN: http://10.5.5.9/gp/gpControl/setting/51/1
- 2 MIN: http://10.5.5.9/gp/gpControl/setting/51/2
- 3 MIN: http://10.5.5.9/gp/gpControl/setting/51/3
- NEVER: http://10.5.5.9/gp/gpControl/setting/51/0

##### Quick Capture

- ON: http://10.5.5.9/gp/gpControl/setting/54/1
- OFF: http://10.5.5.9/gp/gpControl/setting/54/0

##### Auto Off

- 5 MIN: http://10.5.5.9/gp/gpControl/setting/59/4
- 15 MIN: http://10.5.5.9/gp/gpControl/setting/59/6
- 30 MIN: http://10.5.5.9/gp/gpControl/setting/59/7
- NEVER: http://10.5.5.9/gp/gpControl/setting/59/0

##### Video Sub Mode

- Video: http://10.5.5.9/gp/gpControl/setting/68/0
- Time Warp Video: http://10.5.5.9/gp/gpControl/setting/68/4

### Photo

##### Photo Sub Mode

- Single: http://10.5.5.9/gp/gpControl/setting/69/0
- Continuous: http://10.5.5.9/gp/gpControl/setting/69/1
- Night: http://10.5.5.9/gp/gpControl/setting/69/2

##### ISO Min

- 3200: http://10.5.5.9/gp/gpControl/setting/75/5
- 1600: http://10.5.5.9/gp/gpControl/setting/75/4
- 800: http://10.5.5.9/gp/gpControl/setting/75/0
- 400: http://10.5.5.9/gp/gpControl/setting/75/1
- 200: http://10.5.5.9/gp/gpControl/setting/75/2
- 100: http://10.5.5.9/gp/gpControl/setting/75/3

##### ISO Min

- 100: http://10.5.5.9/gp/gpControl/setting/76/3
- 200: http://10.5.5.9/gp/gpControl/setting/76/2
- 400: http://10.5.5.9/gp/gpControl/setting/76/1
- 800: http://10.5.5.9/gp/gpControl/setting/76/0
- 1600: http://10.5.5.9/gp/gpControl/setting/76/4
- 3200: http://10.5.5.9/gp/gpControl/setting/76/5

### Other

##### Audio Protune

- On: http://10.5.5.9/gp/gpControl/setting/79/1
- Off: http://10.5.5.9/gp/gpControl/setting/79/0

##### GPS

- ON: http://10.5.5.9/gp/gpControl/setting/83/1
- OFF: http://10.5.5.9/gp/gpControl/setting/83/0

##### Language

- English: http://10.5.5.9/gp/gpControl/setting/84/0
- French: http://10.5.5.9/gp/gpControl/setting/84/6
- German: http://10.5.5.9/gp/gpControl/setting/84/2
- Italian: http://10.5.5.9/gp/gpControl/setting/84/3
- Spanish: http://10.5.5.9/gp/gpControl/setting/84/4
- Chinese: http://10.5.5.9/gp/gpControl/setting/84/1
- Japanese: http://10.5.5.9/gp/gpControl/setting/84/5
- Korean: http://10.5.5.9/gp/gpControl/setting/84/7
- Portuguese: http://10.5.5.9/gp/gpControl/setting/84/8
- Russian: http://10.5.5.9/gp/gpControl/setting/84/9
- Swedish: http://10.5.5.9/gp/gpControl/setting/84/10
- Chinese(Traditional): http://10.5.5.9/gp/gpControl/setting/84/11

##### Voice Control Language

- Chinese: http://10.5.5.9/gp/gpControl/setting/85/8
- English - AUS: http://10.5.5.9/gp/gpControl/setting/85/2
- English - IND: http://10.5.5.9/gp/gpControl/setting/85/13
- English - UK: http://10.5.5.9/gp/gpControl/setting/85/1
- English - US: http://10.5.5.9/gp/gpControl/setting/85/0
- French: http://10.5.5.9/gp/gpControl/setting/85/4
- German: http://10.5.5.9/gp/gpControl/setting/85/3
- Italian: http://10.5.5.9/gp/gpControl/setting/85/5
- Japanese: http://10.5.5.9/gp/gpControl/setting/85/9
- Korean: http://10.5.5.9/gp/gpControl/setting/85/10
- Portuguese: http://10.5.5.9/gp/gpControl/setting/85/11
- Russian: http://10.5.5.9/gp/gpControl/setting/85/12
- Spanish: http://10.5.5.9/gp/gpControl/setting/85/6
- Spanish - NA: http://10.5.5.9/gp/gpControl/setting/85/7

##### Voice Control Enable

- ON: http://10.5.5.9/gp/gpControl/setting/86/1
- OFF: http://10.5.5.9/gp/gpControl/setting/86/0

##### Beeps

- High: http://10.5.5.9/gp/gpControl/setting/87/100
- Medium: http://10.5.5.9/gp/gpControl/setting/87/70
- Low: http://10.5.5.9/gp/gpControl/setting/87/40
- Mute: http://10.5.5.9/gp/gpControl/setting/87/0

##### LCD Brightness

- 10%: http://10.5.5.9/gp/gpControl/setting/88/10
- 20%: http://10.5.5.9/gp/gpControl/setting/88/20
- 30%: http://10.5.5.9/gp/gpControl/setting/88/30
- 40%: http://10.5.5.9/gp/gpControl/setting/88/40
- 50%: http://10.5.5.9/gp/gpControl/setting/88/50
- 60%: http://10.5.5.9/gp/gpControl/setting/88/60
- 70%: http://10.5.5.9/gp/gpControl/setting/88/70
- 80%: http://10.5.5.9/gp/gpControl/setting/88/80
- 90%: http://10.5.5.9/gp/gpControl/setting/88/90
- 100%: http://10.5.5.9/gp/gpControl/setting/88/100

##### LED

- All On: http://10.5.5.9/gp/gpControl/setting/91/2
- All Off: http://10.5.5.9/gp/gpControl/setting/91/0
- Front Off Only: http://10.5.5.9/gp/gpControl/setting/91/1

##### Audio Input

- None: http://10.5.5.9/gp/gpControl/setting/95/0
- Standard Mic: http://10.5.5.9/gp/gpControl/setting/95/1
- Standard Mic+: http://10.5.5.9/gp/gpControl/setting/95/2
- Powered Mic: http://10.5.5.9/gp/gpControl/setting/95/3
- Powered Mic+: http://10.5.5.9/gp/gpControl/setting/95/4
- Line In: http://10.5.5.9/gp/gpControl/setting/95/5

##### No Audio Track

- ON: http://10.5.5.9/gp/gpControl/setting/96/1
- OFF: http://10.5.5.9/gp/gpControl/setting/96/0

##### ISO Min

- 6400: http://10.5.5.9/gp/gpControl/setting/102/0
- 3200: http://10.5.5.9/gp/gpControl/setting/102/3
- 1600: http://10.5.5.9/gp/gpControl/setting/102/1
- 800: http://10.5.5.9/gp/gpControl/setting/102/4
- 400: http://10.5.5.9/gp/gpControl/setting/102/2
- 200: http://10.5.5.9/gp/gpControl/setting/102/7
- 100: http://10.5.5.9/gp/gpControl/setting/102/8

##### Wake On Voice

- ON: http://10.5.5.9/gp/gpControl/setting/104/1
- OFF: http://10.5.5.9/gp/gpControl/setting/104/0

##### Timer

- 10 Seconds: http://10.5.5.9/gp/gpControl/setting/105/2
- 3 Seconds: http://10.5.5.9/gp/gpControl/setting/105/1
- Off: http://10.5.5.9/gp/gpControl/setting/105/0

##### Video Compression

- HEVC: http://10.5.5.9/gp/gpControl/setting/106/1
- H.264 + HEVC: http://10.5.5.9/gp/gpControl/setting/106/0

##### Clips

- 30 Seconds: http://10.5.5.9/gp/gpControl/setting/107/2
- 15 Seconds: http://10.5.5.9/gp/gpControl/setting/107/1
- Off: http://10.5.5.9/gp/gpControl/setting/107/0

##### Speed

- 30X: http://10.5.5.9/gp/gpControl/setting/111/1
- 15X: http://10.5.5.9/gp/gpControl/setting/111/0
- 10X: http://10.5.5.9/gp/gpControl/setting/111/9
- 5X: http://10.5.5.9/gp/gpControl/setting/111/8
- 2X: http://10.5.5.9/gp/gpControl/setting/111/7
- Auto: http://10.5.5.9/gp/gpControl/setting/111/10

##### Landscape Lock

- All: http://10.5.5.9/gp/gpControl/setting/112/0
- Landscape: http://10.5.5.9/gp/gpControl/setting/112/5
- Locked: http://10.5.5.9/gp/gpControl/setting/112/255

##### Protune

- ON: http://10.5.5.9/gp/gpControl/setting/114/1
- OFF: http://10.5.5.9/gp/gpControl/setting/114/0

##### White Balance

- 6500K: http://10.5.5.9/gp/gpControl/setting/115/3
- 6000K: http://10.5.5.9/gp/gpControl/setting/115/7
- 5500K: http://10.5.5.9/gp/gpControl/setting/115/2
- 5000K: http://10.5.5.9/gp/gpControl/setting/115/12
- 4500K: http://10.5.5.9/gp/gpControl/setting/115/11
- Auto: http://10.5.5.9/gp/gpControl/setting/115/0
- Native: http://10.5.5.9/gp/gpControl/setting/115/4
- 4000K: http://10.5.5.9/gp/gpControl/setting/115/5
- 3200K: http://10.5.5.9/gp/gpControl/setting/115/10
- 2800K: http://10.5.5.9/gp/gpControl/setting/115/9
- 2300K: http://10.5.5.9/gp/gpControl/setting/115/8

##### Color

- Flat: http://10.5.5.9/gp/gpControl/setting/116/1
- GoPro: http://10.5.5.9/gp/gpControl/setting/116/0

##### Sharpness

- High: http://10.5.5.9/gp/gpControl/setting/117/0
- Medium: http://10.5.5.9/gp/gpControl/setting/117/1
- Low: http://10.5.5.9/gp/gpControl/setting/117/2

##### EV Comp

- 2.0: http://10.5.5.9/gp/gpControl/setting/118/0
- 1.5: http://10.5.5.9/gp/gpControl/setting/118/1
- 1.0: http://10.5.5.9/gp/gpControl/setting/118/2
- 0.5: http://10.5.5.9/gp/gpControl/setting/118/3
- 0.0: http://10.5.5.9/gp/gpControl/setting/118/4
- -0.5: http://10.5.5.9/gp/gpControl/setting/118/5
- -1.0: http://10.5.5.9/gp/gpControl/setting/118/6
- -1.5: http://10.5.5.9/gp/gpControl/setting/118/7
- -2.0: http://10.5.5.9/gp/gpControl/setting/118/8

##### Lens (Video/TimeWARP)

- Max SuperView: http://10.5.5.9/gp/gpControl/setting/121/7
- Wide: http://10.5.5.9/gp/gpControl/setting/121/0
- Linear: http://10.5.5.9/gp/gpControl/setting/121/4
- Narrow: http://10.5.5.9/gp/gpControl/setting/121/6
- Dual 360: http://10.5.5.9/gp/gpControl/setting/121/5

##### Lens (Photo)

- Max SuperView: http://10.5.5.9/gp/gpControl/setting/122/18
- Wide: http://10.5.5.9/gp/gpControl/setting/122/15

##### Lens (TimeLapse)

- Max SuperView: http://10.5.5.9/gp/gpControl/setting/123/18
- Wide: http://10.5.5.9/gp/gpControl/setting/123/15

##### Bit Rate

- Low: http://10.5.5.9/gp/gpControl/setting/124/0
- High: http://10.5.5.9/gp/gpControl/setting/124/1

##### Default Preset

- Last Used: http://10.5.5.9/gp/gpControl/setting/127/65535
- HERO Video: http://10.5.5.9/gp/gpControl/setting/127/0
- 360 Video: http://10.5.5.9/gp/gpControl/setting/127/196608
- HERO Photo: http://10.5.5.9/gp/gpControl/setting/127/65536
- HERO PowerPano: http://10.5.5.9/gp/gpControl/setting/127/65537
- 360 Photo: http://10.5.5.9/gp/gpControl/setting/127/262144
- HERO TimeWarp: http://10.5.5.9/gp/gpControl/setting/127/131072
- HERO TimeLapse: http://10.5.5.9/gp/gpControl/setting/127/131073
- 360 TimeWarp: http://10.5.5.9/gp/gpControl/setting/127/327680

##### Format

- Video: http://10.5.5.9/gp/gpControl/setting/128/13
- Photo: http://10.5.5.9/gp/gpControl/setting/128/20

##### Anti-Flicker

- 60Hz: http://10.5.5.9/gp/gpControl/setting/134/0
- 50Hz: http://10.5.5.9/gp/gpControl/setting/134/1

##### Audio

- Stereo: http://10.5.5.9/gp/gpControl/setting/137/0
- Front: http://10.5.5.9/gp/gpControl/setting/137/1
- Back: http://10.5.5.9/gp/gpControl/setting/137/2
- Match Lens: http://10.5.5.9/gp/gpControl/setting/137/3

##### 360 AUDIO

- Stereo: http://10.5.5.9/gp/gpControl/setting/138/0
- 360 + Stereo: http://10.5.5.9/gp/gpControl/setting/138/5

##### RAW Audio

- High: http://10.5.5.9/gp/gpControl/setting/139/2
- Medium: http://10.5.5.9/gp/gpControl/setting/139/1
- Low: http://10.5.5.9/gp/gpControl/setting/139/0
- Off: http://10.5.5.9/gp/gpControl/setting/139/3

##### QuikCapture Default Mode

- Last Used: http://10.5.5.9/gp/gpControl/setting/141/2
- HERO: http://10.5.5.9/gp/gpControl/setting/141/0
- 360: http://10.5.5.9/gp/gpControl/setting/141/1

##### Lens Mode

- Single: http://10.5.5.9/gp/gpControl/setting/142/0
- Dual: http://10.5.5.9/gp/gpControl/setting/142/1

##### Lens

- Front: http://10.5.5.9/gp/gpControl/setting/143/0
- Rear: http://10.5.5.9/gp/gpControl/setting/143/1

##### Shutter

- 1/960: http://10.5.5.9/gp/gpControl/setting/145/23
- 1/800: http://10.5.5.9/gp/gpControl/setting/145/28
- 1/480: http://10.5.5.9/gp/gpControl/setting/145/22
- 1/400: http://10.5.5.9/gp/gpControl/setting/145/21
- 1/384: http://10.5.5.9/gp/gpControl/setting/145/25
- 1/240: http://10.5.5.9/gp/gpControl/setting/145/18
- 1/200: http://10.5.5.9/gp/gpControl/setting/145/17
- 1/192: http://10.5.5.9/gp/gpControl/setting/145/16
- 1/120: http://10.5.5.9/gp/gpControl/setting/145/13
- 1/100: http://10.5.5.9/gp/gpControl/setting/145/12
- 1/96: http://10.5.5.9/gp/gpControl/setting/145/11
- 1/60: http://10.5.5.9/gp/gpControl/setting/145/8
- 1/50: http://10.5.5.9/gp/gpControl/setting/145/7
- 1/48: http://10.5.5.9/gp/gpControl/setting/145/6
- 1/30: http://10.5.5.9/gp/gpControl/setting/145/5
- 1/25: http://10.5.5.9/gp/gpControl/setting/145/4
- 1/24: http://10.5.5.9/gp/gpControl/setting/145/3
- Auto: http://10.5.5.9/gp/gpControl/setting/145/0

##### Shutter

- Auto: http://10.5.5.9/gp/gpControl/setting/146/0
- 1/125: http://10.5.5.9/gp/gpControl/setting/146/1
- 1/250: http://10.5.5.9/gp/gpControl/setting/146/2
- 1/500: http://10.5.5.9/gp/gpControl/setting/146/3
- 1/1000: http://10.5.5.9/gp/gpControl/setting/146/4
- 1/2000: http://10.5.5.9/gp/gpControl/setting/146/5

##### Max HyperSmooth

- ON: http://10.5.5.9/gp/gpControl/setting/148/1
- OFF: http://10.5.5.9/gp/gpControl/setting/148/0

##### Wind

- Auto: http://10.5.5.9/gp/gpControl/setting/149/2
- On: http://10.5.5.9/gp/gpControl/setting/149/1
- Off: http://10.5.5.9/gp/gpControl/setting/149/0

##### Horizon Leveling (Video)

- On: http://10.5.5.9/gp/gpControl/setting/150/1
- Off: http://10.5.5.9/gp/gpControl/setting/150/0
