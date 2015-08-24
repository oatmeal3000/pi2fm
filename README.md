README:

Page numbers in comments refer to
http://www.raspberrypi.org/wp-content/uploads/2012/02/BCM2835-ARM-Peripherals.pdf

Build Command:
$ gcc -lm -std=c99 -g pi2fm.c -o pi2fm

Usage:
pi@raspberrypi $ sudo ./pi2fm sound.wav 77.7

pi@raspberrypi $ avconv -i sound.mp3 -f s16le -ar 22.05k -ac 1 - | sudo ./pi2fm -

pi@raspberrypi $ arecord -l
**** List of CAPTURE Hardware Devices ****
card 1: Device [USB PnP Sound Device], device 0: USB Audio [USB Audio]
  Subdevices: 1/1
  Subdevice #0: subdevice #0


pi@raspberrypi $ arecord -D plughw:1,0 -f S16_LE -r 22050 | sudo ./pi2fm -


