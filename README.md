# dr0-docker :sweat_smile:
Simple docker project with purpose of counting vistis on a specific web page.
Project is classsic example of docker usage.

In order to build our image we will need 2 separate components:
1. Some type of web server, something that will respond to our http request and generate some html to show inside of browser.
2. To acctually store the number this site has been visited we will need redis-server, redis is in memory data store (like a tiny database that sits only inside of memory)

#### Steps we went through while making our application:
1. Created Node JS web app
2. Created a Dockerfile
3. Built image from dockerfile
4. Ran image as container
5. Connected to web app from browser

First we created our working directory, navigated to it and opened or visual studio code inside of it:
`mkdir visits` then `cd visits` then open our code editior `code .`
Here we gonna have 4 separate files:
 package.json - thats going to record all dependencies of our application
 index.js - which will server as an actual node server
 Dockerfile - containing docker container instructions
 docker-compose.yml - help us to start multiple docker containers at the same time and connect them together in some automated fashion.


 This project is example of basic usage of docker-compose, we created 2 separate services and docker-compose automatically made connection between them. 
The key thing to keep in mind here, in order to communicate between these two we use the host name of the name of that other service/container and that name is specified inside our docker-compose file. Anywhere you would usually put the url of container u can instead just list the name of that other container and the host name will be automatically resolved by docker.
#### Requirments:
As we can see from steps, running our poroject requires Node JS with npm, docker engine

#### Use(Linux based):
 
1. We have to navigate inside docker directory where we put in all our files(using terminal):
 `cd /PATH/visits`
 
2. Then we need to build our docker image(since we are having docker-compose.yml we are able to start it instantly after build process is finished):
 `docker-compose up --build`

3. I used port 4001 on my localhost, while port 8081 is inside of the machine, so open your browser and type: [localhost:4001](https://localhost:4001) 
 If u want to use another port on your local machine, you can simply change it inside of docker-compose.yml file, while for changing containers port you have to  
 change index.js file as well. And thats all you need to run this application.

#### Down below are steps we would have to go trough if we had not implemented docker-compose.yml file.

2.1 If u want to work with dockers id):
  `docker build .` 
  
2.2 Also you can tag your docker image by giving it a name so that we dont need to care about his id all the time:
`docker build -t <your_dockers_name>/<name_of_projects_dir>:latest .`
 
here is example of how i used it, I picked my name for docker name, and projects dir is named visits, `.` at the end specifies that we want to build docker from current directory

 `docker build -t stefan/visits:latest .`

3. Start redis-server docker: `docker run redis`
 
4. Now we should be able to start our application by running:
   `docker run <dockers_name>/<name_of_projects_dir>`
  
  In my case that would be: 
  `docker run stefan/visits`
  
 5. Now we have 2 separate containers runnng and we must establish a connection..


 
  
  


<use your specific names inside>
