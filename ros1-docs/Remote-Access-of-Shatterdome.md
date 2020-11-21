# Remote Access of Shatterdome

Shatterdome is the Mars Rover Team's Linux machine, which we often work on. Since you'll usually need to use Shatterdome without having physical access to it (it's in the Engineering Building), we need ways to connect remotely. Described below are options for accomplishing this.

## Using SSH

If you're **on-campus**, you can use the following command to connect:
* From WSL or the Windows Command Line: `ssh <username>@10.156.210.33`
* If you would like to open non-terminal programs as well, use `ssh -X <username>@10.156.210.33` instead

If you're **off-campus**, ssh won't work as described above. Instead, you have two options:
* One option is to install the AnyConnect VPN from [secure.niu.edu](https://secure.niu.edu/+CSCOE+/logon.html), and after it gets installed, connect to `secure.niu.edu` from the client. Then ssh as if you were on-campus (described above)
* The other option is to use one of the CSCI departmental servers, `turing` or `hopper`, as an intermediate destination. To do so, connect using either `ssh <your z-ID>@turing.cs.niu.edu` or `ssh <your z-ID>@hopper.cs.niu.edu`, with a lowercase "z" like `z1234567`. Then ssh into Shatterdome as if you were on-campus (described above). Advanced users can alternatively use ssh tunneling, which is more efficient but the same idea.
  > If this is your first time logging into turing or hopper, your default password will be in the format `NIU.YYYYMmmDD`, using your birthdate (for example, `NIU.2001Feb01` for someone born 2/1/2001). After you log in for the first time, IMMEDIATELY CHANGE YOUR PASSWORD to something other than the default, using the `passwd` command.

## Using TeamViewer

* Download and install the TeamViewer desktop client from [their site](https://www.teamviewer.com/en-us/)
* Log in with the account `NiuRover@gmail.com`. You'll have to request the password from the team lead.
* Go to "Computers & Contacts" in the desktop app, expand "Computers", and double click shatterdome. Enjoy
* **Note: only one person can be connected using TeamViewer at a time**