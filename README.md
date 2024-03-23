# Jenkins 

Jenkins stands as a pivotal open-source build orchestration tool within the realm of DevOps, facilitating the creation of comprehensive CI/CD pipelines. Its core function revolves around automating the build and deployment processes, streamlining workflows from code integration to delivery. Operating on a Master-Slave architecture, Jenkins efficiently distributes tasks across multiple nodes, optimizing resource utilization and enhancing scalability. One of its defining features is the Jenkins Pipeline, enabling the scripting of entire delivery pipelines using Groovy. With Jenkins, teams can seamlessly integrate various stages of software development, enabling rapid iteration, robust testing, and continuous delivery, ultimately fostering a culture of automation and efficiency within modern software development practices.

## Prerequisites 

### 1. Launch AWS Ubuntu EC2 Instances

- Launch 2 Linux based EC2 instances: Jenkins_Master and Jenkins_Slave.
  
  [Launch Instance](https://github.com/Prathamesh78/AWS/tree/main/EC2)
- Make sure to enable inbound traffic on port 8080 for Jenkins.
  
  [Security Group Configuration](https://github.com/Prathamesh78/AWS/tree/main/Security%20Groups)

### 2. Connect to EC2 Instances

- Connect to your EC2 instances using one of the following methods:
  - EC2 Instance Connect
  - SSH Agents like MobaXterm, Putty, or Terminal

## Working with Jenkins

### 1. Master Node Configuration

- Install Java Development Kit (JDK) on Linux based EC2 Instance
  ```bash
    sudo apt update -y
    sudo apt install openjdk-17-jre -y
    java -version
  ```
  ![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/b2aff5fc-ba89-4af1-8716-6a957206528e)


- Install Jenkins on Linux based EC2 Instance
  ```bash
    sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
  
    sudo apt-get update -y
    sudo apt-get install jenkins -y
  ```
  ![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/5ce65c21-770c-4637-9573-21d0f1c25307)

- Install Git on Linux based EC2 Instance
  ```bash
    sudo apt install git -y
  ```
  ![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/933d76e0-0f50-4379-afa3-8a97ff6c03fd)

- Access the Jenkins
  - Jenkins is installed in the directory: '/var/lib/jenkins'
  - Access Jenkins using a web browser:
    - URL: http://<public_ip_address>:8080
  ![image](https://github.com/Prathamesh78/Jenkins/assets/104883046/38ea31c3-8cbe-47fa-9c53-21eff9397bb0)

