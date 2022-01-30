# dr0-docker
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
 Dockerfile - 

#### Requirments:
As we can see from steps, running our poroject requires Node JS with npm, docker engine

#### Use(Linux based):
1. We have to navigate inside docker directory where we put in all our files(using terminal):
 `cd /PATH/visits`
2. 


