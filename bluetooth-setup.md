# Setting up a Bluetooth device on your DragonBoard 410c

This guide will help you set up any Bluetooth device with your DragonBoard 410c. It will go over the two ways to do the same; first through serial console if you use ssh to access your board and the other using a monitor, keyboard and mouse with the DragonBoard410c and use the available Linux desktop.

## Hardware Requirements:

1. [DragonBoard 410c](https://www.96boards.org/product/dragonboard410c)
2. The bluetooth device you wish to connect to DragonBoard 410c

Since we are trying to establish a wireless connection, there isn't a hardware setup required for the bluetooth device and the DragonBoard. Just make sure that the Bluetooth device is ON and well within its connectivity range with the DragonBoard.

## Establishing the connection:
As mentioned above, this guide will discuss two ways to establish a bluetooth connection, one via the command line interface and another via the desktop.

### Command line interface:

Run the following commands on the command line interface to establish a connection between the DragonBoard and the bluetooth device. 

```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install bluez
$ sudo apt-get install bluez-utils
$ bluetoothctl
[bluetooth]# agent KeyboardOnly 
Agent registered
[bluetooth]# default-agent 
Default agent request successful
[bluetooth]# scan on
Discovery started
[CHG] Controller 00:10:20:30:40:50 Discovering: yes
[NEW] Device 00:12:34:56:78:90 myLino
[CHG] Device 00:12:34:56:78:90 LegacyPairing: yes
[bluetooth]# pair 00:12:34:56:78:90
Attempting to pair with 00:12:34:56:78:90
[CHG] Device 00:12:34:56:78:90 Connected: yes
[CHG] Device 00:12:34:56:78:90 Connected: no
[CHG] Device 00:12:34:56:78:90 Connected: yes
Request PIN code
[agent] Enter PIN code: 1234
[CHG] Device 00:12:34:56:78:90 Paired: yes
Pairing successful
[CHG] Device 00:12:34:56:78:90 Connected: no
[bluetooth]# connect 00:12:34:56:78:90
Attempting to connect to 00:12:34:56:78:90
[CHG] Device 00:12:34:56:78:90 Connected: yes
Connection successful
```

### Linux Desktop:

First, power on your DragonBoard 410c with 96Boards compliant power supply
When the system starts, open Bluetooth Manager and turn ON the Bluetooth. Click on 'search' so that the DragonBoard can start scanning for nearby devices. Once the name of your device appears, right click on it and click on 'pair'. Finally, after pairing, click on 'connect'.

Congratulations! You have successfully made a bluetooth connection between the DragonBoard and your Bluetooth device.

# References:
[Bluetooth ArchLinux](https://wiki.archlinux.org/index.php/bluetooth)