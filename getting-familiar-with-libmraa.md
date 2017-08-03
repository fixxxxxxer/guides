# Getting familiar with libmraa 
This guide helps the user get familiar with libmraa on a DragonBoard 410c. This guide will show you how to successfully install the mraa library and run a simple example in order to test it.

# Hardware requirements:
1. [DragonBoard 410c](https://www.96boards.org/product/dragonboard410c)
2. [Grove Sensors Mezzanine](http://www.96boards.org/product/sensors-mezzanine/)
3. [Grove Relay](http://wiki.seeed.cc/Grove-Relay/)
4. [Grove - Touch Sensor](http://wiki.seeed.cc/Grove-Touch_Sensor/)
5. [Grove Universal 4 Pin Cable](https://www.seeedstudio.com/Grove---Universal-4-Pin-20cm-Unbuckled-Cable-%285-PCs-Pack%29-p-749.html)

# Hardware Setup:
In order to test an example we will be using a Sensors Mezzanine and a relay and a touch sensor. 
1. Make sure that the DragonBoard 410c is initially unplugged (powered off)
2. Conect the Sensors Mezzanine  to DragonBoard 410c through the 40 pin low-speed expansion connector. Mezzanine board (male pins) will match 1-to-1 with female pins on DragonBoard 410c connector. Make sure all 40 pins are lined up properly before moving to next step.
3. Attach the relay to G2.
4. Attach the touch sensor to G3.

# Software Setup:
There are two ways to install the mraa library. For the first one, run the follwing commands on the CLI.
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
For the second method, use the instruction given below:
```
$ sudo apt-get install libmraa-dev
```
Now that we have successfully installed the library, lets run an example code to test it. To do the same, 
```
$ git clone https://github.com/96boards/Starter_Kit_for_96Boards
$ cd touch_switch
$ make
$ ./touch_switch
```
Congratulations! You have downloaded and installed libmraa to your DragonBoard 410c and run an example code on it. If you explore the [mraa repository ](https://github.com/intel-iot-devkit/mraa) you will find more examples to help you get started with mraa library. 
