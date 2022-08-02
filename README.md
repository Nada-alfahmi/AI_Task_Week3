# AI_Task_Week3
I had many issues with downloading ROS first i downloaded ubuntu 22.04 and downloading kinetic But it didn't work for some reason I could not figure it out .
Then i download Ubuntu 18.04 and ROS Melodic i got some issues like :

Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)

E: Unable to lock directory /var/lib/apt/lists/

W: Problem unlinking the file /var/cache/apt/pkgcache.bin - RemoveCaches (13: Permission denied)

W: Problem unlinking the file /var/cache/apt/srcpkgcache.bin - RemoveCaches (13: Permission denied)

I fixed it thanks to this site : https://cloudlinuxtech.com/could-not-open-lock-file-var-lib-dpkg-lock-frontend/

Then It's worked and i downloaded ROS peacefully 

# Install ROS on Ubuntu

# 1 - Setup your sources.list :

$  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

# 2 - Set up your keys :

$  sudo apt install curl # if you haven't already installed curl

$  curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

# 3 - Installation

$  sudo apt update

$  sudo apt install ros-melodic-desktop-full

$  sudo apt install ros-melodic-desktop

$  sudo apt install ros-melodic-ros-base

$  sudo apt install ros-melodic-PACKAGE

$  sudo apt install ros-melodic-slam-gmapping

# 4 - Environment setup

$  echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc

$  source ~/.bashrc

$  source /opt/ros/melodic/setup.bash

$  echo "source /opt/ros/melodic/setup.zsh" >> ~/.zshrc

$  source ~/.zshrc

# 5 - Dependencies for building packages

$  sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

# 5.1 Initialize rosdep

$  sudo apt install python-rosdep

$  sudo rosdep init

$  rosdep update

# 6 - To make sure its work 

$ roscore

# Creating a WrokSpace :

$ mkdir tutorials_catkin_ws

$ cd tutorials_catkin_ws/

$ mkdir src

$ cd src/

$ catkin_init_workspace

$ cd .. 

$ catkin_make

$ echo ${ROS_PACKAGE_PATH}

$ source setup.bash

$ echo ${ROS_PACKAGE_PATH}

$ cd ..

# Install the Arm Package :

$ cd src/

$ sudo apt install git

$ git clone http://github.com/smart-methods/arduino_robot_arm

$ cd  ~/tutorials_catkin_ws

$ rosdep install --from-paths src --ignore-src -r -y

$ sudo apt-get install ros-melodic-moveit

$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui

$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher

$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control

# Finally laucnh the package

$ roslaunch robot_arm_pkg check_motors.launch

