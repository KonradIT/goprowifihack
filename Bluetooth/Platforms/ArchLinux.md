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


