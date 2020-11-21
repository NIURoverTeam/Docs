## Installation
The package that controls the 3DConnexion SpaceNavigator 3D Mouse is [spacenav_node](http://wiki.ros.org/spacenav_node). To install this package, **ssh into shatterdome** and then run:

```ubuntu
$ sudo apt install spacenavd
$ sudo apt install ros-<distro>-spacenav-node
```
- Note: The [spacenav_node documentation](http://wiki.ros.org/spacenav_node) uses `indigo` in place of the distribution instead of just saying `<distro>`. Don't be tricked by their silly little lies

## Using the spacenav_node package

Go to the shatterdome machine and log in (*ssh will not work for these next steps*). Plug in the 3D mouse, open a new terminal, and run `roslaunch spacenav_node classic.launch`. 

- If this is your first time accessing the shatterdome machine, you will likely get an error when you attempt to do this because the ROS environment is not set up on your user account. Use the [Installing and Configuring ROS Environment tutorial](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) to set this up and then run `roslaunch spacenav_node classic.launch` again.

There are 4 topics that `spacenav_node` publishes to. To view any of the topics, **open a new terminal** and use either `rostopic echo /<topic_name>` to view messages published to the topic, or `rostopic echo -c /<topic_name>` to view messages published and have the screen cleared between each update, which is more readable.
The topics are as follows:

- `spacenav/offset`: This is the linear component of the joystick's position. Of the 3 linear axes, **each linear axis is ±0.68359375 individually** (i.e. pushing or pulling the z axis to its fullest extent would give the ±0.6 ish number regardless of the x and y), and together they are approximately normalized to a range of -1 to 1.
- `spacenav/rot_offset`: Same deal as spacenav/offset, but this topic is the angular component. Of the 3 rotational axes, **each rotational axis is ±0.68359375 individually**, and together they are approximately normalized to a range of -1 to 1.
- `spacenav/twist`: Package summary says it `combines offset and rot_offset into a single message`, it does in fact do that
- `spacenav/joy`: This topic displays all the information received from the 3D mouse, including the header, 6 degrees of freedom, and 2 buttons. The stuff in the header is the time the data is received from the joystick. For the axes, they are as follows: `[linear x, linear y, linear z, angular x, angular y, angular z]`. If holding the 3D mouse so the cord is pointing toward your body and the logo is pointing away, then the buttons are as follows: `[right button, left button]`.