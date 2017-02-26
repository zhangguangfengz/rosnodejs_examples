# rosnodejs examples

## Install and Build

Prerequisites:
- [Install ROS Kinetic or Lunar](http://wiki.ros.org/kinetic/Installation/Ubuntu)  
- [Install `nodejs` and the `npm` package manager, with `nodejs` version 6.x or 7.x recommended]
(https://nodejs.org/en/download/package-manager/)  
  
To get started the "catkin" way:
```
$ mkdir -p ~/rosnodsjs_ws/src
$ cd ~/rosnodsjs_ws/src
$ git clone https://github.com/RethinkRobotics-opensource/rosnodejs_examples.git
$ cd rosnodejs_examples
$ npm install
$ cd ~/rosnodsjs_ws
$ source /opt/ros/kinetic/setup.bash
$ catkin build
```

## Running Talker / Listener
To run the programs, open three terminal windows (for illustration purposes).  
### Window 1: typical ROS Master
```
$ source ~/rosnodejs_ws/devel/setup.bash
$ roscore
```
### Window 2: talker.js script 
```
$ source ~/rosnodejs_ws/devel/setup.bash
$ rosrun rosnodejs_examples talker.js
```
You should see output like the following:
```
[INFO] [1487773766.635] (ros): I said: [hello world 10]
[INFO] [1487773766.735] (ros): I said: [hello world 11]
[INFO] [1487773766.835] (ros): I said: [hello world 12]
```

### Window 3: listener.js script
```
$ source ~/rosnodejs_ws/devel/setup.bash
$ rosrun rosnodejs_examples listener.js
```
You should see echoed output like the following:
```
[INFO] [1487773766.644] (ros): I heard: [hello world 10]
[INFO] [1487773766.743] (ros): I heard: [hello world 11]
[INFO] [1487773766.845] (ros): I heard: [hello world 12]
```

Congratulations! You've just published and subscribed over ROS using Javascript!
