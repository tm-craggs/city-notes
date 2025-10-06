[Play with Docker](https://labs.play-with-docker.com/p/d3htc6i91nsg00e4us1g#d3htc6i9_d3htc7q91nsg00e4us20) is a good website for running some online containers and seeing how docker works. You can create docker instances for free and interact through a command line. 

Docker is a **two-part system** you will be using the docker command line client, to talk to the docker engine through a number of protocols (Socket, TCP/TLS, SSH Tunnel)

The commands you type are in a version (a binary or exe), this will be talking to the engine in the background that will execute, via the API, the commands which we are telling it. 

Here is an example of starting a docker container, running an apache web server:


```
docker version
```

This is a simple command that you can use to check that docker is installed, accessible, and up to date for both the Client, and Server.

```
docker run -d -p 8800:80 httpd
```

This command starts am Apache server running in a docker container. `-d` is shorthand for **detached** meaning the container will be running in the background. `-p` stands for open a port and **publish**, 8800 is the listening port on our local host, and tell it to go into the container on port 80, where Apache is listening. `httpd` is the name of the docker image which Apache is running on. 

Imagine it like port forwarding. The first port is the port that Docker is listening to externally, the second port is the port that it will be forwarded to in the containers local networking. This is saying, take all the traffic from local port 8800, and sent it to port 80 of the local container. 

```
curl localhost:8800
```

This command proves that it is working, showing us the webpage hosted in the local port. 

```
docker ps
```

This shows us a list of all the container processes running. 

We can start up another Apache server, to run in a separate container. These processes will not be able to interfere with each other. However, the new instance **must be hosted on a different public port**. 

```
docker run -d -p 8801:80 httpd
```

This command will run successfully and show the new process in `docker ps`. If we did not change the public port, this would have returned an error. 

#### What happens when you use `docker run`?

![[image-58.png|396x481]]

This is a visualisation of what we just did. Docker works through layers, so the image sits on top of the Docker layer, which itself sits above our Linux host. 

`docker run` automatically downloads the image. This can also be manually done with `docker pull`.

#### Major Linux features used by Docker

- `namespaces`
- `cg groups`
- `veth`
- `iptables`
- `union mount`

