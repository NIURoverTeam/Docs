# What and Why?

For this guide, you'll learn how to get the Robotic Operating System 2 up and running in Docker. 
In order to do that, there's two key components that you have to understand: Docker, and ROS2.

## Docker

Docker is what's called a "containerization tool".  This article gives a great explanation of 
Docker, using burritos and pizza as an analogy:
[What _**is**_ Docker?](https://dev.to/javascriptcoff1/what-is-docker-3be2) Give it a read, it's
quite fun and informative as well.
<!---
If you're familiar with Virtual Machines, 
containers are kind of like tiny little lightweight VMs, but which leverage as much of the host
operating system and kernel as they can get away with. If you're not familiar with VMs, just 
think of it like a mini-computer running inside your computer, which is used to do a specific 
set of things. What's nice about Docker is it gives you nice things like the ability to run 
code targeted for one operating system easily on another, easily reproducible environments, 
dependency management, and isolated development.
--->

## ROS2

The Robotic Operating System 2 (ROS2) is "a set of software libraries and tools for building robot 
applications". It's a really powerful tool for developing the software that makes robots do 
things, and has many, many packages for interfacing with different hardware, incorporating 
advanced robotics techniques like autonomous navigation and inverse kinematics, and much 
more. ROS2 is the new-and-improved successor to the original ROS.

# Getting Set Up

Now that we've got that out of the way, let's get a move on.

## A Note on Operating Systems and Platforms

This guide definitely works for the latest version of Windows 10 and Ubuntu 18.04/20.04.
It **should** work for most distributions of Linux. MacOS hasn't been tested yet, so it might
need some tweaking. I'll note when I'm giving Windows specific instructions, Linux users you
can skip these parts.

## Getting Your Computer Ready

Follow the following guides to get set up:
1. [Setting Up WSL2](https://github.com/NIURoverTeam/Docs/blob/main/Guides/Setting-Up-WSL2.md) (skip if you're a Mac or Linux user)
1. [Installing an X-server](https://github.com/NIURoverTeam/Docs/blob/main/Guides/Installing-an-X-Server.md) (skip if you're a Linux user)
1. [Installing Docker](https://github.com/NIURoverTeam/Docs/blob/main/Guides/Installing-Docker.md)

# Run ROS2 in Docker

Finally, change to whatever directory you use to do work in, and run 
`git clone https://github.com/NIURoverTeam/Dockerfiles.git` (you may need to install git 
first). After that, `cd Dockerfiles/ros2_foxy`, and follow the instructions in the 
[README.md](https://github.com/NIURoverTeam/Dockerfiles/blob/master/ros2_foxy/README.md). 
Once you follow all the steps, you should have successfully run ROS2 inside a Docker Container!
