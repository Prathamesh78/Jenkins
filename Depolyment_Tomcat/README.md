# Installing Apache Tomcat Application Server on Ubuntu

## Introduction
This guide provides step-by-step instructions for installing and configuring Apache Tomcat on an Ubuntu v20.04 AWS EC2 instance. Apache Tomcat is an open-source web server and servlet container that is used to deploy Java-based web applications.

## Prerequisites
- Ubuntu v20.04 AWS EC2 instance
- Inbound rule allowing traffic on port 8080
- Switch to root user in ubuntu terminal
  
## Installation Steps

### 1. Update Ubuntu and Install Java
```bash
sudo apt update -y 
sudo apt install openjdk-11-jre -y 
```
![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/ee76a815-6a2a-424b-9923-24967dda3eb8)

### 2. Set JAVA_HOME Environment Variable
```bash
sudo vi /etc/profile
```
#### Add the following line:
export JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
```bash
source /etc/profile
```
![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/b6851484-1d63-4ae6-a8cb-1de70f51c397)

### 3. Download and Extract Apache Tomcat
```bash
cd /opt
wget https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.99/bin/apache-tomcat-8.5.99.tar.gz
tar -xvzf apache-tomcat-8.5.99.tar.gz
mv apache-tomcat-8.5.99 tomcat
```
![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/93d93a1b-6b37-4c02-aea7-9d527097f305)

### 4. Create a User for Administration
```bash
sudo useradd <user_name> -s /bin/bash -m -d /home/<user_name>
sudo su - <user_name>
ssh-keygen -t rsa -b 2048 -m PEM
cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys
chown -R <user_name> /home/<user_name>/.ssh
chmod 600 /home/<user_name>/.ssh/authorized_keys
chmod 700 /home/<user_name>/.ssh
```

### 5. Exit to the root directory

### 6. Set Ownership of Tomcat Directory
```bash
sudo chown -R <user_name> /opt/tomcat
```

### 7. On Master Node 
- Goto manage jenkins --> Plugins --> Avaliable Plugins - search for 'Publish Over SSH'  --> install and restart Jenkins
- Goto Manage Jenkins --> System --> Publish Over SSH plugin for configuration.
