### Wifi Commands for HERO3/3+

Tested on: HERO3 Black, V3.00

The URL scheme:  http://10.5.5.9/param1/PARAM2?t=PASSWORD&p=%OPTION

* param1 = That defines if the action will be activated in the **camera** or **bacpac** (back in the HERO2 days the "bacpac" was the separate WiFi unit).
* PARAM2 = A two character parameter which defines what the camera needs to do. Eg: SH for Shoot
* OPTION: The arguments for PARAM2
* If you see a URL which contains "PASSWORD" without the quotes, it 
means it needs the camera password, which you can obtain here:  
http://10.5.5.9/bacpac/sd using cURL or other HTTP lib using the "GET" 
method.

HTTP Response Codes:

| Response Code | Meaning  |
| ------------- |:-------------:|
| 200 | Successful |
| 403 | Password Incorrect |
| 410 | Command Failed |

##### Basics:

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

	**Example if you have Hero3+Black with FW v03.03 (They are using HEX now):**

	Y  -M - D H : m : s

	2016-05-11 16:47:49

	Would be:

	(16 05 11 16 47 49 , Expressed in Base 10 (decimal), then converted to hexadecimal)

	%10%05%0b%10%2f%31

|Base 10 | Base 16 |
|--------|---------|
|16			 |	10     |
|05	 		 |	05     |
|11	     |	0b     |
|16	     |	10     |
|47	     |	2f     |
|49	     |	31     |

A more in depth table cane be found [here](/HERO3/Numeral-systems-conversion-table.md)

##### Mode:

* camera CM - 00 Video Mode

* camera CM - 01 Photo Mode

* camera CM - 02 Burst Mode

* camera CM - 03 Timelapse Mode

* camera CM - 04 Timer Mode (hero2)

* camera CM - 05 Play HDMI

##### Orientation

* camera UP - 00 Orientation UP

* camera UP - 01 Orientation DOWN

##### Video resolutions HERO2 and HERO3 silver:

* camera VR - 00 WVGA 60

* camera VR - 01 WVGA 120

* camera VR - 02 720 30

* camera VR - 03 720 60

* camera VR - 04 960 30

* camera VR - 05 960 48

* camera VR - 06 1080 30

##### Video resolutions Black edition:

* camera VV 08 4kCin12

* camera VV 07 2.7kCin24

* camera VV 06 4k 15

* camera VV 05 2.7k 30

* camera VV 04 1440p 40

* camera VV 03 1080 60

* camera VR 05 1080 30

* camera VR 06 960 48

* camera VV 02 960 100

* camera VV 01 720 120

* camera VV 00 WVGA 240

##### Video resolutions HERO3+Black:

* camera VV 06 - 4K

* camera VV 08 - 4K 17:9

* camera FS 01 - 4K 15FPS

* camera FS 00 - 4K 12FPS

* camera VV 07 - 2K

* camera VV 05 - 2.7k

* camera FS 02 - 2.7k 24FPS

* camera FS 04 - 2.7k 30FPS

* camera VV 04 - 1440p  

* camera FS 05 - 1440 48FPS

* camera VV 09 - 1080 SuperView   

* camera VV 03 - 1080  

* camera VV 02 -  960p   

* camera VV 0a - 720 SuperView   

* camera VV 01 - 720p

##### Frame rate:

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

##### Fov:

* camera FV - 00 wide

* camera FV - 01 medium

* camera FV - 02 narrow

##### Photo resolution HERO3 silver/white:

* camera PR - 00 11mpW

* camera PR - 01 8mpM

* camera PR - 02 5mpW

* camera PR - 03 5mpM

##### Photo resolution HERO3 Black ed:

* camera PR - 05 12mpW

* camera PR - 04 7mpW

* camera PR - 06 7mpM

* camera PR - 03 5mpM

##### Timelapse Interval:

* camera TI - 00 0,5 sec

* camera TI - 01 1sec

* camera TI - 05 5sec

* camera TI - 0a 10sec

* camera TI - 1e 30sec

* camera TI - 3c 60sec

##### Photo+Video Setting:

* camera PN - 00 OFF
* camera PN - 01 5sec
* camera PN - 02 10sec
* camera PN - 03 30sec
* camera PN - 04 1min


##### Volume:

* camera BS - 00 no sound

* camera BS - 01 70%

* camera BS - 02 100%

##### Continuous Shot (HERO3):

* camera CS - 00 Single

* camera CS - 03 3SPS

* camera CS - 05 5SPS

* camera CS - 0a 10SPS

##### Burst Rate HERO3:

* camera BU - 00 3/1s

* camera BU - 02 10/1s

* camera BU - 03 10/2s

* camera BU - 04 30/1s

* camera BU - 05 30/2s

* camera BU - 06 30/3s

##### Loop Video HERO3:

* camera LO - 00 OFF

* camera LO - 01 5min

* camera LO - 02 20Min

* camera LO - 03 60Min

* camera LO - 05 Max

---

####Protune Settings:

##### Protune ON/OFF:

* camera PT - 01 ON

* camera PT - 00 OFF

##### White Balance HERO3 Black/+Black ONLY IF Protune is ON:

* camera WB - 00 auto

* camera WB - 01 3000k

* camera WB - 02 5500k

* camera WB - 03 6500k

* camera WB - 04 CAMRAW

##### Color Profile for HERO3+ Black ONLY IF Protune is ON:

* camera CO - 00 GoPro Color
* camera CO - 01 Flat

##### ISO for HERO3+ Black ONLY IF Protune is ON:

* camera GA - 00 6400
* camera GA - 01 1600
* camera GA - 02 400

##### Sharpness for HERO3+ Black ONLY IF Protune is ON:

* camera SP - 00 HIGH
* camera SP - 01 MEDIUM
* camera SP - 02 LOW

##### Exposure Compensation for HERO3+ Black ONLY IF Protune is ON:

* camera EV - 06 "-2.0
* camera EV - 07 -1.5
* camera EV - 08 -1.0
* camera EV - 09 -0.5
* camera EV - 10 0
* camera EV - 11 +0.5
* camera EV - 12 +1.0
* camera EV - 13 +1.5
* camera EV - 14 +2.0

##### Low Light for 60+ FPS:

* camera LW - 01 ON
* camera LW - 00 OFF

##### Delete:

* camera DL - (no number) last

* camera DA - (no number) all

* camera DF - (replace %OPTION with /<folder name>/<file name>) delete a specific file


##### Leds:

* bacpac LB - 00 no leds

* camera LB - 01 2 leds

* camera LB - 02 4 leds

##### Spot Meter:

* camera EX - 00 OFF

* camera EX - 01 ON

##### One Button Mode:

* camera OB - 00 OFF

* camera OB - 01 ON

##### Protune Resolutions HERO3 silver DEPRECATED:

* camera VR - 07 1080 30 Protune

* camera VR - 08 1080 24 Protune

* camera VR - 11 1080 25 Protune

* camera VR - 09 960 60 Protune

##### Protune Resolutions HERO3 black ONLY IF PROTUNE IS ON:

* camera VV 00 720 120T

* camera VV 02 960 100T

* camera VV 03 1080 60T

* camera VV 04 1440 48T

* camera VV 05 2.7k 30T

* camera VV 06 4k 15T

* camera VV 07 2.7KCin24T

* camera VV 08 4kCin12T

##### Auto Power Off:

* camera AO - 00 NEVER

* camera AO - 01 60s

* camera AO - 02 120s

* camera AO - 03 300s

##### Default Mode:

* camera DM - 00 Video

* camera DM - 01 Photo

* camera DM - 02 Burst

* camera DM - 03 Timelapse

##### OnScreen Display:

* camera OS - 00 OFF

* camera OS - 01 ON

##### Locate:

* camera LL - 01 Start

* camera LL - 00 Stop

##### Video Mode:

* camera VM - 00 NTSC

* camera VM - 01 PAL
