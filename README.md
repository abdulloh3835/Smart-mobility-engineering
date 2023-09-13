
# Setup ROS 2 Humble on Ubuntu 22.04   
# First step：setlocale   
locale  # check for UTF-8    

sudo apt update && sudo apt install locales    
sudo locale-gen en_US en_US.UTF-8    
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8    
export LANG=en_US.UTF-8    

locale  # verify settings      
      
<img width="1280" alt="Screenshot 2023-09-13 at 4 40 51 PM" src="https://github.com/abdulloh3835/Smart-mobility-engineering/assets/90837231/d6473bd1-d054-42c3-8494-d986e4638ee2">



# Second Step: Add ROS 2 apt repository    
#apt-cache policy | grep universe    
sudo apt install software-properties-common     
sudo add-apt-repository universe    
<hr />

sudo apt update && sudo apt install curl gnupg lsb-release -y     
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg     
<hr />
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null   
<hr />
sudo apt update        

sudo apt upgrade     

# Third Step: Install ros-humble-desktop， ros-humble-ros-base
sudo apt install ros-humble-desktop   
sudo apt install ros-humble-ros-base

# Fourth Step: Config environment   

source /opt/ros/humble/setup.bash    
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc  

# Fifth Step: Verify that ROS 2 was installed successfully
 
printenv | grep -i ROS         
<img width="1189" alt="Screenshot 2023-09-13 at 4 54 58 PM" src="https://github.com/abdulloh3835/Smart-mobility-engineering/assets/90837231/e7061648-ca29-424f-a846-23beeaf1c152">



