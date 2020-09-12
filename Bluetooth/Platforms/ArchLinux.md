## Arch Linux setup

```shell
Requirements: bluetoothctl, gatttool
```

Tested on HERO 5 Black.


```shell
sudo bluetoothctl
```

```shell
>scan on
Look for GP [address]
>trust [address]
>pair [address]
>connect [address]
>CTRL-D
```

```shell

sudo gatttool -t random -b [address] -I

```

For a GoPro Hero 5 Black, handle 47 (0x2f) is mapped to b5f90072-aa8d-11e3-9046-0002a5d5c51b (Characteristic: Command) while handle 52 (0x34) is mapped to b5f90074-aa8d-11e3-9046-0002a5d5c51b (Characteristic: SetSetting). Other versions of GoPro might have them mapped differently - use the char-desc command in bluetoothctl to confirm handles to UUID mapping

### Command / Setting Structure

The structure of the value for Command or Setting is very similar:
Offset | Size | Field | Comments
------ | ---- | ----- | --------
0 | 1 | reqLen | 1+2*n+x where n is the number of 1 byte parameters, and x is the number of bytes required for each parameter > 1 byte
1 | 1 | request | Setting number as shown in REST API, see below for known commands
2 | 1 | len(p[0]) | Normally 1 since we have not exhausted the 8 bit space for commands or settings
3 | len(p[0]) | p[0] | First parameter
3+len(p[0]) | 1 | len(p[1]) | Only if the request required more than 1 parameters (ie, Submodes), and usually size 1
4+len(p[0]) | len(p[1]) | p[1] | Second parameter

Command table:
Command | Parameters | Comments
------- | ---------- | --------
0x01 | 1 | Shutter control
0x02 | 1 | Switch mode group
0x03 | 2 | Switch mode group & sub-mode
0x04 | 0 | Power off (BLE off)
0x05 | 0 | Sleep (BLE on)
0x0a | 1 | Reset video ProTune settings
0x0b | 1 | Reset Multishot ProTune settings
0x0c | 1 | Reset Photo ProTune settings
0x16 | 1 | Locator control
0x17 | 1 | WiFi control
0x18 | 0 | Tag

Commands available for gatttool:


- RECORD STOP: 2f 03010100
- RECORD START: 2f 03010101
- POWER OFF: 2f 020105
- TAG: 2f 020118

- WIFI ON: 2f 03170101
- WIFI OFF: 2f 03170100
- LOCATE ON: 2f 03160101
- LOCATE OFF: 2f 03160100

### MAIN_MODES:

- VIDEO: 2f 03020100
- PHOTO: 2f 03020101
- MULTISHOT: 2f 03020102

### SUB_MODES:

- VIDEO SINGLE: 2f 050301000100
- VIDEO TL: 2f 050301000101
- VIDEO PHOTO: 2f 050301000102
- VIDEO LOOP: 2f 050301000103

- PHOTO SINGLE: 2f 050301010101
- PHOTO NITE: 2f 050301010102

- MULTISHOT BURST: 2f 050301020100
- MULTISHOT TIMELAPSE: 2f 050301020101
- MULTISHOT NITELAPSE: 2f 050301020102

### Settings

Should be a direct map to the settings REST API, but settings with values > 256 (ie, NightLapse Interval) is untested. Here are some examples

- Video Resolution - 4K: 34 03020101
- TimeLapse Interval - 10s: 34 031e010a
- RAW Photo NightLapse On: 34 03630101
