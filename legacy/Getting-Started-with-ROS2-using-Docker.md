# What and Why?

For this guide, you'll learn how to get the Robotic Operating System 2 up and running in Docker. In order to do that, there's two key components that you have to understand: Docker, and ROS2.

## Docker

Docker is what's called a "containerization tool". If you're familiar with Virtual Machines, containers are kind of like tiny little lightweight VMs, but which leverage as much of the host operating system and kernel as they can get away with. If you're not familiar with VMs, just think of it like a mini-computer running inside your computer, which is used to do a specific set of things. What's nice about Docker is it gives you nice things like the ability to run code targeted for one operating system easily on another, easily reproducible environments, dependency management, and isolated development.

## ROS2

The Robotic Operating System 2 is "a set of software libraries and tools for building robot applications". It's a really powerful tool for developing the software that makes robots do things, and has many, many packages for interfacing with different hardware, incorporating advanced robotics techniques like autonomous navigation and inverse kinematics, and much more. ROS2 is the new-and-improved successor to the original ROS.

# Getting Setup

Now that we've got that out of the way, let's get a move on.

## A Note on Operating Systems and Platforms

This guide definitely works for the latest version of Windows 10 and Ubuntu 18.04/20.04. It **should** work for most distributions of Linux. MacOS hasn't been tested yet, so it might need some tweaking. I'll note when I'm giving Windows specific instructions, Linux users you can skip these parts.

## Getting Windows Ready

**Note: This is one of those sections Linux users can skip**

## Enabling Windows Subsystem For Linux 2 (WSL2)

First things first, we're going to enable something called WSL2. It lets you run a full Linux Distribution and Kernel on Windows 10. Note: you NEED to have Windows 10 Version 2004 or higher for this to work. Otherwise, you'll only be able to run WSL1, which will NOT work for this. If you can't update from the "Check for Updates" page in Settings, try the [Windows 10 Update Assistant](https://www.microsoft.com/en-us/software-download/windows10).

Assuming you're running an acceptable version of Windows 10, we next need to turn on an optional Windows Feature. Open the Start Menu and search for "Turn Windows features on or off". Select the corresponding option, find "Windows Subsystem for Linux" in the list, and check it. You'll likely have to restart your computer after it completes. If it's already checked, great!

Next, go to the Microsoft Store and search for "Ubuntu". Install it. You may also want to grab the "Windows Terminal (Preview)" while you're there, if you want a terminal that doesn't suck.

Once Ubuntu is installed and ready to go, hit `Win + R` and type `cmd`. Hit enter, then run this command: `wsl --set-version Ubuntu 2`. This will make sure you're running Ubuntu in WSL2 and not WSL1.

Now you can launch Ubuntu, either directly or inside the Windows Terminal, and set up the default user.

## Install an X-server

X-servers are how Linux displays graphical applications. In order to do this on Windows, we need to install an X-server, since Windows does not include one by default.

First, install VcXsrv from [here](https://sourceforge.net/projects/vcxsrv/). Once it's done installing, launch it and use these parameters in the configuration dialog: Display Number -1, "Start no Client", "Disable access control" (everything else leave as the default). You'll have to do this every time you want to use graphical applications.

In WSL, you'll need to run `export DISPLAY=$(grep -m 1 nameserver /etc/resolv.conf | awk '{print $2}'):0.0`. Either run it every time you want to launch Docker, or add it to your `~/.bashrc` so it gets run automatically.

# Install Docker

Now, we need to install Docker on our machine or in WSL.

## Docker Account

Regardless of the operating system you're using, you'll need to register for a docker account at [hub.docker.com](https://hub.docker.com). Yuck, I know, but it is what it is.

## Docker Engine Installation

Now, we get to install the Docker Engine. Follow the instructions [here](https://docs.docker.com/engine/install/ubuntu/), using the "Install using the repository" instructions, preferably, to do that. NOTE: REGARDLESS OF WHETHER YOU'RE USING WINDOWS OR LINUX, INSTALL THE LINUX VERSION. If you're on Windows, follow the Ubuntu instructions **inside** WSL. If you're on Ubuntu, just do it in your terminal. If you're on a different distro, like Fedora, find the appropriate page on the left.

Once you've completed the instructions and installed docker, go to [the post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/) and follow "Manage Docker as a non-root user".

**Note for windows users: WSL doesn't natively support the systemd service that docker uses to automatically start, so we'll have to do it ourselves. To start docker for the current instance, run `sudo service docker start`. Then you should be able to run docker commands as expected. For it to automatically start with WSL, run `sudo crontab -e` and add this line to the very end of the file: `@reboot service docker start`.**

Now, to test our docker setup. First, run `docker login` and provide your Docker Hub credentials. Then, run `docker run hello-world` to make sure everything is working properly.

# Run ROS2 in Docker

Finally, change to whatever directory you use to do work in, and run `git clone https://github.com/NIURoverTeam/Dockerfiles.git` (you may need to install git first). After that, `cd Dockerfiles/ros2_foxy`, and follow the instructions in the [README.md](https://github.com/NIURoverTeam/Dockerfiles/blob/master/ros2_foxy/README.md). Once you follow all the steps, you should have successfully run ROS2 inside a Docker Container!