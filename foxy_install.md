## ROS2 Foxy installation
### (1) Set `locale`
```bash
locale
sudo apt update
sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
locale
```
<!-- #### Output should be like this
```bash
.....
LANG=en_US.UTF-8
LANGUAGE=
LC_CTYPE="en_US.UTF-8"
LC_NUMERIC="en_US.UTF-8"
LC_TIME="en_US.UTF-8"
LC_COLLATE="en_US.UTF-8"
LC_MONETARY="en_US.UTF-8"
LC_MESSAGES="en_US.UTF-8"
LC_PAPER="en_US.UTF-8"
LC_NAME="en_US.UTF-8"
LC_ADDRESS="en_US.UTF-8"
LC_TELEPHONE="en_US.UTF-8"
LC_MEASUREMENT="en_US.UTF-8"
LC_IDENTIFICATION="en_US.UTF-8"
LC_ALL=en_US.UTF-8
```-->
### (2) Setup Sources
```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo apt update
sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
### (3) Install ROS2 packages
```bash
sudo apt update
sudo apt upgrade -y
sudo apt install ros-foxy-desktop python3-argcomplete -y
```
### (4) Environmental setup
```bash
echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### (5) *optional
### Test the installation
#### Open one new terminal and run the `listener` node
```bash
ros2 run demo_nodes_py listener
```
#### Then, open another new terminal and run `talker` node
```bash
ros2 run demo_nodes_py talker
```
`talker` node starts publishing `Hello World` every second \
When you open `listener` node, you can see it recieves `talker`'s data \
\
You can stop both terminal by `Ctrl+C`.
