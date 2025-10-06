Three docker innovation

Docker Image
Docker Registrary
Docker Container

Called build, ship, + run

The main thing behind docker is to take uncontainered software, put it in a registrary and then put it in a container. 

**Docker/Container Image**

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