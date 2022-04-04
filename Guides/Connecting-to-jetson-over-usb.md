# Connecting to the Jetson Nano over USB/Serial

## Instructions for MacOS

Locate the tty device

Before connecting to your Jetson developer kit for initial setup, check to see what Serial devices are already shown on your macOS computer.
```
$ ls /dev/cu.usbmodem*
~$
```
Connect your macOS computer to the developer kit’s Micro-USB port and run the same command to find what’s newly added.
```
~$ ls /dev/cu.usbmodem*
/dev/cu.usbmodem14133200001053
~$
```
The new serial device is for your Jetson developer kit.
```
~$ ls -l /dev/cu.usbmodem*
crw-rw-rw-  1 root  wheel   18,  19 Oct  2 03:54 /dev/cu.usbmodem14133200001053
~$
```
Screen command

Screen is already installed by default as part of macOS.

Use the device name discovered previously as a command line option for the `screen` command.
```
$ sudo screen /dev/cu.usbmodem14133200001053 115200
```
Terminate screen

To terminate your screen session, press C-a + k (Ctrl + a, then k), then press y on confirmation.
