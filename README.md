# first docker project 


in this project we attempt to dockerize a next js application 

 next js is a react framework for building web applications 
 it is based on react and node js


 in this project all we have is a simple next js application that displays hello world 
 on the '/' route
 we will dockerize this application using a dockerfile and a docker compose file

## instructions to clone this repository 


```bash
git clone https://github.com/atoms19/hello-world-docker
```

then 

```bash
cd hello-world-docker
```


This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).
bootstrapping here means the process of setting up a new project with all the necessary files and configurations

##  starting docker 

ensure that docker is installed on your machine
you can check if docker is installed by running the following command 

```bash
docker --version
```
it should return the version of docker installed on your machine

ensure that you have docker daemon running on your machine
on windows and macos you can check this by looking for the docker icon in the system tray
on linux you can check this by running the following command
```bash
systemctl status docker
```
you can start the docker daemon by running the following command
```bash
systemctl start docker
```
or in windows and macos you can start it by clicking on the docker icon or clicking start docker engine 
in docker desktop application




## building the docker image
after you have cloned the repository and navigated into it
you can build the docker image by running the following command
```bash
docker build -t hello-world-docker .
```
this will build the docker image and tag it with the name hello-world-docker
you can see the list of docker images on your machine by running the following command
```bash
docker images
```
if your image is listed there then it means that the image was built successfully


# running the docker container
after building the docker image you can run the docker container by running the following command
an instance of an image is called a container
```bash
docker run -p 3000:3000 hello-world-docker
```

here 3000:3000 mean we are mapping the port 3000 of the host machine ( your machine ) to the port 3000 of the container

you can now open your browser and navigate to http://localhost:3000

you should see the text " hello world " displayed on the page

## advantages 
for doing this you didnt have to install node js or next js on your machine
all you needed was docker installed on your machine




## cleaning up
after you are done with running the docker container you can clean up by stopping and removing the docker container and image

### stopping the docker container

you can see the list of running docker containers by running the following command
```bash
docker ps
```
this will list all the running docker containers on your machine

to stop a running docker container you can run the following command
```bash
docker stop <container_id>
```

container_id is automatically generated when you run a docker container
you can get the container_id from the output of the docker ps command
for example if the container_id is abc123 you can stop the container by running the following command
```bash
docker stop abc123
```

### removing the docker container
after stopping the docker container you can remove it by running the following command
```bash
docker rm <container_id>
```

### removing the docker image
after removing the docker container you can remove the docker image by running the following command
```bash
docker rmi hello-world-docker
```
