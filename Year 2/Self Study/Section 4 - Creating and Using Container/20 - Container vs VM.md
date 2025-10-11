You often see people comparing containers to VMs, there are some similarities in function but very different in the way they work. Containers are **not** just mini VMs

- They are just processes running on your host operating system
- They are limited to what resources they can access
- They exit when process stops

For example, if we create a container running mongo, we will see the processes when you run, `docker container top mongo`

However, you will also see these processes in your host, as they are processes on your system. You will need to connect to the docker VM itself to see these on Mac or Windows.

They do run on a different process ID to the rest of the system due to the security features, but it is important to stress that the process is not hiding away somewhere we can't access inside a Virtual Machine, it is right there, on our system. When we stop the container, this process disappears. 