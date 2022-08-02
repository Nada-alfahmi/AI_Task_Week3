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
1 - Setup your sources.list :
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
2 - Set up your keys :
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
3 - Installation
sudo apt update
sudo apt install ros-melodic-desktop-full
sudo apt install ros-melodic-desktop
sudo apt install ros-melodic-ros-base
sudo apt install ros-melodic-PACKAGE
sudo apt install ros-melodic-slam-gmapping
4 - Environment setup
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
source /opt/ros/melodic/setup.bash
echo "source /opt/ros/melodic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
5 - Dependencies for building packages
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
sudo apt install python-rosdep
sudo rosdep init
rosdep update
6 - To make sure its work 
roscore
