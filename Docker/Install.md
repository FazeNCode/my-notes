<h2> Installation: </h2>

<h4> Install prerequisite packages, which will allow apt to use packages over HTTPS </h4>
sudo apt install apt-transport-https ca-certificates curl software-properties-common



<h4>Update the package database with Docker packages:</h4>

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

<h4>Install docker: </h4>

```
sudo apt install docker-ce
```
