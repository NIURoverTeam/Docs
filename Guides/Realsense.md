# Installing the Intel Realsense SDK on Ubuntu 20.04

1. Download the latest release's "Source code (zip)" from [https://github.com/IntelRealSense/librealsense/releases](https://github.com/IntelRealSense/librealsense/releases)
1. Use `unzip` to extract the zip file, then `cd` into the resulting directory.
1. Install the neccessary dependencies: `sudo apt-get install build-essential libx11-dev git libssl-dev libusb-1.0-0-dev pkg-config libgtk-3-dev`
1. `mkdir build && cd build`
1. `cmake ../ -DFORCE_RSUSB_BACKEND=true -DCMAKE_BUILD_TYPE=release -DBUILD_EXAMPLES=true -DBUILD_GRAPHICAL_EXAMPLES=true`
1. `sudo make install`

And you're done!
