# I<sup>2</sup>C Development Crash Course

## Introduction

**Inter-Integrated Circuit (I<sup>2</sup>C)** 
* Pronounced "Eye Squared See"
* A hardware communications protocol which allows us to simply and efficiently transfer data between multiple devices.
* [Basics of the I<sup>2</sup>C Communication Protocol](http://www.circuitbasics.com/basics-of-the-i2c-communication-protocol/): A good primer to understand how the actual protocol works.

## Development Tips

To determine the I<sup>2</sup>C address of a device connected to the TX2 on Ubuntu:

* `sudo apt-get install libi2c-dev i2c-tools`
* `sudo i2cdetect -y -r 0`

The device address will be shown in the table output as a two digit hex character (ignore u characters).

In python, we use the `python-smbus` package, which you can find some docs for [here](http://wiki.erazor-zone.de/wiki:linux:python:smbus:doc).


## Orbitty Carrier Pin Layout

Quick and dirty guide to the pin layout used on the carrier board we use for the Nvidia Jetson TX2.

|      |    |
|------|----|
|  1   | 2  |
|  3   | 4  |
|  5   | 6  |
|  7   | 8  |
|  9   | 10 |
| **11** | **12** |
|  13  | 14 |
|  15  | 16 |
|  17  | 18 |
|  19  | **20** |

Pin 11: `SCL`: Serial Clock

Pin 12: `SDA`: Serial Data

Pin 20: `GND`: Ground