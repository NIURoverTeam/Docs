# Setting Up a Development Environment

Rover 2.0 runs on the open source [Robotic Operating System](https://www.ros.org), specifically the latest LTS version dubbed Melodic Morena. Which can be installed on Linux (ideally Ubuntu), Windows, or Mac (through Homebrew).

### Installing Ubuntu

[Install Ubuntu](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop), preferably version 18.04 Bionic Beaver.

If you're unfamiliar with Linux or the command line, we recommend running through our [Bash Crash Course](Bash-Crash-Course) at some point.

## Installing ROS

Once you have a working Linux distro, you can install a version of ROS. We currently target Melodic.

* **[ROS Melodic Install Page](http://wiki.ros.org/melodic/Installation)**

Follow the instructions for your current OS. Once installed, consider checking out our [ROS Crash Course](ROS-Crash-Course).

## Condas and Jupyter Notebooks/Lab

[The Jupyter Project](https://jupyter.org/) provides tools to run interactive notebooks for interpreted languages, such as Python. To get started, follows these steps:

1. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
1. Next, follow the [JupyterLab install instructions](https://jupyter.org/install.html) for conda
1. Then, follow the instructions to install the [ROS Jupyter extension](https://github.com/RoboStack/jupyter-ros#installation-and-dependencies), specifically for JupyterLab

## Editors

We highly recommend installing [Visual Studio Code](https://code.visualstudio.com/) or [Atom](https://atom.io/) to use as your primary code editor. Both are highly customizable and extensible, and have extensions available for ROS.