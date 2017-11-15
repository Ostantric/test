# Installation

``` bash 
source /opt/ros/kinetic/setup.bash
mkdir workspace
cd worksapce
git clone -b murat https://bitbucket.org/mark_turner_sahaiku/prototype/src
catkin_make
roslaunch convert_joystick teleop.launch
```

<img src="/rosgraph.svg">

