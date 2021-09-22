## Enabling Windows Subsystem For Linux 2 (WSL2)

> For reference, these instructions are adapted from the
[Windows Subsystem for Linux Installation Guide for Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

First things first, we're going to enable something called WSL2. It lets you run a full Linux
Distribution and Kernel on Windows 10. Note: you NEED to have Windows 10 Version 2004 or higher
for this to work. Otherwise, you'll only be able to run WSL1, which will NOT work for this. If
you can't update from the "Check for Updates" page in Settings, try the 
[Windows 10 Update Assistant](https://www.microsoft.com/en-us/software-download/windows10).

Assuming you're running an acceptable version of Windows 10, we next need to turn on an 
optional Windows Feature. Open the Start Menu and search for "Turn Windows features on or off".
Select the corresponding option, find "Windows Subsystem for Linux" in the list, and check it.
You'll likely have to restart your computer after it completes. If it's already checked, great!

Next, install 
[Ubuntu from the Microsoft Store](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6?activetab=pivot:overviewtab). 
You may also want to grab the "Windows Terminal (Preview)" while you're there.

Once Ubuntu is installed and ready to go, hit `Win + R` and type `cmd`. Hit enter, then run 
this command: `wsl --set-version Ubuntu 2`. This will make sure you're running Ubuntu in WSL2
and not WSL1.

Now you can launch Ubuntu, either directly or inside the Windows Terminal, and set up the 
default user.
