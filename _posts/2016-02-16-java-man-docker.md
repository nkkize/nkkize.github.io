---
layout: post
title: Creating and Publishing Your First Docker Image
date: 2016-02-16 13:32:20 +0300
description: Creating and Publishing your first docker Image
img: i-docker.png
fig-caption: # Add figcaption (optional)
tags: [docker, java, maven]
---

## Creating and Publishing your own docker Image 
In this post, we will create our own docker image and push it in docker hub.  
We will shipping the image prebuilt with jdk, and maven.

### Creating the image
```
$ sudo docker pull ubuntu
```
Create a container from the Ubuntu image:
```
$ sudo docker run -it --name ${container_name} ubuntu:latest
eg.
$ sudo docker run -it --name javaimg ubuntu:latest
```
### Manually installing java in the container
Create a folder /java in container you just created
```
mkdir /java
```
On base machine download jdk (.tar.gz file) from Oracle (http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
Copy the downloaded file from base machine to the /java folder in docker container you just created. From the directory where file is downloaded run:
```
sudo tar -cv jdk-8u91-linux-x64.tar.gz | sudo docker exec -i javaimg tar x -C /java
```
Inside container go to /java and extract the jdk file
```
tar -xvzf jdk-8u91-linux-x64.tar.gz
```
Move the extracted contents to /usr/lib/jvm folder
```
sudo mv /java/jdk1.8.0_91/ /usr/lib/jvm/oracle_jdk8
```
Add new jdk alternatives
```
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/oracle_jdk8/jre/bin/java 2000
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/oracle_jdk8/bin/javac 2000
sudo update-alternatives --config java
sudo update-alternatives --config javac
```
Create a file /etc/profile.d/oraclejdk.sh, replace the contents from the file in this repository and set the paths by running
```
source /etc/profile.d/oraclejdk.sh
```

### Manually installing maven in the container
Create a folder /maven in container you just created
```
mkdir /maven
```
On base machine download apache maven binary (.tar.gz file) from Apache Maven official site (https://maven.apache.org/download.cgi)
Copy the downloaded file from base machine to the docker container. From the directory where file is downloaded run:
```
sudo tar -cv apache-maven-3.3.9-bin.tar.gz | sudo docker exec -i javaimg tar x -C /maven
```
Inside container, go to /maven and extract the file
```
tar -xvzf apache-maven-3.3.9-bin.tar.gz
```
Move the extracted contents to /usr/lib/maven folder
```
sudo mv /maven/apache-maven-3.3.9/ /usr/lib/maven
```
Set the maven path
```
export PATH=/usr/lib/maven/bin:$PATH
```
Verify by checking maven version
```
mvn -v
```

### Commit the changes and Push the image
Exit from the container and commit the changes in a new image
```
docker commit -m "maven and java added" -a "{author name}" {container_id} {new_image_name}:{tag}
eg
docker commit -m "maven and java added" -a "Narender Kumar" e3f03f2f779d mavenimg:1.0

```
You can push the image in docker hub now using below command
```
sudo docker push {your_dockerhub_account_name}/{new_image_name}:{tag}
```
