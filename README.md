# Controlling-the-robot-arm-by-joint-state-publisher

## step1: setup a ROS workspace (Catkin)
```
mkdir catkin_ws
```

then you can go inside your new folder:
```
cd catkin_ws
```

then we are going to create a source (make sure it it exactly src inside thr catkin work space)
```
mkdir src
```

now make sure that you are inside the catkin_ws folder (not inside the src folder) then we can start to compile by running the command :
```
catkin_make
```
![Screenshot 2024-07-10 000233](https://github.com/khawla-cs/-/assets/173630971/72887bf8-8d75-488b-9e40-b6e159a11719)

basicaally this is gonna compile everything in the workspace, install stuff, etc...

## step 2:
 now if we run the command ``` ls ``` we see that we have two new folders (build and devel)
 
 ![Screenshot 2024-07-10 000814](https://github.com/khawla-cs/-/assets/173630971/2670d240-8322-42f6-ab52-d93f9b35fa84)


if you go to the devel folder : ``` cd devel/ ``` then ```ls ```

![image](https://github.com/khawla-cs/-/assets/173630971/1d7e6b82-59f2-4e0e-b49e-c120076adb98)

here we see something  called (setup.bash)
we will need to source this (setup.bash) script if we want to be able to use the code that we have written in our catkin workspace.

so, to source this we will need to:
```
source ~/catkin_ws/devel/setup.bash
```

once you have run this command you can use your custom ROS code

last thing here is to run ``` gedit ~/.bashrc``` then this window will appears

![Screenshot 2024-07-10 002846](https://github.com/khawla-cs/-/assets/173630971/310c014d-27ef-498f-a4f2-abb4945449ca)

 at the end or the window we have the source line for our global ROS installation . so we will add this line ```source ~/catkin_ws/devel/setup.bash``` (after) the global ROS installation

 ![Screenshot 2024-07-10 003349](https://github.com/khawla-cs/-/assets/173630971/cabc3e06-6bae-4152-9798-a621b6f05d19)

 now save and quit the file. you should have those two lines so you can see your global ros installation as kind of a first level, and then your custom workspace here have the second level. you need to source both the global ROS installation and your catkin workspace, so you can use your code with ROS functionalities.

 ## Installing the package arduino_robot_arm
1-- Add the “arduino_robot_arm” package to “src” folder ```cd src``` then copy this command :
```
sudo apt install git
```

![Screenshot 2024-07-10 035256](https://github.com/khawla-cs/-/assets/173630971/a433dd62-2a3b-4a3e-ade0-d570d9deb7ba)


2- ```git clone https://github.com/smart-methods/arduino_robot_arm```

![Screenshot 2024-07-10 035512](https://github.com/khawla-cs/-/assets/173630971/b418dc3b-8cff-4dc8-9e0e-f615f539e4c6)

3- now go back to the (catkin_ws) using command ```cd ..``` ,then

```
rosdep install --from-paths src --ignore-src -r -y
```

![Screenshot 2024-07-10 035927](https://github.com/khawla-cs/-/assets/173630971/9ca15059-72be-4bc6-a296-13e75f0fb234)

4- run the command ```sudo apt-get install ros-noetic-moveit```

![Screenshot 2024-07-10 040113](https://github.com/khawla-cs/-/assets/173630971/c01e38da-2870-4d93-b9cd-195fbf39876b)

5- run the command 
```
sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
```

![Screenshot 2024-07-10 040346](https://github.com/khawla-cs/-/assets/173630971/d1a06ad5-f57b-4411-be00-3de0d4ad08cb)

6-
```
sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
```
![Screenshot 2024-07-10 040600](https://github.com/khawla-cs/-/assets/173630971/62485bfd-c36c-4053-8ae6-6e3ed3410f38)

7-
```
sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```

![Screenshot 2024-07-10 040907](https://github.com/khawla-cs/-/assets/173630971/c88d7160-3ee5-454d-a245-8dcc08096083)

8-compile the package
```
catkin_make
```

## Controlling the motors

- when you run this command the widows will apears
  
```
roslaunch robot_arm_pkg check_motors.launch
```

![Screenshot 2024-07-10 041251](https://github.com/khawla-cs/-/assets/173630971/65c444c5-8391-4d77-9993-0e9856baab5e)

You can move it as you wish too!

![Screenshot 2024-07-10 041454](https://github.com/khawla-cs/-/assets/173630971/9b3c222e-e6bf-492a-8c7c-c9bfeda6ad59)

## showing the graph

if you want to see a graph of what is happening at this time just run this command 
```
rqt_graph
```

![Screenshot 2024-07-10 041650](https://github.com/khawla-cs/-/assets/173630971/ea07244f-b470-413d-83d2-1cb36653209f)


## Gazebo
run the command :
```
roslaunch robot_arm_pkg check_motors_gazebo.launch
```

<img width="458" alt="Screenshot 2024-07-10 042455" src="https://github.com/khawla-cs/-/assets/173630971/bf890b54-c942-402c-9a80-871523864698">

## MoveIt controlling
```
roslaunch moveit_pkg demo.launch
```

![Screenshot 2024-07-10 044224](https://github.com/khawla-cs/-/assets/173630971/da2ebcf2-c347-46e2-a6af-1b9e4a4d52a9)















 


