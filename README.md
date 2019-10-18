# camera-by-rosterclub
camera by rosterclub

camera by roster For enabling camera in Raspberry Pi, open raspberry pi configuration using following command, sudo raspi-config

then select Interfacing options in which select camera option to enable its functionality. Reboot Raspberry Pi.

You can capture an image by just typing a single line command. Open terminal window and type the command as follows: $ sudo raspistill –o /home/pi/Desktop/image.jpg

Python Program for Image Capture
#import time and picamera library 
import picamera 
from time import sleep

#create object for PiCamera class 
camera = picamera.PiCamera()

#set resolution 
camera.resolution = (1280, 720) 
camera.brightness = 60 
camera.start_preview()

#Camera warmup time 
sleep(2)

#store image 
camera.capture('/home/pi/Pictures/image1.jpeg') 
camera.stop_preview()

Python Program for Video Recording 
import picamera 
from time import sleep

camera = picamera.PiCamera() 
camera.resolution = (1280, 720) 
camera.start_preview()

#start recording using pi camera 
camera.start_recording("/home/pi/demo.h264") 
sleep(20)

#stop recording 
camera.stop_recording() 
camera.stop_preview()
