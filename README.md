# Team MEGA

We created a quadrotor based testbed for existing and new traffic control algorithms. This system can accelerate the development of modular self-contained autonomous routing controllers for dense low-altitude fleets of quadrotors. This platform will be used by students and researchers as a low-cost, but realistic tool for testing outdoor navigation algorithms. 

## Devpost
https://devpost.com/software/autonomous-airspace

##Additional Project Components
GUI https://github.com/katetolstaya/teammega_gui  
Matlab Path Planner https://github.com/brent8149/Matlab_planner   
C++ controller https://github.com/brent8149/teamMEGA 

##Installation Requirements
See each individual link for installation instructions.  
A simulator of choice (jMavSim or Gazebo) (http://dev.px4.io/simulation-sitl.html)  
MAVROS (http://dev.px4.io/ros-mavros-installation.html)  
ROS (Tested with Kinetic) (http://wiki.ros.org/kinetic/Installation/Ubuntu)  
MATLAB Planner (https://github.com/brent8149/Matlab_planner)  
teamMEGA ROS Node (https://github.com/brent8149/teamMEGA)  
GUI Application (https://github.com/katetolstaya/teammega_gui)  
ROSBridge (https://github.com/RobotWebTools/rosbridge_suite)  

##Executing the Software

If you are using a simulator (jMavSim):   

To use jmavsim:  
cd ~/src/Firmware  
make broadcast jmavsim  

Otherwise, simply note the IP Address of your quadrotor on the network.    

To run MAVROS: (Check the port / IP)  
For simulator:  
roslaunch mavros px4.launch fcu_url:="udp://:14540@127.0.0.1:14557"  
For Serial / USB:  
roslaunch mavros px4.launch fcu_url:="serial:///dev/ttyACM0:921600"  
For real drone over WIFI:  
roslaunch mavros px4.launch fcu_url:="udp://:14550@192.168.4.1:14555"  

Launch ROSbridge  
roslaunch rosbridge_server rosbridge_websocket.launch  

Launch web-app  
open teammega_gui/index.html  

Launch team_mega  
rosrun teamMega teamMega  

Launch matlab  
matlab planner_sim.m  

After the above commands have been executed, you will be able to click landing locations and obstacles in the GUI, and observe the planner creating appropriate trajectories for the system, and then successfully flying the quadrotors.  
