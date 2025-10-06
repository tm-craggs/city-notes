The core principle of docker is **build, ship, run**. The idea that we can take the software which we made on **one machine**, and all of its **dependencies**, and run it exactly that **same way on another system**. 

Build Ship, Run is divided amongst the **three key innovations** of docker.

- The Docker Image - Build
- The Docker Registrary - Ship
- Docker Container - Run

#### Docker Image

- Also called the **container image**
- Universal app packager
- Never been anything before that is completely cross platform and application language agnostic
- Dockerfile - The instructions that are used to make your image

Example Dockerfile
```dockerfile
FROM python
RUN pip install flask
COPY ..
CMD python app.py
```

It runs top down through image layers. `FROM python` installs everything Python needs to run. Next, it install flask, which is a dependency for the app. All of these together creates a docker image, that is created through the command `docker build`

#### Docker Registry

- Docker registry is for application distribution
- It is like a package manager for a Linux distribution
- All sorts of websites have docker registries where you can store docker images (docker hub, GitHub. etc.)
- Each docker file has a SHA Hash to confirm that the image is authentic.
- You can use `docker push` to push up to a docker registry, can also do a `docker pull` on a different machine. 

#### Docker Container

- Once we have built the image and put it in a location where we can access it, such as a server. We often get this from running `docker pull`
- The server will be running the Docker engine in the background. 
- Once the image is downloaded onto that machine, we can run the command `docker run [image-name]` to run the app in its own container. 
- That container is known as a **namespace**, prevents it from seeing any of the other system files. 
- It gets its own file system, IP address, process list. 
- It essentially looks like its own system. 
- If we run the `docker run` command again, we will get another process. They will run side by side, but will not see each other and will be completely separate. 
- If you change a file in one container, by 
