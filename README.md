
Prerequisite:
1:Amazon (aws)linux machine Or local machine
2:Docker and Docker-compose installed
3:GIT to clone the Repository
4: Open the below Port
        1: 80 for Nginx
        2: 8080 for tomcat node 1
        3: 8081 for tomcat node 2
        4: 3306 For mysql
        5: 22 for ssh access (only for aws)

Steps To Run the Test the Application

 Note : output images are stored in the images directory and also create the /opt/test directory for mysql data mount

1: clone the repo
   git clone https://github.com/sharad0427/PTC-Assignment.git

   After cloning the repo you will find the docker-compose.yaml file & war , conf , images directory.
   1: war file contained the 2 war file namely node1.war & node2.war (sample web application).
   2: conf file contained nginx.conf file use for the loadbalancing the application 
   3: images file contained sample output of the assingment 

2: Now Run the run the docker compose up command to start the container/application
   docker-compose up -d

3: Check the container is up or not (sample output images are stored in the image directory)
    docker ps -a

4: hit the url and check the output again refresh the page and check the output again you will see request is routing to both of the tomcat node one at time  i.e node 1 & 2 (in my case request is routing to both of the tomcat container one at a time at page refress)

   url: https://IP_OF_THE_HOST/SampleApp  // use the public IP of the instance
   in my case : http://3.138.139.107/SampleApp/
