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

 now save and quit the file. you should have those two lines so you can see your global ros installation as kind of a first level, and then your custom workspace here have the second level. you need to source both the global ROS installation and your catkin workspace, so you can use your code with ROS functionalities
 


