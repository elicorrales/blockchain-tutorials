# Install Docker (Engine only) on WSL Ubuntu 20.04  
  
### Caviat: I was not able to get Docker working on Ubuntu 22.04 using the below method.  
It does work if you go the Docker Desktop route.  
<br/>
```
sudo apt update && sudo apt -y upgrade
```


Uninstall old versions  
Older versions of Docker were called docker, docker.io, or docker-engine. If these are installed, uninstall them:  
```
sudo apt-get remove docker docker-engine docker.io containerd runc
```
  
It’s OK if apt-get reports that none of these packages are installed.  
  
Install using the repository  
  
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.  
  
Set up the repository
  
Update the apt package index and install packages to allow apt to use a repository over HTTPS:  

```
sudo apt update && sudo apt -y upgrade
```
```
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
  
Add Docker’s official GPG key:  
```
sudo mkdir -p /etc/apt/keyrings
```
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
  
Use the following command to set up the repository:  
```
echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
  
Install Docker Engine  

Update the apt package index, and install the latest version of Docker Engine, containerd, and Docker Compose, or go to the next step to install a specific version:  
```
sudo apt update
```
```
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
  
Verify that Docker Engine is installed correctly by running the hello-world image.
```
sudo docker run hello-world
```
  
IF ERROR:
```
sudo docker run hello-world
docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?.
See 'docker run --help'.
```
THEN DO:  
```
sudo service docker start
```
```
sudo service docker start
 * Starting Docker: docker

```
```
 sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
Digest: sha256:53f1bbee2f52c39e41682ee1d388285290c5c8a76cc92b42687eecf38e0af3f0
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```


# Install Portainer

```
sudo docker volume create portainer_data
```

```
sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data \
    portainer/portainer-ce:latest
```
  
You can the point a browser to either the HTTP(8000) or HTTPS(9443) port and you'll see the portainer start-page.  
Once you get past that, near center there should be a box speaking about your local environment, just click it.  
Left-Nav pane should also have Images and Containers; you'll probably use those a lot.
