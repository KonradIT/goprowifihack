### Camera Status

This URL contains a JSON with the camera parameters: http://10.5.5.9/gp/gpControl/status

### Status object:

- 1 - Internal Battery is available:
  - 0 = No Battery
  - 1 = Battery is available
- 2 - Internal Battery Level:
  - 4 = Charging
  - 3 = Full
  - 2 = Halfway
  - 1 = Low
  - 0 = Empty
- 43 - Current Mode:
  - Video - 0
  - Photo - 1
  - MultiShot - 2
- 44 - Current SubMode
  - 0 = Video/Single Pic/Burst
  - 1 = TL Video/Continuous/TimeLapse
  - 2 = Video+Photo/NightPhoto/NightLapse
- 13 - Current Recording Video Duration
- 39 - Number of MultiShot pictures taken
- 31 - Number of clients connected to the camera [reference from HERO4 Session doc]
- 32 - Streaming feed status:
  - 0 = Not Streaming
  - 1 = Streaming
- 33 - SD card inserted:
  - 0 = SD card inserted
  - 2 = No SD Card present
- 34 - Remaining Photos
- 35 - Remaining Video Time
- 36 - Number of Batch Photos taken (Example: TimeLapse batches, burst batches, continouous photo batches...)
- 37 - Number of videos shot
- 38 - Number of ALL photos taken
- 39 - Number of ALL videos taken
- 8 = Recording/Processing status:
  - 0 = Not recording/Processing
  - 1 = Recording/processing
- 54 - Remaning free space on memorycard in bytes
