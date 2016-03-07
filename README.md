# ROSsensory
Object sensory for ROS

This will control the Observer A and the object O seperetely.

Dependencies:
sudo apt-get install ros-indigo-rtabmap ros-indigo-rtabmap-ros

start:
roslaunch openni_launch openni.launch depth_registration:=true

roslaunch rtabmap_ros rgbd_mapping.launch rtabmap_args:="--delete_db_on_start" rviz:=true rtabmapviz:=false

resetMem:
use action "Edit->Delete memory" OR rosservice call /rtabmap/reset



Changes made:

gazebo::
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu trusty main" > /etc/apt/sources.list.d/gazebo-latest.list'
wget http://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -
*update ubuntu*

update ssh file in usr/share/gazebo
export GAZEBO_MODEL_DATABASE_URI=http://old.gazebosim.org/models

Kabuki::
	Followed kabuki install:
	http://wiki.ros.org/kobuki/Tutorials/Installation
		sudo apt-get install ros-indigo-kobuki ros-indigo-kobuki-core
		roslaunch kobuki_node minimal.launch
	...didn't work

	so now:
	http://wiki.ros.org/kobuki_gazebo
		sudo apt-get install ros-indigo-kobuki-desktop
		roslaunch kobuki_gazebo kobuki_empty_world.launch
		roslaunch kobuki_keyop keyop.launch
	Works pretty well

kinect::
	(using the one in turble bot)
	sudo apt-get install ros-indigo-turtlebot ros-indigo-turtlebot-apps ros-indigo-turtlebot-interactions ros-indigo-turtlebot-simulator ros-indigo-kobuki-ftdi ros-indigo-rocon-remocon ros-indigo-rocon-qt-library ros-indigo-ar-track-alvar-msgs

	