So much more happens under the hood when we run a container. 

1. Looks for that image locally in image cache, doesn't find anything. 
2. Then looks in remote repository (default to Docker Hub)
3. Downloads the latest version
4. Creates new container based on that image and prepares to start
5. Gives it a virtual IP on a private network inside docker engine. 
6. Opens up port 80 on host and forwards to port 80 in container. 
7. Starts container by using the CMD in the image dockerfile. 

You can actually change all of these in the command line by passing flag, such as the version, CMD command, ports, and more. Most of these are just defaults. 