# Install an X-server

X-servers are how Linux displays graphical applications. In order to do this not on Linux, we need
to install an X-server manually.

### If using Windows
For Windows users, first install VcXsrv from [here](https://sourceforge.net/projects/vcxsrv/). Once it's done
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

For MacOS, we have only one functional option: XQuartz.  It's based on the original libraries Apple packaged in Mac OSX 10.5 to 10.7 (which was subsequently removed).  It's not in the app store, but it is a signed package so installing it is fairly simple.  Just head to https://xquartz.org and download the stable `.dmg` file.  For Big Sur, you may have to log out and back in after installing for the module to attach to the terminal properly.

With that, X11 applications will pretty much automatically trigger XQuartz to start, so there's nothing you need to do.

### Testing your X-Server in WSL or Linux

If you'd like to confirm your X-server is set up correctly, launch it, open a terminal, and run the
following commands:
```
sudo apt update; sudo apt install -y x11-apps
xeyes
```
If everything is functioning, you should have a window with a pair of eyes that follow the cursor!

![image](https://user-images.githubusercontent.com/19244666/118378411-57a53280-b599-11eb-8840-1f77d6dd8646.png)
