# wheeled_robot
Differential drive robot made in ROS2 foxy, to map a world created in gazebo

Source the files @ workspace -

    source install/setup.bash
   
Launch the bot -

    ros2 launch wheeled_robot bot.launch.py
  
 In another terminal, launch gazebo (load the world path and spawn the robot in another terminal) -
 
    ros2 launch gazebo_ros gazebo.launch.py
    
    ros2 run gazebo_ros spawn_entity.py -topic robot_description -entity bot
 
For mapping and localization, open up a new terminals and -

    ros2 launch slam_toolbox online_async_launch.py params_file:=./src/wheeled_robot/config/mapper_params_online_async.yaml
   
    ros2 launch nav2_bringup navigation.launch.py use_sim_time:=true
   
Visualize using rviz2

Move the bot around using -
 
    ros2 run teleop_twist_keyboard teleop_twist_keyboard
