
Docker is an open-source containerization platform, which allows users to create containrized operating systems, with only mandatory packages installed to run the OS

Docker Images are very small and light weight, compared to traditional virtual machines.

Docker has a large ecosystem and an active community. The Docker Hub serves as a centralized repository for sharing and discovering container images.

<br>
<h2> Docker Components: </h2>

<h3> Docker Daemon: </h3>
This is also called Docker Engine, it is a background process which runs on the host system responsible for building and running containers.
<br>

<h3> Docker Client: </h3>
Command line tool used by the user to interact with the Docker daemon.
<br>

<h3>Docker Image: </h3>
Image is an immutable file. Essentially a snapshot of a container.
<br>

<h3> Docker Container: </h3>
This is a running instance of a docker image with an application and its dependencies. 
Each container has a unique process ID and is isolated from other containers, the only thing containers share is the Kernel.
<br>

<h3>Docker Registry: </h3>
Application responsible for managing storage and delivery of Docker container images. It can be private or public.
<br>

<h3>Docker Compose: </h3>
A tool used to define and run multi-container Docker applications.
Kubernetes, is a container orchestration system 
