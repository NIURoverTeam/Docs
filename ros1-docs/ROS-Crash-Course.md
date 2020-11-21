# ROS Crash Course

## Introduction

The NIU Mars Rover Team develops for our Rovers using the open source [Robotic Operating System (ROS)](http://www.ros.org). While not a true operating system, generally running on Ubuntu or other Linux distributions, ROS is a package-based development stack that allows roboticists and developers to take advantage of a wide assortment of preexisting robotics software without the need to reinvent the proverbial wheel. It's a flexible, extensible, and powerful tool, but it comes at the price of having a decently steep learning curve. That said, there's a vast array of resources and tools out there aimed at getting newbies and veteran developers alike up and running on ROS, so don't be afraid to jump in and start learning.

Installed ROS already? If not, check out [Setting Up a Development Environment](Setting-Up-a-Development-Environment).

## [ROS.org Tutorials](http://wiki.ros.org/ROS/Tutorials)

The best way to learn ROS is to dig into the extensive tutorials, linked above, on the organizations main wiki page.

### Recommended Tutorials to Get Started

Note: These are *only* recommendations. If you want, you can certainly do more, and you should feel free to defer or entirely ignore tutorials that you don't think will be useful to you. The goal here is not to give you more homework than you already have, but to give you the resources you need to start developing as quickly as possible.

* Beginner Level
    * [Installing and Configuring Your ROS Environment](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment)
    * [Navigating the ROS Filesystem](http://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem)
    * [Creating a ROS Package](http://wiki.ros.org/ROS/Tutorials/CreatingPackage)
    * [Building a ROS Package](http://wiki.ros.org/ROS/Tutorials/BuildingPackages)
    * [Understanding ROS Nodes](http://wiki.ros.org/ROS/Tutorials/UnderstandingNodes)
    * [Understanding ROS Topics](http://wiki.ros.org/ROS/Tutorials/UnderstandingTopics)
    * [Understanding ROS Services and Parameters](http://wiki.ros.org/ROS/Tutorials/UnderstandingServicesParams)
    * [Using rqt_console and roslaunch](http://wiki.ros.org/ROS/Tutorials/UsingRqtconsoleRoslaunch)
    * [Using rosed to edit files in ROS](http://wiki.ros.org/ROS/Tutorials/UsingRosEd)
    * [Writing a Simple Publisher and Subscriber (Python)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29)
    * [Examining the Simple Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber)
    * [Examining the Simple Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/WritingServiceClient%28python%29)
    * [Examining the Simple Service and Client](http://wiki.ros.org/ROS/Tutorials/ExaminingServiceClient)
    * [Recording and playing back data](http://wiki.ros.org/ROS/Tutorials/Recording%20and%20playing%20back%20data)
    * [Getting started with roswtf](http://wiki.ros.org/ROS/Tutorials/Getting%20started%20with%20roswtf)
* Intermediate Level
    * [Managing System dependencies](http://wiki.ros.org/ROS/Tutorials/rosdep)
    * [Roslaunch tips for large projects](http://wiki.ros.org/ROS/Tutorials/Roslaunch%20tips%20for%20larger%20projects)
    * [Running ROS across multiple machines](http://wiki.ros.org/ROS/Tutorials/MultipleMachines)
* Specific ROS Libraries/Packages
    * [Modeling Robots with URDF](http://wiki.ros.org/urdf/Tutorials)
    * [Visualization with Rviz](http://wiki.ros.org/visualization/Tutorials)
    * [Navigation](http://wiki.ros.org/navigation/Tutorials)

## Tips and Tricks

* Follow the RoverCoreOS README.md instructions to get ready to work with the Rover's code.
* Make sure you're always running `source /opt/ros/melodic/setup.bash` and `source ~/catkin_ws/devel/setup.bash` before working with ROS. We strongly recommend adding them to the end of your `~/.bashrc` file.

## Other Links
* [Robot Ignite Academy](https://www.robotigniteacademy.com/en/path/ros-for-beginners/): Good for if you don't have a machine that can run ROS, tutorials can be run entirely in the browser.
* [ROS101: An Intro to the Robot Operating System](https://www.designnews.com/gadget-freak/ros-101-intro-robot-operating-system/107053141061075): A beginner friendly run down.
* [ROS web tutorial part 1 - rosbridge server and roslibjs](https://msadowski.github.io/ros-web-tutorial-pt1/): An interesting web based approach to working with ROS.
* [Introduction to Simultaneous Localization and Mapping](https://towardsdatascience.com/slam-intro-fd833ef29e4e): Good primer if you want to work on the Autonomous Navigation.
* [How does Autonomous Driving Work? An Intro into SLAM](https://towardsdatascience.com/slam-intro-fd833ef29e4e)