
Docker is an open-source containerization platform, which allows users to create containrized operating systems, with only mandatory packages installed to run the OS

Docker Images are very small and light weight, compared to traditional virtual machines.

Docker has a large ecosystem and an active community. The Docker Hub serves as a centralized repository for sharing and discovering container images.

<br>
<h2> Docker Components: </h2>

<h5> Docker Daemon: </h5>
This is also called Docker Engine, it is a background process which runs on the host system responsible for building and running containers.
<br>

<h5> Docker Client: </h5>
Command line tool used by the user to interact with the Docker daemon.
<br>

<h5>Docker Image: </h5>
Image is an immutable file. Essentially a snapshot of a container.
<br>

<h5> Docker Container: </h5>
This is a running instance of a docker image with an application and its dependencies. 
Each container has a unique process ID and is isolated from other containers, the only thing containers share is the Kernel.
<br>

<h5>Docker Registry: </h5>
Application responsible for managing storage and delivery of Docker container images. It can be private or public.
<br>

<h5>Docker Compose: </h5>
A tool used to define and run multi-container Docker applications.
Kubernetes, is a container orchestration system 
