# AUV Exploration

Collection of ROS packages for localization, map building and SLAM with autonomous underwater vehicles and sonar sensing.

## Dependencies (tested on Ubuntu 16.04 and 18.04)
* AUVLIB [here](https://github.com/nilsbore/auvlib) 
* Bathymetric SLAM [in the private gitr] (https://gitr.sys.kth.se/torroba/bathymetric_slam)
* UFOMap [here](https://github.com/ignaciotb/UFOMap.git)

## Building

This is a collection of ROS packages. Just clone the repo within your catking workspace and run
```
catkin_make -DCMAKE_BUILD_TYPE=Release install
```
If you've managed to install the dependencies, this part should be pretty easy.

## ROS Packages

## Usage
So far, the online command line utility is
```
roslaunch auv_model auv_exploration.launch
```
Open RVIZ separately and use the config file in the bathy_mapper pkg to visualize the setup.

Keep reading to see how to change the operation mode.

### Replay an AUV survey 
Construct and store a bathymetric map from a real AUV survey as a UFOmap. 
Modify the launch file 'auv_exploration.launch' under the auv_model package: change the parameter `mode = gt`

### Simulate AUV missions based on existing bathymetry 
Use the bathymetric map constructed previously and an AUV with an MBES simulation to create your own missions. 
Modify the launch file 'auv_exploration.launch' under the auv_model package: change the parameter `mode = sim`

After launching the system, click on the black screen that pops up and use the following commands to navigate the simulated AUV:
- w/s forwards/backward throtle
- right/left keys: steering
- up/down keys: inclination




