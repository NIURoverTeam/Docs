## Dependencies
* ROS Melodic
* RoverCoreOS ar_tag_tracking branch
  * Run `git checkout ar_tag_tracking` from the RoverCoreOS directory.
* RealSense2 Wrapper and SDK

## Getting it Running
* Install the *alvar* package for ROS.
* The launch file to run with the RealSense is in RoverCoreOS
* When launching the realsense node, add `enable_tf_dynamic:=true` as the last parameter.
* Then, run `roslaunch launch/ar_tag_tracking.launch`
  * Make sure you're in the path `catkin_ws/src/RoverCoreOS/`.
* That should run just tasty.
* You can use `rostopic echo /ar_pose_marker` to see the number that'll make it work.

## RViz Instructions
* `rosrun rviz rviz`
* Make sure under `Global Options` set `Fixed Frame` to `camera_link`.
* Add a Marker Display and make sure the marker topic is `visualization_marker`.
* Add a Camera Display and set the image topic to `/camera/color/image_raw`
* Add a TF display and disable all frames, save for the `ar_marker_#` frames that will appear as you show it tags.