# ROS_Localization

The Localization project uses AMCL (Adaptive Monte Carlo Localization) package interacting with robot in gazebo world to localize the robot position under ROSS (Robot Operation System) framework. AMCL algorithm localizes the robot with the help of particle filter. The particle will update its measurement and current state as the robot keeps moving. An important weight which tells how closed this partilce is to the robot will be assigend to each particle. The resampling process will generate more particles with higher important weight and convergence of particles will appear after sufficient numbers of iterations.

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
   
   
    ![3](https://user-images.githubusercontent.com/60047845/89331006-b034c000-d656-11ea-8750-96ad712d3771.PNG)
    
   
   The swarm of red arrows will converge gradually as the robot keeps moving. Try to move the robot to different goal locations until the convergence of red arrows is satisfactory. An example of convergence is shown below:
   
   ![1](https://user-images.githubusercontent.com/60047845/89330153-76af8500-d655-11ea-95eb-aa12b0b293c4.png)
   




