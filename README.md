# containerize-java application

![Screenshot from 2024-09-27 08-19-18](https://github.com/user-attachments/assets/440e41e7-eaea-471c-9f12-3b24a43e3084)



 
# Introduction
In this project, the goal is to containerize a Java-based application using Docker and orchestrate the setup of five critical services: Nginx, MySQL, RabbitMQ, Memcached, and Tomcat. Each of these components plays a unique role in the architecture of the application, providing scalability, performance optimization, and streamlined deployment.

Nginx: Acts as a reverse proxy server, efficiently distributing client requests to backend services, improving load balancing and security. It also handles static content delivery.

MySQL: Serves as the relational database management system, storing persistent data for the application, such as user information and other structured data.

RabbitMQ: Functions as the messaging broker, facilitating communication between services via message queues, enabling reliable, asynchronous communication.

Memcached: Implements distributed caching to speed up dynamic web applications by reducing database load and improving response times for frequently accessed data.

Tomcat: Hosts the core Java application by running the Java Servlet and JavaServer Pages (JSP) technologies, providing the runtime environment for your web application.

we'll take the rabbitmq & memcashed official images from dockerhub and customize our 3 images (tomcat - mysql - nginx)

By containerizing these services, you ensure that the environment is reproducible, scalable, and easily deployable across various stages (development, testing, production). Using Docker Compose, you'll manage the orchestration of these containers, ensuring smooth communication between them.

# Prerequisites
Before you begin, ensure you have met the following requirements:

1- Oracle VM VirtualBox: A powerful x86 and AMD64/Intel64 virtualization product for enterprise as well as home use.
<br>
2- Vagrant: A tool for building and managing virtual machine environments in a single workflow.
<br>
3- install docker engine & docker compose on the vm
<br>
<br>
note : you can use AWS (EC2) insted of using vagrant vms

# fork the source code and clone it in your editor
1- go to this link on github https://github.com/devopshydclub/vprofile-project/
<br>
2- change the branch to containers
<br>
3- fork the repo 
<br>
4- clone the code to your editor
<br>
<br>
note : it's good to save the project next to the vagrant file 
# make 3 repos for our customised images in dockerhub 
![Screenshot from 2024-09-27 10-43-00](https://github.com/user-attachments/assets/6107592c-d44c-4ff8-9c75-45b14cbaa21f)


# App image Dockerfile (tomcat)
-we'll use multi-stage docker file cause we can't build the app in the same image
<br>
-we should find the right base image for our application
<br>
-you'll find the Dockerfile for this image in this location  /Docker-files/app/Dockerfile

# DB image Dockerfile (mysql)

-you'll find the Dockerfile for this image in this location  /Docker-files/db/Dockerfile



# nginx image Dockerfile (nginx)
-you'll find the Dockerfile for this image in this location  /Docker-files/web/Dockerfile
-put your own config next to the nginx Dockerfile


# Docker compose file
i'll attach the docker-compose.yaml file in the repo 

# Build & Run 
-login into vagrant vm 
```
vagrant ssh
```
-get inside the repo folder 

run the containers 
```
docker compose up -d
```


# access and verfiy our project via vm ip address
-check ip address 
```
ip addr show
```

![Screenshot from 2024-09-27 11-14-51](https://github.com/user-attachments/assets/0b6c7095-f265-419e-be4e-d2b7f508c9c4)












<br>






![Screenshot from 2024-09-27 11-15-11](https://github.com/user-attachments/assets/492305a3-0769-4dfb-bb92-68d49be9d1b8)







# congrats your app is working successfully













