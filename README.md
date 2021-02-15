# simple_cm
0. Pre-requisites
    0. OS: Ubuntu 20.04
    1. Install the following:
        - ROS Noetic (Desktop Full)
            - [How To: Ubuntu install of ROS Noetic](http://wiki.ros.org/noetic/Installation/Ubuntu)
    2. [How To: Create a Catkin Workspace](http://wiki.ros.org/catkin/Tutorials/create_a_workspace)

1. Run the following commands

    ```bash
    # Navigate to catkin src and clone this repo
    cd ~/catkin_ws/src
    git clone THIS_REPO_URL

    # Build project and source
    cd .. # move to ~/catkin/ws
    catkin_make # make sure this is done in ~/catkin_ws/
    source ~/catkin_ws/devel/setup.bash
    ```

2. Run the project in Gazebo using roslaunch

    ```bash

    roslaunch simple_cm spawn_robot.launch
    ```
------
Other steps:
3. Sending basic movement commands using rostopics?
    - run code in src/[main.py](http://main.py) or use rostopics in terminal to send message

        ```bash
        # DRAFT: script for testing publishing movement via ros topics

        #!/usr/bin/env python
        import rospy
        import random
        from std_msgs.msg import Float64

        def generate_rnd_float64:
        		return random.uniform() #?

        def generate_random_joint_movements():
        		global rate_value = 10 #??
            rospy.init_node('??', anonymous=True)
            rate = rospy.Rate(rate_value)     
            pub = rospy.Publisher('??', Float64, queue_size=10)
            
            while not rospy.is_shutdown():
                try:  
                    pub.publish(generate_rnd_float64())
                    rate.sleep()
                except rospy.ROSInterruptException:
        	    rospy.logerr("ROS Interrupt Exception")

        if __name__ == "__main__":
        	generate_random_joint_movements()
        ```
