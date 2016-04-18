###HERO4 Session Specific Notes and Commands

The GoPro HERO4 Session is a simplified version of the popular HERO camera. Because of this the camera only responds to GET requests when is in APP mode, to turn the camera to APP mode send a magic packet (WoL) with these parameters: MAC ADDRESS OF THE CAMERA, 10.5.5.9 as IP ADDRESS, Subnet Mask 255.255.255.0, Port 9. For the Hero4 Session, this magic packet has to be sent when your project wants to operate with the camera.

And to check that you have access to the camera, GET the status of the camera (more info on CameraStatus.md)
