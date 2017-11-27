# INSTALL

``` bash 
source /opt/ros/kinetic/setup.bash
mkdir workspace
cd worksapce
git clone -b murat https://bitbucket.org/mark_turner_sahaiku/prototype/src
catkin_make
```
# JOYSTICK
### RUN

This launch file will run the Dongbu_joy, Dongbu_teleop and the roscore

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
if its different than js0 then find this line in the launch file and change the js0 value.
```
<param name="joystick_device_file" type="string" value="/dev/input/js0" />
```

# MAC-Controller

### RUN 

This launch file will run the Mac_Controller_Bridge and the roscore

``` bash 
roslaunch mac_controller bridge.launch 
```

### NOTE

port can be changed in bridge.py 

```
ser = serial.Serial(port = '/dev/ttyUSB0', baudrate = 9600, timeout=0.1) 
```

Commands can be send by publishing 
```
input_mac_controller
```

### List of Commands
```
AbortTask
BeginTask
StopAxis
UserBoolean
UserNumber
CheckTask
```

### Task.msg layout
```
"Command:
  Command: '' //command name
Id:
  Id: 0 //taskid
Value:
  SetRetrieve: false //set true if you want to retrieve
  SetBoolean: false //set true or false
  SetNumber: 0.0" //float number
```
