## Dependencies 
Before you install Tensorflow and the ROS package in the next step, make sure you have ROS and the required Realsense software installed. The home page [here ](https://github.com/NIURoverTeam/RoverCoreOS) has the instructions for that. 

## Installation
The two main things you're going to need to install are TensorFlow and the ROS package that will work with it. 

Instructions on how to install TensorFlow can be found [here.](https://www.tensorflow.org/install/pip?lang=python2) Double check to make sure you're following the instructions for Python 2.7, not 3. 

The ROS Object Detection package can be found [here. ](https://github.com/cagbal/ros_people_object_detection_tensorflow)

## Setting Parameters
You're going to need to pick a model for the package to use. Currently, we're using a model named `faster_rcnn_inception_v2_coco_2018_01_28`. 
Different models can be installed from the [Model Zoo. ](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md)

Model files should be extracted into `catkin_ws/src/cob_people_object_detection_tensorflow/src/object_detection`

### To update the model: 
cd into
`catkin_ws/src/cob_people_object_detection_tensorflow/launch` and open 
`launch/cob_people_object_detection_tensoflow_params.yaml` in a file editor. 

From there, just copy and paste the new model name into the file. 

Note: If it's your first time running this package, you'll probably need to update the topics for your camera. For the RealSense, the RGB image topic will likely need to be changed to `/camera/color/image_raw`.

## Running 
First, turn the RealSense on with `roslaunch realsense2_camera rs_camera.launch`

Next, in a new terminal, start the TensorFlow virtual environment with `source ./venv/bin/activate`.

After that, you're good to run the Object Detection package with `roslaunch cob_people_object_detection_tensorflow alltogether.launch`.
