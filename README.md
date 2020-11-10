# jackal_simulation_rob

Simulation for the Jackal robots at the University of Luebeck

##1. Install ROS kinetic
Follow: http://wiki.ros.org/kinetic/Installation/Ubuntu
##2. Install additional Jackal packages
```
sudo apt-get install ros-kinetic-jackal-simulator ros-kinetic-jackal-desktop ros-kinetic-jackal-navigation
```

##3. Create catkin workspace
In your home folder open a terminal and create your workspace:
```
mkdir catkin_ws
cd catkin_ws
mkdir src
cd src
```

##4. Clone repos
Clone following repos into your src folder
```
git clone https://github.com/l-schilling/jackal_simulation_rob.git
git clone https://github.com/wilselby/ouster_example
```

##5. Build your workspace
```
cd ..
catkin_make
```

If needed source your workspace (in your catkin_ws: source devel/setup.bash)

##6. Run simulation
```
roslaunch jackal_base jackal.launch
```


ZED Camera currently not supported in Gazebo.
For a quick fix you can change the argument config in the file jackal_base/launch/jackal.launch to "front_bumblebee2"
