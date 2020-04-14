# Controlling GoPro from RaspberryPi over Bluetooth

In order to connect to GoPro over Bluetooth, you need Raspberry Pi with Bluetooth Low Energy support, meaning Rasperry Pi 3, 3+ or Zero W, possibly other older models with working Bluetooth 4.0+ dongle.

GoPro needs to be paired at least with one device to turn the wireless (including Bluetooth) on.

Following procedure was tested on Raspberry Pi Zero W with Raspbian Stretch (release 2018-04-18) and GoPro HERO5 with FW 2.60.

If you're using BlueZ 5.50 or later, you might need to force the controller to run only in BLE mode with this line in /etc/bluetooth/main.conf (the comments are already there - this is to help you locate the commented statement):
```
# Restricts all controllers to the specified transport. Default value
# is "dual", i.e. both BR/EDR and LE enabled (when supported by the HW).
# Possible values: "dual", "bredr", "le"
ControllerMode = le
```
If this still doesn't allow the pairing to complete, try disabling the SAP plugin by modifying /lib/systemd/system/bluetooth.service:
```
ExecStart=/usr/lib/bluetooth/bluetoothd --noplugin=sap
```
And restart the Bluetooth daemon:
```shell
systemctl daemon-reload
systemctl restart bluetooth.service
```
## How to

First step is to prepare Raspberry. If you already have Raspbian set up, you can skip to the next section

1. Download latest [Raspbian Lite](https://www.raspberrypi.org/downloads/raspbian/)

2. Flash it onto SD card using [Etcher](https://etcher.io)

3. After flashing, create `ssh` file in the root of the SD card (volume _boot_) to enable ssh access:

    ```shell
    cd /Volumes/boot/
    touch ssh
    ```

4. Turn on Raspberry and SSH into it (default username `pi`, password `raspberry`)

5. Better to upgrade:

    ```shell
    sudo apt-get update
    sudo apt-get upgrade -y
    sudo apt-get dist-upgrade
    sudo rpi-update
    sudo reboot
    ```


Now it's time to connect Raspberry to GoPro.


6. Put GoPro into pairing mode (Connect new device > GoPro App)

7. Run:

   ```shell
   sudo bluetoothctl
   ```

8. Scan for devices:

   ```shell
   scan on
   ```
   and after a while, you should see GoPro's Bluetooth address (among others):

   ```shell
   Discovery started
   [CHG] Controller B8:27:EB:E2:EB:2D Discovering: yes
   [NEW] Device DE:71:28:EE:A7:FD GoPro 2495
   ```

9. Now we need to pair GoPro with Raspberry. Replace with your GoPro's Bluetooth address and run:

   ```shell
   trust DE:71:28:EE:A7:FD
   ```
   
   then you should see:
   
   ```shell
    [CHG] Device DE:71:28:EE:A7:FD Trusted: yes
    Changing DE:71:28:EE:A7:FD trust succeeded
   ```

10. Run (again replace):
  
    ```shell
    pair DE:71:28:EE:A7:FD
    ```
    
    then you should see something like this:
    
    ```shell
    Attempting to pair with E6:2A:02:F5:C3:00
    [CHG] Device DE:71:28:EE:A7:FD Connected: yes
    [CHG] Device DE:71:28:EE:A7:FD Paired: yes
    Pairing successful
    ```
Make sure the negotiated pairing keys are stored in /var/lib/bluetooth/${HCI_MAC}/${GOPRO_MAC}/info - there should be 4 sections titled: RemoteSignatureKey, LocalSignatureKey, LongTermKey, SlaveLongTermKey. Without these, you technically didn't complete pairing and you would not be able to access the GoPro over BLE until you reset all connections on the GoPro to start the pairing process again.

Now GoPro is paired with Raspberry. Now you can try to wake up your GoPro over Bluetooth.

11. Turn off the GoPro, then run (putting in your Bluetooth address):
  
    ```shell
    connect DE:71:28:EE:A7:FD
    ```
    
    and GoPro should wake up and light up the display

Let's continue and try controlling GoPro over Bluetooth.

12. Disconnect from the GoPro and exit  `bluetoothctl` utility:

    ```shell
    disconnect
    exit
    ```

13. Run:

    ```shell
    sudo gatttool -t random -b DE:71:28:EE:A7:FD -I
    ```

    – don't forget to replace the Bluetooth address.

14. Try to connect:

    ```shell
    connect
    ```

    and you should see:

    ```shell
    Attempting to connect to DE:71:28:EE:A7:FD
    Connection successful
    ```

15. Now try to run:

    ```shell
    char-write-req 2f 03160101
    ```

    and GoPro should start beeping – you've just turned on the locate function over Bluetooth!

16. To stop beeping, run:

    ```shell
    char-write-req 2f 03160100
    ```

But probably what you want the most is ability to turn on the WiFi over Bluetooth.

17. In that case, just run:

    ```shell
    char-write-req 2f 03170101
    ```

    to turn the WiFi on and

    ```shell
    char-write-req 2f 03170100
    ```

    to turn the WiFi off.

------
Step 13-15 can be run on directly on the command line, and you can substitute the different value below to replicate step 16 and 17 :
```shell
sudo gatttool -t random -b DE:71:28:EE:A7:FD --char-write-req -a 0x2f -n 03160101
```

This is just a first try to control GoPro over the WiFi. In case you want to elaborate more, take a look at [this article](https://gethypoxic.com/blogs/technical/gopro-hero5-interfaces) from HYPOXIC (especially the Bluetooth section). And you can [learn more about the `gatttool`](https://github.com/pcborenstein/bluezDoc/wiki/hcitool-and-gatttool-example).

If you have problems with making Bluetooth on your Raspberry working, try to look at [this tutorial](https://learn.adafruit.com/install-bluez-on-the-raspberry-pi/installation). 
