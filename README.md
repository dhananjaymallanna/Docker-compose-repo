# In this repo i am creating the templates for using docker compose on your local machine, feel free to download these and use freely.

# why docker-compose?
1. As you are aware we tend to install a lot of softwares on our machine for local development, Instead we can use docker to our leverage and keep out laptop clean.
2. this help us keep the development environment consistant across the team, so no more "works on my machine" things.
3. faster and easier mean to setup the env
4. code managed thing, so nothing can miss out.

# Step to use this thing:
 1. goto https://docs.docker.com/desktop/
 2. install appropriate version the one and only software you need for setup
 3. verify that this is working
 4. download docker compose into a folder
```
docker compose up -- getting all conatiner up - pull the images, read config and deploy on docker
docker compose down -- to bring down the containers
docker compose ps -- geting status of the containers running
docker compose start -- start all containers
docker compose stop -- start all containers
```
![Alt text](https://media.geeksforgeeks.org/wp-content/uploads/20230419174014/Docker-hub-registry.webp)

# To build image from springboot

mvn spring-boot:build-image

## Push image to Docker Registry

goto <https://hub.docker.com> and register
docker login -u username
docker tag imagename:tagname username/imagename:tagname
docker push username/imagename:tagname

```md
Note:: [INFO] Successfully built image 'docker.io/library/imagename:tagname'
```
## Via Dockerfile
```
FROM ubuntu

# install app dependencies
RUN apt-get update && apt-get install -y python3 python3-pip
RUN pip install flask==2.1.*

# install app
COPY hello.py /

# final configuration
ENV FLASK_APP=hello
EXPOSE 8000
CMD flask run --host 0.0.0.0 --port 8000
```
