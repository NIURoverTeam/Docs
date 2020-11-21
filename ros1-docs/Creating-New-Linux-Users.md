# Creating New Linux Users

New users can be created on Shatterdome (the base station) or the TX2 by any current user with sudoer privileges. The steps are as follows:

1. `adduser <username>`, replacing `<username>` with the name of the user you want to create.
1. Enter the required information.
1. `usermod -aG sudo,dialout,tty,i2c,docker <username>`
1. Login to the new user.
1. Enjoy!