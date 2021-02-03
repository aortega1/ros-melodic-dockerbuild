# ros-melodic-dockerbuild
ros melodic docker build



## pull in the docker image, and run (docker-compose to follow)
docker run -it --rm osrf/ros:melodic-desktop-full roscore

command pulls osrf ros melodic desktop full image, and runs roscore init and starts

## the container doesn't kick off the catkin project initially, to do so:
1.  exec into the container
2.  run the following commands


echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
source ~/.bashrc

## create your package path and package, where my workspace/path examples are your mkdir paths (.e.g. mkdir ~/.catkin_workspace/src ) 

mkdir -p path_to_my_workspace/workspace_name/src
cd path_to_my_workspace/workspace_name/src
catkin_init_workspace
cd path_to_my_workspace/workspace_name/
------
catkin_make
-----
To compile for python3 instead use 
----------------  $ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3

source path_to_my_workspace/workspace_name/devel/setup.bash

## To validate env is built correctly
echo $ROS_PACKAGE_PATH
output - - -    /root/catkin_ws/src:/opt/ros/melodic/share


# following this tutorial for the rest of ROS testing/playing
http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment
