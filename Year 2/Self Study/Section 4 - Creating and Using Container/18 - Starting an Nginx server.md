**Reminder**: Image vs Container

- An image is the application we want to run
- A container is an instance of that image running a process.
- You can have many containers running off the same image. 
- In this lecture our image will be an Nginx server
- Dockers deafult image registry is called the docker hub


To start the server

`docker container run --publish 80:80 nginx`
