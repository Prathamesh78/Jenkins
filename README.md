# Jenkins ![Untitled](https://github.com/Prathamesh78/Jenkins/assets/104883046/bbff8242-b2ad-423f-b235-818836a2d2c5)


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

- Install Git on Linux based EC2 Instance
  ```bash
    sudo apt install git -y
  ```
- Access the Jenkins
  - Jenkins is installed in the directory: '/var/lib/jenkins'
  - Access Jenkins using a web browser:
    - URL: http://<public_ip_address>:8080
