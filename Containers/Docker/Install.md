<h2> Installing Docker on Ubuntu: </h2>

<h4> Install prerequisite packages, which will allow apt to use packages over HTTPS </h4>
sudo apt install apt-transport-https ca-certificates curl software-properties-common



<h4>Update the package database with Docker packages:</h4>

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

<h4> Install docker and it's nesesscary components: </h4>

```
sudo apt install docker-ce
```



<h2> Configuration of docker </h2>
If you want to use docker without the need of running sudo everytime you run docker, put the user in the docker group by running the command below

```
usermod -aG docker faze
```

To confirm docker has been installed and configured run docker hello-world
```
docker hello-world
```

Info will provide important information regarding docker, such as 
- Running containers  
- Stopped container  
- Docker Version  
- Images

```
docker info 
```

 You will need to configure your docker hub user on the server you wish to utilize docker. Once configurerd you will be able to pull various images from docker hub, which is docker's repository containing all sorts of images.

Note: not all images require you to login.

```
docker login
```

View all active and inactive containers,
- Status of container
- Container ID's
- Creation date of the contaier 

```
docker ps -a
```


<h3> Container Usage: </h3>

search for a Docker container specifically ubuntu
```
docker search ubuntu
```

In order to utilize a containerized operating system of your choice, you must pull the image first. The mpull command will fetch the os from docker's repostiroy hub. Repostiroies can be public and private.
```
docker pull ubuntu
```

Initiates the creation of a fresh container instance from the specified image. Runs the docker container in the foreground. 
```
docker run ubuntu
```

Initiates the creation of a fresh container instance from the specified image in interactive mode  
```
docker run -it ubuntu
```

You must start the container before entering and utilizing the container.
when you "exit" from the container you must start the container.
```
docker start [container-id]
```

Starts an interactive shell within the container, allows you to run commands, inspect files or make configuration changes. Does not connect to the main process. 
--rm flag automatically removes the container after we stop using it. 
A more versatile command compared to docker attach.

```
docker exec -it container_id /bin/bash
```

To connect your terminal to the main process of a container. -i interactive | -t tty terminal
Used to observe or interact with the logs or real-time output of the main process.
```
docker attach [container-id]
```

Docker image names can only be lowercase.
```
docker commit -p container_id new_container_name
```

You can create a Docker volume anywhere on your PC.
```
sudo mkdir -p Docker_Share
```
 



Juice shop is used for web application pen-testing, paired with burp suite.
```
docker pull bkimminich/juice-shop
```

Damn Vulnerable Web application is used for web application pen-testing, such as mySQL injection.

```
docker pull vulnerables/web-dvwa
```
