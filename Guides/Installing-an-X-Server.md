# Install an X-server

X-servers are how Linux displays graphical applications. In order to do this not on Linux, we need
to install an X-server manually.

### If using Windows
First, install VcXsrv from [here](https://sourceforge.net/projects/vcxsrv/). Once it's done
installing, launch it (it's named XLaunch) and use all the default parameters in the 
configuration dialog, except for the following modifications: uncheck "Native opengl," and
check "Disable access control." You'll have to do this every time you want to use graphical
applications (unless you save the configurations, in which case you'd run the executable 
`config.xlaunch` from your Start menu to boot the X-server with your saved settings).

![](https://i.imgur.com/1EJWKh5.png)

In WSL, you'll need to run 
`export DISPLAY=$(grep -m 1 nameserver /etc/resolv.conf | awk '{print $2}'):0.0`. 
Either run it every time you want to launch Docker, or add it to your `~/.bashrc` so it gets run 
automatically.

### If using MacOS

***placeholder***

### Testing your X-Server

If you'd like to confirm your X-server is set up correctly, launch it, open a terminal, and run the
following commands:
```
sudo apt update; sudo apt install -y x11-apps
xeyes
```
If everything is functioning, you should have a window with a pair of eyes that follow the cursor!

![image](https://user-images.githubusercontent.com/19244666/118378411-57a53280-b599-11eb-8840-1f77d6dd8646.png)
