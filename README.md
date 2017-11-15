### INSTALL

``` bash 
source /opt/ros/kinetic/setup.bash
mkdir workspace
cd worksapce
git clone -b murat https://bitbucket.org/mark_turner_sahaiku/prototype/src
catkin_make
```
### RUN
This launch file will run the  convert_joystick, joy_node and the roscore

``` bash 
roslaunch convert_joystick teleop.launch
```
### NOTE
if you have this problem;
```
[ERROR] [1510716314.539557608]: Couldn't open joystick /dev/input/js0. Will retry every second.
```
Make sure you plugged in the joystick and your joystick shown as js0 under input.
You can check the js-number by executing this
``` bash 
ls /dev/input/
```

### RQT GRAPH

Ignore rostopic_21425(topic echos cmd_vel)

<img src="/rosgraph.svg">

