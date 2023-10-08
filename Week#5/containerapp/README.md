## Build and Test the Image
1.Build the image:

`docker build . -t web`

2.Check that we have the web image:

`docker image ls` 

3.Launch Docker based on the web image:

`docker run -dt -p 8080:80 --name web01 web` 

4.Once it is finished running, check that the website has been launched:

`curl localhost:8080` 
We will get the HTML for the website.

5.Copy the public IP address provided on the lab page, and paste it into a new browser tab. We'll know it worked correctly when the Container Hub website appears.
http://sandboxdevops.southeastasia.cloudapp.azure.com:8080/

## Tagging and Pushing Images to DockerHub

Prerequisite:
- Docker Hub Account

Log in to Docker Hub

`docker login -u supiwmi`

Build the image:

`docker image build -t <USERNAME>/appname:`

### Get the Git Commit Hash
ต้องทำ git init แล้วสั่ง commitเพื่อให้ได้ log มาก่อน

```
cd ~/containerhub 
git log -1 --pretty=%H
``` 

### Build the weather-app Image
Now let's move up a directory (Dockerfile exist) and build the image:

E.g. docker image build -t [USERNAME]/weather-app:[HASH] --build-arg VERSION=1.5 . 
``` 
docker image build -t supiwmi/simpleweb:d031aeb892d1c3d5364c459d65bb13b62c30a303 --build-arg VERSION=1.5 .
docker images
```

### Tag the weather-app Image as Latest
E.g. docker image tag [USERNAME]/weather-app:[HASH] [USERNAME]/weather-app:latest
```
docker image tag supiwmi/simpleweb:d031aeb892d1c3d5364c459d65bb13b62c30a303 supiwmi/simpleweb:latest
```

### Push Both Images to Docker Hub
E.g.docker image push [USERNAME]/weather-app:[HASH]

`docker image push supiwmi/simpleweb:d031aeb892d1c3d5364c459d65bb13b62c30a303` 

E.g. docker image push [USERNAME]/weather-app:latest

`docker image push supiwmi/simpleweb:latest` 


## Check image on Docker Hub

https://hub.docker.com/repositories/supiwmi
