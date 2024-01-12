

<h2> Installing on Redhat / CentOS </h2>
```
yum install podman
```

```
yum install podman @container-tools
```

```
yum module install container-tools
```

<p> Loging redhad registry gives you ability to pull all sorts of images, without any 
restrictions
</p>
```
podman login registry.redhat.io
```






<h2> Pull a container image </h2>
```
podman search [httpd] | less 
```

search for what you want to install/pull

podman pull docker.io/library/httpd
we will pull the httpd apache web server in this example.

podman images 
To view the images on the system.

podman rmi [IMAGE ID OR SERVICE NAME]
To delete any images on the system

Check the running container 
```
podman ps
```


 <h2> Run a container </h2>

 -d flag means deattached 
--name give the name of the container
6e794a483258 is the Image ID

```
podman run -d --name web1 6e794a483258
```

Check stopped and running container 
```
podman ps -a
```


-d flag means detached
--name flag means name of the image
-p flag means port 
```
poadman run -d --name web2 -p 8080:80 6e794a483258
```


podman run -it 6e794a483258 /bin/bash
-it flag stands for interactive 

curl localhost:8080

podman stop web1 
To stop the container



Map the container to a local directory 
```
mkdir -p /example/directory 
touch /example/directory/file.txt
podman run -d --name web3 -p 8081:80 -v /web:/example/directory 6e794a483258
```



Run the container as a service
