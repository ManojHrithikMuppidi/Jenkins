# Jenkins
## Requirements 
AWS EC2 Instance 
Docker
Docker Compose
Jenkins
### Jenkins Admin Password
Jenkins admin password 33ec6f70b3904ec2b73eef544b1ffa10 
## Steps to install in Amazon Linux Ec2
- sudo yum update
- sudo yum install  docker
- sudo yum install docker-ce
- sudo systemctl status docker
- sudo systemctl enable docker
- sudo systemctl start docker
- docker -v
- docker ps -a
- sudo curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- sudo systemctl restart docker
- mkdir -p /home/ec2-user/jenkins_data/jenkins_home
- vi docker-compose.yml
```
services:
  jenkins:
    container_name: jenkins
    image: jenkins/jenkins:lts-jdk11
    restart: unless-stopped
    ports:
      - "8080:8080"
    volumes:
      - "/home/ec2-user/jenkins_data/jenkins_home:/var/jenkins_home"
```
- sudo docker-compose up -d
- sudo docker ps -a
- cd jenkins_data/
- cat jenkins_home/secrets/initialAdminPassword

#### Jenkins URL: http://13.126.129.155:8080/
