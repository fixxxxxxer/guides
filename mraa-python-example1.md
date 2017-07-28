# Running a Libmraa Python example on your DragonBoard 410c

This guide will help you execute a simple python code using libmraa. 

## Step 1: Hardware Setup:

### Hardware Requirements:

1. [DragonBoard 410c](https://www.96boards.org/product/dragonboard410c)
2. [Grove Sensors Mezzanine](http://www.96boards.org/product/sensors-mezzanine/)
3. [LED](https://www.seeedstudio.com/Grove-LED-p-767.html)
4. [Grove Universal 4 Pin Cable](https://www.seeedstudio.com/Grove---Universal-4-Pin-20cm-Unbuckled-Cable-%285-PCs-Pack%29-p-749.html)

### Hardware Connections:

1. Make sure that the DragonBoard 410c is initially unplugged (powered off)
2. Conect the Sensors Mezzanine  to DragonBoard 410c through the 40 pin low-speed expansion connector. Mezzanine board (male pins) will match 1-to-1 with female pins on DragonBoard 410c connector. Make sure all 40 pins are lined up properly before moving to next step.
3. If you wish to use the serial console from your host machine, connect USB cable to host machine and microUSB on mezzanine board (USB Type-A end of cable connects to host machine, microUSB end of cable connects to microUSB port on Mezzanine.
If you wish to use the Linux Desktop, connect a mouse and a keyboard on the USB ports available on the DragonBoard. USe the HDMI port to connect your device to a monitor. 
4. Attach the LED to GPIO 23.

## Step 2: Software Setup:

### Downloading and installing libmraa (if you don't already have it)

> NOTE: If you already have libmraa, or if you are unsure, you should run this command to guarantee it's avilability on your DragonBoard 410c

```
$ git clone https://github.com/intel-iot-devkit/mraa
$ cd mraa
$ mkdir build
$ cd build
$ cmake ..
$ make
$ sudo make install
$ sudo ldconfig /usr/local/lib/
```
### Getting the sample code and running it
This sample code is meant to blink an LED at a certain time interval. Follow the steps below to execute the code.

```
$ cd mraa
$ cd examples
$ cd python
$ vim blink-io8.py
```
You can go through the code in order to understand what is happening. Since we have connected the LED to GPIO 23, edit that in the code at line 28. 
```
x = mraa.Gpio(23)
```
Now execute the code
```
$ python blink-io8.py
```
Congratulations! You have executed your first python code using libmraa.
