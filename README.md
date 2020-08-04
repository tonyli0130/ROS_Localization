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
    
2. Next launch the `amcl.launch` file which opens the scripts containing the main code to localize the robot in gazeo world:
    * `roslaunch my_robot amcl.launch`
 
   The RViz which provides a better visualization of both robot and simulation environment will open simultaneously, the fixed frame should be set to /map and the swarm of red arrows which represent the particle filters will appear after few minutes:
      
   ![2](https://user-images.githubusercontent.com/60047845/89330177-80d18380-d655-11ea-9a68-4763ca16275f.png)
  
 
   After launching the `world.launch` and `amcl.launch`, the localization is ready. Use the 2D navigation tool button shown below to point out the goal location and the robot will start to move toward the goal location autonumously:
   
   The swarm of red arrows will converge gradually as the robot keeps moving. Try to move the robot to different goal locations until the convergence of red arrows is satisfactory. An example of convergence is shown below:
   ![1](https://user-images.githubusercontent.com/60047845/89330153-76af8500-d655-11ea-95eb-aa12b0b293c4.png)

 
## Source Code Explaination
