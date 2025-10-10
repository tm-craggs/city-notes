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

Example: `docker container run --publish 80:80 --detach nginx`

This command will give us back the container ID, each time you run a new container you get a new, unique, ID

We can view the container by the command

`docker container ls`

If we want to stop this container, run:

`docker container stop [ID]`

Note: it will fuzzy match this, you only need to type in the first few digits, enough for it to be unique. 

Now we have used `run` twice, if we do `docker container ls -a`, this will show us 2 containers. This is because the -a flag shows us all containers, not just the ones that are active.

But why do we have 2 containers? This is because we used the `docker run` command, as opposed to the `docker start` command. 

`docker run` **always starts a new container**. Use `docker start` to start an existing stopped one. 

Docker co