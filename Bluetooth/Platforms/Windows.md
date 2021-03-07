## GoPro Camera control and setting query with Windows 10

To issue your custom comands from a command line program use [BLEConsole](https://sensboston.github.io/BLEConsole/)

This app from the Windows Store also works: [Bluetooth LE Lab](https://www.microsoft.com/en-us/p/bluetooth-le-lab/9n6jd37gwzc8?activetab=pivot:overviewtab)

Using BLEConsole:

```
format hex
open GoPro 0000
write #06/#00 03 01 01 01
write #06/#00 03 01 01 00
```

`#06` is the control service (0x02F)

### A much better alternative: gopro-ble-py

[GoPro-BLE-py](https://github.com/konradit/gopro-ble-py) has been rewritten using a new library, called `bleak`, and now offers compatibility with systems that run BlueZ (most Linux distros), Windows 10 and Mac OS.

It also works with the Hero9, Hero8 as well as previously supported cameras (MAX, Hero7, Hero6 and Hero5)
