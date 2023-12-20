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



<h2> Configuration of docker </h2> --
If you want to use docker without the need of running sudo everytime you run docker, put the user in the docker group by running the command below

```
usermod -aG docker faze
```

To confirm docker has been installed and configured 
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
