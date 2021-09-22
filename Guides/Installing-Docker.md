# Install Docker

Now, we need to install Docker on our machine or in WSL.

## Docker Account

Regardless of the operating system you're using, you'll need to register for a docker account 
at [hub.docker.com](https://hub.docker.com). Yuck, I know, but it is what it is.

## Docker Engine Installation

Now, we get to install the Docker Engine. Follow the instructions 
[here](https://docs.docker.com/engine/install/ubuntu/), using the "Install using the repository"
instructions, preferably, to do that. NOTE: REGARDLESS OF WHETHER YOU'RE USING WINDOWS OR 
LINUX, INSTALL THE LINUX VERSION. If you're on Windows, follow the Ubuntu instructions **inside**
WSL. If you're on Ubuntu, just do it in your terminal. If you're on a different distro, like 
Fedora, find the appropriate page on the left.

Once you've completed the instructions and installed docker, go to 
[the post-installation steps](https://docs.docker.com/engine/install/linux-postinstall/) 
and follow "Manage Docker as a non-root user".

**Note for windows users: WSL doesn't natively support the systemd service that docker uses 
to automatically start, so we'll have to do it ourselves. To start docker for the current 
instance, run `sudo service docker start`. Then you should be able to run docker commands 
as expected. For it to automatically start with WSL, see our 
[Docker autostart guide](https://github.com/NIURoverTeam/Docs/blob/main/Tips-n-Tricks/docker-autostart.md).**

Now, to test our docker setup. First, run `docker login` and provide your Docker Hub 
credentials. Then, run `docker run hello-world` to make sure everything is working properly.
