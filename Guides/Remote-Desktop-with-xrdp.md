> This doc is WIP

# What is xrdp?

[xrdp](http://xrdp.org/) is a tool which allows us to remotely access Shatterdome's desktop using 
RDP (Microsoft's Remote Desktop Protocol) from any operating systems. It allows multiple users to
log in at the same time, which is a perk over TeamViewer and NoMachine (tools we've used in the past).

# Installation

*  Windows 10
   * There's nothing to install - Windows 10 starts with it! The program is called `Remote Desktop Connection`.
* Windows 11
   * TODO
* MacOS
   * Install Microsoft Remote Desktop from the app store.
* Linux
   * TODO


# Connecting to Shatterdome while on NIU's network

Once you have it installed, use the following instructions (from 
[here](https://linuxconfig.org/ubuntu-20-04-remote-desktop-access-from-windows-10))
(tested on Windows 10):

1. Search for a program called `Remote Desktop Connection`.
   ![image](https://user-images.githubusercontent.com/19244666/151673679-91932c83-89af-4afb-9b17-b28f33c82374.png)
1. Click "Show Options" in the bottom-left corner.
2. Enter "10.156.209.2" as the Computer. Enter your username on shatterdome as the User name.
Optionally check "Allow me to save credentials" if you want that.
![image](https://user-images.githubusercontent.com/19244666/151673933-8900393f-3e2d-4d29-96aa-da6951433403.png)
6. Click Connect. Click `Yes` if asked about connecting when the identity of the remote computer
cannot be verified.
![image](https://user-images.githubusercontent.com/19244666/151674008-b7d67d0e-9a66-44c1-87e8-62b3be170845.png)
7. Enter your shatterdome password if it asks for one.
![image](https://user-images.githubusercontent.com/19244666/151674020-547a6ce8-ca19-479d-8bcd-0ddbd23f7efe.png)
8. You should now be remotely connected to Shatterdome.

### What to do if your xrdp is slow

My xrdp was very sluggish at first. To speed it up, I followed only instruction 1 from [this
StackOverflow answer](https://stackoverflow.com/a/45227464/13055399). You're welcome to follow the other
steps too, but I only needed to do the first one for a big improvement. For redundancy, here's the
step 1:

> 1. Change RDP settings, then run the RDP session and connect to the remote machine:
> ![image](https://user-images.githubusercontent.com/19244666/151674113-18912c81-adec-4c30-9829-361e16e9ea9d.png)

# Connecting to Shatterdome when not on NIU's network
Notes: 
```
mddmprovost@DESKTOP-21RFLUN:~ $ ssh -Y z1872355@hopper.cs.niu.edu -L 4000:localhost:4000
z1872355@hopper.cs.niu.edu's password:
Warning: No xauth data; using fake authentication data for X11 forwarding.
Linux hopper 4.19.0-18-amd64 #1 SMP Debian 4.19.208-1 (2021-09-29) x86_64
The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.
Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
You have mail.
Last login: Sun Jan  2 20:30:52 2022 from 73.50.58.118
z1872355@hopper:~ $ ssh -X drakeprovost@10.156.209.2 -L 4000:localhost:4000
drakeprovost@10.156.209.2's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.11.0-41-generic x86_64)
 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
341 updates can be applied immediately.
To see these additional updates run: apt list --upgradable
Your Hardware Enablement Stack (HWE) is supported until April 2025.
*** System restart required ***
Last login: Sun Jan  2 22:51:56 2022 from 10.158.56.120
drakeprovost@shatterdome:~ $
```

`Nomachine should connect to 127.0.0.1, or localhost, not shatterdome's ip`
