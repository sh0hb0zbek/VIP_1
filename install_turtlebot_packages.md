## (1) PC setup
#### Install `Gazebo`
```bash
sudo apt-get install ros-foxy-gazebo-*
```
#### Install `Cartographer`
```bash
sudo apt install ros-foxy-cartographer
sudo apt install ros-foxy-cartographer-ros
```
#### Install `Navigation`
```bash
sudo apt install ros-foxy-navigation2
sudo apt install ros-foxy-nav2-bringup
```
#### Install `TutleBot3` packages
```bash
source ~/.bashrc
sudo apt install ros-foxy-dynamixel-sdk
sudo apt install ros-foxy-turtlebot3-msgs
sudo apt install ros-foxy-turtlebot3
```
#### Set the ROS environment for PC
```bash
echo "export ROS_DOMAIN_ID=30" >> ~/.bashrc
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc
```
