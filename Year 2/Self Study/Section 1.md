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

It runs top down through image layers. The first layer is the app, `FROM python`