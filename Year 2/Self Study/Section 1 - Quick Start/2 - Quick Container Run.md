[Play with Docker](https://labs.play-with-docker.com/p/d3htc6i91nsg00e4us1g#d3htc6i9_d3htc7q91nsg00e4us20) is a good website for running some online containers and seeing how docker works. You can create docker instances for free and interact through a command line. 

Docker is a **two-part system** you will be using the docker command line client, to talk to the docker engine through a number of protocols (Socket, TCP/TLS, SSH Tunnel)

The commands you type are in a version (a binary or exe), this will be talking to the engine in the background that will execute, via the API, the commands which we are telling it. 

Commands which I have run:

```
docker version
```

This is a simple command that you can use to check that docker is installed, accessible, and up to date for both the Client, and Server.

```
docker run -d -p 8800:80 httpd
```

```
curl localhost:8800
```

```
docker ps
```

