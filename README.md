# Executing a MapReduce Algorithm with AWS EC2  

### Setup Steps are as Follows:  
1. launch an EC2 virtual machine instance  
2. choose AMI == Ubuntu 20.04  
3. create Key Pair  
4. connect to EC2  
5. 'sudo apt update'  
6. 'sudo apt upgrade'  
7. 'sudo nano /etc/hostname' to change the hostname to hadoop  
8. 'sudo rebot' note that this may take a few minutes  
9. 'sudo apt install openjdk-8-jdk' to Install Open JDK 8  
10. 'wget https://dlcdn.apache.org/hadoop/common/hadoop-3.3.6/hadoop-3.3.6.tar.gz -P ~/Downloads'  you can change the link for a different version of hadoop as needed  
11. 'sudo tar zxvf ~/Downloads/hadoop-* -C /usr/local' to unpack hadoop  
12. 'sudo mv /usr/local/hadoop-* /usr/local/hadoop' to rename the folder  
13. Set up of Environment
    1. 'nano ~/.bashrc' to open a .bashrc file
    2. Write the following into the bottom of the .bashrc file:
       'export HADOOP_HOME=/usr/local/hadoop
        export HADOOP_INSTALL=$HADOOP_HOME
        export HADOOP_MAPRED_HOME=$HADOOP_HOME
        export HADOOP_COMMON_HOME=$HADOOP_HOME
        export HADOOP_CONF_DIR=/usr/local/hadoop/etc/hadoop
        export HADOOP_HDFS_HOME=$HADOOP_HOME
        export YARN_HOME=$HADOOP_HOME
        export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
        export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin'
    4. 'source ~/.bashrc' to refelt current session
    5. 'sudo nano $HADOOP_CONF_DIR/hadoop-env.sh' to get into the hadoop env
    6. once inside the env go to the bottom of the script and paste the following:
       `export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
        export HADOOP_CONF_DIR=/usr/local/hadoop/etc/hadoop'
  
14. 'sudo mkdir -p $HADOOP_HOME/data/hdfs/namenode' to make the namenode dir
15. 'sudo mkdir -p $HADOOP_HOME/data/hdfs/datanode' to make the datanode dir
16. 'sudo chown -R ubuntu $HADOOP_HOME' to change the owner
17. 'sudo nano $HADOOP_HOME/masters' once inside type hadoop. This changes the master node
18. 'sudo nano $HADOOP_HOME/slaves' once inside type hadoop. This changes the slave node

### Steps to Running MapReduce:
1. 'nano input' write a few differnt words a few times
2. 'hdfs dfs -mkdir -p WordCount/input'
3. 'hdfs dfs -put input WordCount/input'
4. 'hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.6.jar wordcount WordCount/input WordCount/output' **will run Mapreduce**

Now you can run MapReduce!
