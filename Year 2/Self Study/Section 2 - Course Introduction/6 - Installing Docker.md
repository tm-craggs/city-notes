-  Docker runs on all sorts of devices from laptops, servers to raspberry pi. 
- Docker Inc. now primarily focuses on Docker Desktop, for Windows, Linux and MacOS
- Docker Desktop is a bundle of different tools, Docker Desktop is not meant for servers. That would be docker engine. 
- Docker desktop is free for personal use, but not open source. Although many of the tools it is bundled with are. 

Docker desktop includes:

- `Engine`
- `CLI`
- `Compose`
- `BuildKit`
- `Kubernetes`
- `scan`, `sbom` and more

For learning, running local is best.

Most containers run on a Linux kernel, and a tiny file system. DD handles all of that, mac and Windows require a Linux VM. I am using Linux for this course. 

There are 3 major ways to run containers. We will be starting with local. 

- Locally (Docker Desktop, RD)
- Servers (Docker Engine, K8s)
- PaaS (Cloud Run, Fargate)

