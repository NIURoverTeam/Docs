# Setting up the Jetson Nano

## Some Notes on Powering the Jetson

There are 3 ways to Power the Jetson Nano:

1. The DC5V 2A barrel jack connector. We don't currently have a suitable powersupply for this, so you likely will not be using it.
2. The Micro USB port. There's a 2-pin jumper that needs to be removed, and the powersupply must supply at least 5V at 1.5A. The Jetson is very particular about its power and many 5V power supplies won't actually work because of transmission losses.
3. Two 5V pins on the GPIO. Each can support 1.5A independently, or up to 3A total when combined. Allows the board to draw the maximum amount of power, but requires jumper pins and a reliable power source (DON'T CONNECT DIRECTLY TO 22.2V LIPOS)

1. Follow the [Jetson Nano Getting Started Guide](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit) to get the operating system installed.
1. Put the SD card in and power up the Nano. Create a user and all that.
2. Install any updates that need to be installed.
3. Install Docker using [this guide ](https://dev.to/rohansawant/installing-docker-and-docker-compose-on-the-jetson-nano-4gb-2gb-in-2-simple-steps-1f4i) (you can remove the Docker-Compose bits).
4. Install an ssh server with `sudo apt install ssh`
5. Install the [xpad](https://github.com/paroj/xpad) or [xpadneo](https://github.com/atar-axis/xpadneo) driver for the xbox controller (use the latter for bluetooth, which you'll also need a bluetooth dongle for)
6. Anytime you want to run ROS2, use the ros2-foxy-jetson container from our [Dockerfiles](https://github.com/NIURoverTeam/Dockerfiles/tree/master/ros2_foxy_jetson)

## Some Notes about the Jetson's Limitations

1. The HDMI port on the Jetson does not play nice with HDMI to DVI or VGA adapters.
