# object-detection


in order to download darknet_ros package:
	cd catkin_ws/src
	git clone --recursive git@github.com:leggedrobotics/darknet_ros.git
	cd ../

in order to build:
		catkin build darknet_ros -DCMAKE_BUILD_TYPE=Release

sourcing:
	sourcing can be done internally, like in each terminal, the following line has to be mentioned in the 'build' folder:
		source devel/setup.bash
	on the otherhand, in the '.bashrc.personal' it can also be sourced externally and therefore, the struggle of sourcing in the individual terminal is mitigated:
		 if [ -f /cdtemp/your_catkin_ws/build/devel/setup.bash ]; then
            source /cdtemp/your_catkin_ws/build/devel/setup.bash

sourcing and gpu:
	on the other hand, while integrating with gpu, in the '.bashrc.personal', the following lines has to be mentioned:
			if [ -n "$PS1" ]; then
		if [ -f /opt/ros/melodic/setup.bash ]; then
 
			source /opt/ros/melodic/setup.bash
 
			if [ -f /cdtemp/your_catkin_ws/build/devel/setup.bash ]; then
            source /cdtemp/your_catkin_ws/build/devel/setup.bash
			fi
    	fi
		export PATH=/usr/local/cuda-10.2/bin:$PATH
	fi
		
For using own detection objects:
	'cfg' and 'weight' files has to be placed in the following folders for own detection module testing purpose:
		catkin_workspace/src/darknet_ros/darknet_ros/yolo_network_config/weights/
		catkin_workspace/src/darknet_ros/darknet_ros/yolo_network_config/cfg/		

For launching the whole module:
	command line:
		roslaunch darknet_ros yolo_v3.launch
