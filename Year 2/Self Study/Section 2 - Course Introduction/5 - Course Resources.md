The repository for the course is held on. 
https://github.com/BretFisher/udemy-docker-mastery.git

[Docker Mastery Slides](https://att-c.udemycdn.com/2020-02-03_17-23-06-d5f5d03a46aae60940a9744989017523/original.zip?response-content-disposition=attachment%3B+filename%3DDocker%2BMastery%2BSlides%2B3.0.zip&Expires=1759791371&Signature=4UFaHNYOAz0eyXr6eB-CsnIX9AP5dsNhA35b3mM9n~ZmU8Ft4ck8ndgfghUOF-z6wnydRqBMVHWgBz9BBjLppXOKDquGUxZPTKh8GxR2lmDctg3IcXzD-xeZaJyptceY0gIm3r8bybk9u3NnVNj7uXlUODik4ud1lEmkXqS3c7b3gGF0JyvMNQTlaJkcTAmA~cPPWu-4pqdkKpBve2GPUR54v8sIMd1S9vI3O-lWf4mvy9Rbs0ELDPL-lWZiUxN1ycXEiAKvFSPOFdn~0kTrOmqkNbq54E3gcCZg0A7QAm7gVtFKXKv6RvUx07pN7td2C2tOp-otTWhWtxP763rCTQ__&Key-Pair-Id=K3MG148K9RIRF4)

[Docker Mastery Commands](https://att-c.udemycdn.com/2020-07-08_18-42-17-662f27224426662f3f3440675f0bc272/original.zip?response-content-disposition=attachment%3B+filename%3DDocker%2BMastery%2BCommands%2B2.0.zip&Expires=1759791258&Signature=2aB3ZKMyN-NuHNw-Z0wIOZW8XaTZMT5UJD7b2YIrkF9X~UYfKjWVvP80ud~Doly9gqUEFkraRKk7moe8MvGBADjXoSd-PfOoTOoQIwiM1RKLwYRegStKBHltIEpQvc2m-c5FxxqHrksEdFwKWwsvnW50BdFWfDlQeEqqIuVzfQxHv~dIHWn8XHHO~QTsK~Ym~W9f9SIAmq2KTG8w-ykv7-Yu6mJjq2k7L5mUswZ7vTTEnSe3XIU4maoQMxaf7a5v4oGdFfNyGpluFsT8a8ymPOM3bGCbaIvhipQcVkKqYnAbdp1~vaxD01~tOCKSjudUSe3RFUHTZu7KfI8dngRUJg__&Key-Pair-Id=K3MG148K9RIRF4)

[Docker Cheatsheet](https://att-c.udemycdn.com/2024-08-27_16-38-51-caff3d6655e071211fe50620bbbe7e38/original.pdf?response-content-disposition=attachment%3B+filename%3Ddocker_cheatsheet.pdf&Expires=1759791380&Signature=7lAyBYn~ACq0G9~LkzO3HtyrIKum4ChMw5UfyP4mqudxCrCvLxwfGkzd7bfTTn9ZE09cyG1Vn5hlp~jNmo~OX7OWQXHg6oZ4GSoCnMAxqyeWgpXd3h2-NGGhF324eS1FoxeJ6SPMnnFriW-ez6CHJaTikck5YpH~p7gkP75zkTrG7iI3T~4qeZUHq4gUqbFQNsf29Fipbaf~~zLUAyhJQBww972fvi5UiUzXZoiYNFst20b8diFjSuJ63xrEKmtTBXqPW0rXCNWhAen4-ItriU8l2AAL2hDWo2urCifBH4PVIu-TnmLYEdKP2kzdNI1tguiHuIFzBDp7v-UbAQTemw__&Key-Pair-Id=K3MG148K9RIRF4)

[Discord Server Link](https://devops.fan/)

[YouTube Channel for Q&A](https://www.youtube.com/channel/UC0NErq0RhP51iXx64ZmyVfg)

#### FAQs

This course has over 5,000 a month taking it! That's amazing to me. It also means we get lots of the same questions. Some are just things I didn't explain clearly. Some are minor issues people hit along the way. Here's the most common Q&A in order of frequency.

**NOTE: Don't read all these now, but remember to come back when you hit an issue, This list is the FASTEST way to solve your issues for common course troubles.**

#### Bind for 0.0.0.0:80 failed: port is already allocated. -OR- port already in use -OR- permission denied.

This will happen if you are attempting to start a new container with a port that is already in-use on your machine. Remember in TCP/UDP, only one application/service can use a single IP+PORT at a time. This doesn’t change with containers when you use `-p`  to bind to the host IP+PORT.

**You'll need to either stop the app that's using that port, or just run your container on a different (available) port.**

First run `docker ps` to check if there are any containers using this port - if there are not; you likely have a non-Docker related application running on your machine that is using this port. Maybe IIS, maybe Apache, etc.

If you are on a Mac, you can check what is using the port with the command: `lsof -i :<port>`  

If you are on Windows, you can check what is using which port with: `netstat`  

Of course - if you don’t have a reason to specifically use the port that is throwing this error, simply run your container on another port. Remember, the syntax is `<host port>:<container port>`  , so binding to port 8888 on your host machine with a container that uses port 80, would look like: `docker container run -p 8888:80 your_image`  

#### What happened to Docker Toolbox?

It was deprecated by Docker in lieu of Docker Desktop, which now works on all editions of Windows 10/11, macOS, and Linux Desktop.  If you want a multi-node setup locally, then [Multipass](https://multipass.run/) is a good replacement for Toolbox.  

#### $(pwd) in Windows is getting an error for bind-mounts: C:\Program Files\Docker Toolbox\docker.exe: invalid reference format.

First, you should no longer be using CMD.exe (Command Prompt) or PowerShell for Docker commands, because it tends to be a lot easier to just run them from a WSL Linux (bash/zsh) command where `$(pwd)` will work. But, if you'd like more info on the "why", read on.

PowerShell has a few minor differences in command format. This is a PowerShell thing, not a docker thing. When using the shell path shortcut "pwd":

For PowerShell use: `${pwd}` 

For cmd.exe "Command Prompt use: `%cd%`

bash, sh, zsh, and Docker Toolbox Quickstart Terminal use: `$(pwd)` 

Note, if you have spaces in your path, you'll usually need to quote the whole path in the docker command.

There's another issue sometimes seen, where other apps can mess up your path: [https://stackoverflow.com/questions/50608301/docker-mounted-volume-adds-c-to-end-of-windows-path-when-translating-from-linux](https://stackoverflow.com/questions/50608301/docker-mounted-volume-adds-c-to-end-of-windows-path-when-translating-from-linux)

#### I hit Ctrl-C in Windows, and the Container is still running

I recommend you use WSL Linux with bash or zsh to avoid this quirky inconsistency. If you'd like to know more, read on:

In Windows, there's a quirk with the built-in Powershell and Command Prompt terminals. They don't interpret ctrl-c the same way as Linux, Unix, and macOS. They won't shutdown the container, and you'll need to use `docker stop` commands.

#### How do I cleanup space (images etc.)?

Run prune commands [https://www.udemy.com/docker-mastery/learn/v4/t/lecture/7407918?start=0](https://www.udemy.com/docker-mastery/learn/v4/t/lecture/7407918?start=0)

#### Bind Mount Won't Show Up In Container

This is usually a Docker for Windows issue, where you need to go into Docker Settings GUI (lower right icon) and uncheck the drive where your code is, then save, and then re-check that drive to re-apply the file sharing permissions between the Linux VM and the Windows OS.

#### Starting container process caused "exec: \"ping\": executable file not found in $PATH": unknown

That error is telling you that ping is not available in the image you’re trying to run it from. Official images have changed over time and the official nginx default image (nginx:latest) no longer has ping in it by default.  Image nginx:alpine should still have ping installed (a few of my videos show utilities like ping that are no longer in those images).

If it's a debian-based image (the default nginx) then you can also use `apt-get update && apt-get install -y iputils-ping`   inside the container to install it.

Lastly, I keep a “bunch of troubleshooting and handy admin utilities” in an image here that you can run ping from: `bretfisher/netshoot`  

[https://www.udemy.com/docker-mastery/learn/v4/questions/3751216](https://www.udemy.com/docker-mastery/learn/v4/questions/3751216)

#### Starting mysql container and running ps causes "ps: command not found"

Like above, this is the container shell telling you the binary "ps" isn't in your path, and not installed in the container. Docker changed the mysql image after the video was recorded and removed the ps utility. You can add it back in using the apt package manager.

`apt-get update && apt-get install procps`

For more info: [https://stackoverflow.com/questions/26982274/ps-command-doesnt-work-in-docker-container](https://stackoverflow.com/questions/26982274/ps-command-doesnt-work-in-docker-container)

#### How to run two container websites on a single port in Docker or Swarm services

This is a bit more advanced, but common for production Swarms. You'll need a "reverse proxy"

[https://www.udemy.com/docker-mastery/learn/v4/questions/3931678](https://www.udemy.com/docker-mastery/learn/v4/questions/3931678)  

#### Error response from daemon: pull access denied.

Double and triple-check the spelling of the image you are pulling; if you are attempting to pull a publicly hosted image - this error will not occur, but if there is a typo and Docker can’t find the image - it will expect that it is a private image and ask you to login.

Also, there are times when the config.json file gets messed up, so try docker logout && docker login. If all that still causes the same issue, try removing `~/.docker/config.json`  and then pull again.

#### Kubernetes vs. Swarm.

I have a dedicated lecture for this: 

[https://www.udemy.com/course/docker-mastery/learn/lecture/15094976](https://www.udemy.com/course/docker-mastery/learn/lecture/15094976)

#### Does this help with Docker Certified Associate?

Yes, but it’s not a study guide. Here’s the Lecture with info: [https://www.udemy.com/docker-mastery/learn/v4/t/lecture/9485678?start=0](https://www.udemy.com/docker-mastery/learn/v4/t/lecture/9485678?start=0)

#### Ubuntu Container vs. Ubuntu OS, What's the Difference?

[https://www.udemy.com/docker-mastery/learn/v4/questions/5390204](https://www.udemy.com/docker-mastery/learn/v4/questions/5390204)

#### How to use volumes in Swarm for databases.

[https://www.udemy.com/docker-mastery/learn/v4/questions/2675184](https://www.udemy.com/docker-mastery/learn/v4/questions/2675184)

#### How do we do backups in docker?

[https://www.udemy.com/docker-mastery/learn/v4/questions/2756448](https://www.udemy.com/docker-mastery/learn/v4/questions/2756448)

#### Getting a shell in VM’s that run Docker

Workaround: [https://www.udemy.com/docker-mastery/learn/v4/questions/3860412](https://www.udemy.com/docker-mastery/learn/v4/questions/3860412)

`docker run -it --rm --privileged --pid=host justincormack/nsenter1`  

macOS [https://www.bretfisher.com/docker-for-mac-commands-for-getting-into-local-docker-vm/](https://www.bretfisher.com/docker-for-mac-commands-for-getting-into-local-docker-vm/)

Docker for Windows [https://www.bretfisher.com/getting-a-shell-in-the-docker-for-windows-vm/](https://www.bretfisher.com/getting-a-shell-in-the-docker-for-windows-vm/)

Docker Toolbox `docker-machine ssh default`  

#### Windows firewalls preventing networking or bind mounts in containers

[https://www.udemy.com/docker-mastery/learn/v4/questions/3258290](https://www.udemy.com/docker-mastery/learn/v4/questions/3258290)

#### Anti-Virus Blocking file sharing in Windows

[https://www.udemy.com/docker-mastery/learn/v4/questions/3442460](https://www.udemy.com/docker-mastery/learn/v4/questions/3442460)

#### Are containers more secure than VM’s?

[https://www.udemy.com/docker-mastery/learn/v4/questions/4020880](https://www.udemy.com/docker-mastery/learn/v4/questions/4020880)

#### I have a network proxy and images won’t build

[https://stackoverflow.com/questions/23111631/cannot-download-docker-images-behind-a-proxy/](https://stackoverflow.com/questions/23111631/cannot-download-docker-images-behind-a-proxy/)

#### Public vs. Private IP for Swarm advertise-addr and data-path-addr

[https://www.udemy.com/docker-mastery/learn/v4/questions/3710518](https://www.udemy.com/docker-mastery/learn/v4/questions/3710518)

#### Custom Docker Networks, macvlan and IP setting hardcoding

[https://www.udemy.com/docker-mastery/learn/v4/questions/3706540](https://www.udemy.com/docker-mastery/learn/v4/questions/3706540)
