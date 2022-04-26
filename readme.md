## installing jenkins ##  
[guide to install jenkins](https://www.jenkins.io/doc/book/installing/linux/)  
`java -version` to check java version  
`systemctl start jenkins`  
localhost:8080, user:admin, pass: 
Jenkins Dashboard ->Manage Jenkins ->Manage plugins ->Available ->Maven Integration ->Install.  
install deploy to container plugin for tomcat  [link](https://www.middlewareinventory.com/blog/jenkins-tomcat-deploy-deploying-application-tomcat-using-jenkins/)  


## installing sonarqube (pull docker image and run that) ##  
[guide to starting sonarqube on localhost](https://docs.sonarqube.org/latest/setup/get-started-2-minutes/)  
[sonarqube image on docker](https://hub.docker.com/_/sonarqube/)  
`docker pull sonarqube`  
`docker run -d --name sonarqube -e SONAR_ES_BOOTSTRAP_CHECKS_DISABLE=true -p 9000:9000 sonarqube:latest`  
`docker ps`  
localhost:9000  

## installing tomcat ##  
[installing tomcat9](https://linuxhint.com/install_apache_tomcat_server_ubuntu/)  
[installing jdk8](http://openjdk.java.net/install/index.html)  
`sudo apt-get install openjdk-8-jre`  
`sudo nano /etc/tomcat9/server.xml` to change port number as 8080 was already in use by jenkins  
`sudo nano /etc/tomcat9/tomcat-users.xml` to add and modify user credentials  
`systemctl start tomcat9`
localhost:8082  

## installing nexus ##  
[starting nexus on localhost](https://ahgh.medium.com/how-to-setup-sonatype-nexus-3-repository-manager-using-docker-7ff89bc311ce)  
`docker pull sonatype/nexus`  
`docker run -d -p 8082:8082 --name nexus sonatype/nexus3`
`docker ps`
`docker container exec nexus cat nexus-data/admin.password`  
localhost:8081  

## install maven ##  
`sudo apt update`  
`sudo apt install maven`  

## git repo ##  
[repo](https://github.com/jasonltr/KCMavenWebProject)  
[tutorial](https://www.youtube.com/watch?v=meaD9y1RPNc)  

## Jenkins configuration ##  
dashboard -> new item -> 