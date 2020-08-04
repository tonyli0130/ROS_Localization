# ROS_Localization
Description

## Installation
1. Open a new terminal and build the catkin workspace:

    * `$ mkdir -p /home/workspace/catkin_ws/src`
 
    * `$ cd /home/workspace/catkin_ws/src`
 
    * `$ catkin_init_workspace`
 
  
2. Clone the project under  **/home/workspace/catkin_ws/src** directory:

    * `git clone https://github.com/tonyli0130/ROS_Localization.git`
 
 3. Make and compiler the project (**remember to source the environment variables in every new opened terminals**):
 
    * `cd /home/workspace/catkin_ws`
 
    * `catkin_make`
 
    * `source devel/setup.bash`
 
 
4. Update and upgrade the workspace image to get the lattest features of Gazebo, open a terminal and write the following statements:

    * `$ sudo apt-get update && sudo apt-get upgrade -y`

## Usage
1. Now run the Localization project, first launch the `world.launch` file and have the robot simulation environment ready:

    * `roslaunch my_robot world.launch`
 
 
   The RViz which provides a better visualization of both robot and simulation environment will open simultaneously, the fixed frame should be set to /map and the swarm of red arrows which represent the partilce filters will appear after few minutes:
   


2. Next launch the `ball_chaser.launch` file which opens the scripts containing the main code to interact with robot in gazeo world:
    * `roslaunch ball_chaser ball_chaser.launch`
 
   After launching the `world.launch` and `ball_chaser.launch`, the ball chasing process is ready. Use the drag button shown below to move the white ball to different locations as long as the robot camera can capture. The robot should start to move and chase toward the ball.
 
 
    ![drag_button](https://user-images.githubusercontent.com/60047845/89233799-ff73e580-d5af-11ea-87ea-d89b2f941129.PNG)


## Source Code Explaination
