###Wifi Commands for HERO2

The URL scheme:  http://10.5.5.9/param1/PARAM2?t=PASSWORD&p=%OPTION

* param1 = That defines if the action will be activated in the **camera** or **bacpac** (back in the HERO2 days the "bacpac" was the separate WiFi unit).
* PARAM2 = A two character parameter which defines what the camera needs to do. Eg: SH for Shoot
* OPTION: The arguments for PARAM2

#####Basics:

* bacpac PW - 00 Turn GoPro OFF

* bacpac PW - 01 Turn GoPro ON

* bacpac RS - Reset bacpac

* bacpac SH - 01 Shutter

* bacpac SH - 00 Stop

* camera PV - 02 Preview ON

* camera PV - 00 Preview OFF

* camera TM - Set time, requires a longer string, each field is a byte with a % before it:

	* Last 2 digits of the year
	* Month (1 - January, 12 - December)
	* Day of the month (1 - 31)
	* Hour (24-hour format, starts from zero)
	* Minute
	* Second

#####Mode:

* camera CM - 00 Video Mode

* camera CM - 01 Photo Mode

* camera CM - 02 Burst Mode

* camera CM - 03 Timelapse Mode

* camera CM - 04 Timer Mode (hero2)

* camera CM - 05 Play HDMI

#####Orientation

* camera UP - 00 Orientation UP

* camera UP - 01 Orientation DOWN

#####Video resolutions:

* camera VR - 00 WVGA 60

* camera VR - 01 WVGA 120

* camera VR - 02 720 30

* camera VR - 03 720 60

* camera VR - 04 960 30

* camera VR - 05 960 48

* camera VR - 06 1080 30

#####Frame rate:

* camera FS - 00 FPS12

* camera FS - 01 FPS15

* camera FS - 0b FPS12p5

* camera FS - 02 FPS24

* camera FS - 03 FPS25

* camera FS - 04 FPS30

* camera FS - 05 FPS48

* camera FS - 06 FPS50

* camera FS - 07 FPS60

* camera FS - 08 FPS100

* camera FS - 09 FPS120

* camera FS - 0a FPS240

#####Fov:

* camera FV - 00 wide

* camera FV - 01 medium

* camera FV - 02 narrow

#####Photo resolutions:

* camera PR - 00 11mpW

* camera PR - 01 8mpM

* camera PR - 02 5mpW

* camera PR - 03 5mpM

#####Timelapse Interval:

* camera TI - 00 0,5 sec

* camera TI - 01 1sec

* camera TI - 05 5sec

* camera TI - 0a 10sec

* camera TI - 1e 30sec

* camera TI - 3c 60sec

#####Volume:

* camera BS - 00 no sound

* camera BS - 01 70%

* camera BS - 02 100%

#####Protune ON/OFF:

* camera PT - 01 ON

* camera PT - 00 OFF

#####Delete:

* camera DL - (no number) last

* camera DA - (no number) all

* camera DF - delete specific?

#####Leds:

* bacpac LB - 00 no leds

* camera LB - 01 2 leds

* camera LB - 02 4 leds

#####Spot Meter:

* camera EX - 00 OFF

* camera EX - 01 ON

#####One Button Mode:

* camera OB - 00 OFF

* camera OB - 01 ON

#####Protune Resolutions :

* camera VR - 07 1080 30 Protune

* camera VR - 08 1080 24 Protune

* camera VR - 11 1080 25 Protune

* camera VR - 09 960 60 Protune

#####Auto Power Off:

* camera AO - 00 NEVER

* camera AO - 01 60s

* camera AO - 02 120s

* camera AO - 03 300s

#####Default Mode:

* camera DM - 00 Video

* camera DM - 01 Photo

* camera DM - 02 Burst

* camera DM - 03 Timelapse

#####OnScreen Display:

* camera OS - 00 OFF

* camera OS - 01 ON

#####Locate:

* camera LL - 01 Start

* camera LL - 00 Stop

#####Video Mode:

* camera VM - 00 NTSC

* camera VM - 01 PAL
