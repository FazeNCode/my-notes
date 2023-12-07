
Docker is an open-source containerization platform, which allows users to create containrized operating systems, with only mandatory packages installed to run the OS

Docker Images are very small and light weight, compared to traditional virtual machines.

Docker has a large ecosystem and an active community. The Docker Hub serves as a centralized repository for sharing and discovering container images.


Docker Components:

Docker Daemon: 
This is also called Docker Engine, it is a background process which runs on the host system responsible for building and running containers.

Docker Client: 
Command line tool used by the user to interact with the Docker daemon.

Docker Image:
Image is an immutable file. Essentially a snapshot of a container.

Docker Container: 
This is a running instance of a docker image with an application and its dependencies. 
Each container has a unique process ID and is isolated from other containers, the only thing containers share is the Kernel.

Docker Registry: 
Application responsible for managing storage and delivery of Docker container images. It can be private or public.

Docker Compose:
A tool used to define and run multi-container Docker applications.
Kubernetes, is a container orchestration system 
