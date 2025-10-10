**Reminder**: Image vs Container

- An image is the application we want to run
- A container is an instance of that image running a process.
- You can have many containers running off the same image. 
- In this lecture our image will be an Nginx server
- Dockers deafult image registry is called the docker hub


To start the server

`docker container run --publish 80:80 nginx`

What did this command do?

1. Downloaded image `nginx` from Docker Hub
2. Started a new container from that image
3. Opened port 80 on the host IP
4. Routes that traffic to the container IP, port 80

This command opens in your current shell window, if you want to run it in the background, add the flag `--detach`

Example: `docker container run -`