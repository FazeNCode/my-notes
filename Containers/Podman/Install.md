1.) Pull a container image 
podman search [httpd] | less 
search for what you want to install/pull

podman pull docker.io/library/httpd
we will pull the httpd apache web server in this example.

podman images 
To view the images on the system.

podman rmi [IMAGE ID OR SERVICE NAME]
To delete any images on the system



2.) Run a container 

podman run -d --name web1 6e794a483258
-d flag means deattached 
--name give the name of the container
6e794a483258 is the Image ID

podman ps
To check the running container

poadman run -d --name web2 -p 8080:80 6e794a483258
-d flag means detached
--name flag means name of the image
-p flag means port 


podman run -it 6e794a483258 /bin/bash
-it flag stands for interactive 

curl localhost:8080

podman stop web1 
To stop the container



3.) Map the container to a local directory 
mkdir -p /example/directory 
touch /example/directory/file.txt
podman run -d --name web3 -p 8081:80 -v /web:/example/directory 6e794a483258


4.) Run the container as a service
