# Executing a MapReduce Algorithm with AWS EC2  
### The steps are as follows:  
1 - launch an EC2 virtual machine instance  
2 - choose AMI == Ubuntu 20.04  
3 - create Key Pair  
4 - connect to EC2  
5 - 'sudo apt update'  
6 - 'sudo apt upgrade'  
7 - 'sudo nano /etc/hostname' to change the hostname to hadoop  
8 - 'sudo rebot' note that this may take a few minutes  
9 - 'sudo apt install openjdk-8-jdk' to Install Open JDK 8  
10 - 'wget https://dlcdn.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz -P ~/Downloads'  you can change the link for a different version of hadoop as needed  
11 - 'sudo tar zxvf ~/Downloads/hadoop-* -C /usr/local' to unpack hadoop  
12 - 'sudo mv /usr/local/hadoop-* /usr/local/hadoop' to rename the folder  
