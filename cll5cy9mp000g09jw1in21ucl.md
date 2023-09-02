---
title: "Docker: Introduction step-by-step guide for beginners DevOps Engineers."
datePublished: Thu Aug 10 2023 16:15:53 GMT+0000 (Coordinated Universal Time)
cuid: cll5cy9mp000g09jw1in21ucl
slug: docker-introduction-step-by-step-guide-for-beginners-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691684033575/1acafb53-44a2-4fc5-bee5-95de67991c08.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691683947218/b1653456-2db4-41b5-b101-50ea2c152ec1.png
tags: docker, devops, docker-compose, docker-images, devops-journey

---

### **What is a Docker?**

Docker is a popular open-source project written in Go and developed by Dot Cloud (A PaaS Company). It is a container engine that uses Linux Kernel features like namespaces and control groups to create containers on top of an operating system.

* Docker is a Container management service. Is an Open Platform for developing, shipping & Running applications.
    
* You can separate your applications from your infrastructure and treat your infrastructure like a managed application.
    
* Docker combines kernel containerization features with workflow & tooling that helps you manage & deploy your application.
    

![](https://miro.medium.com/v2/resize:fit:847/1*OSHwUFigCT0EQvhWKWvprg.png align="left")

fig:-Docker architectural workflow

## **Why Use Docker?**

With Docker, you can:

🔧 **Build Once, Run Anywhere:** Docker containers ensure your application behaves the same way in every environment, from your laptop to production servers.

🏭 **Faster Deployment:** Say goodbye to time-consuming setup processes. Docker's lightweight containers launch in a snap!

🚀 **Scalability:** With Docker, scaling your applications becomes as simple as hoisting the sails. 🎉

### **Docker Architecture:-**

![](https://miro.medium.com/v2/resize:fit:847/1*G_7X2dkXHbVEnH0ITd5B-w.png align="left")

fig:- Docker architecture

* Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers.
    
* The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon.
    
* The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface.
    
* Another Docker client is Docker Compose, which lets you work with applications consisting of a set of containers.
    
    ## **Key Features of Docker**
    
    * **Containerization and Isolation:**
        
        Docker allows you to create isolated environments called containers, ensuring that applications and their dependencies are encapsulated, reducing conflicts and promoting consistency.
        
    * **Portability:**
        
        Containers built with Docker are highly portable, meaning you can run them on any platform that supports Docker, from local development machines to cloud servers.
        
    * **Version Control:**
        
        Docker makes it easy to version and share containers, enabling collaboration between developers and streamlining the continuous integration and deployment (CI/CD) pipeline.
        
    * **Efficiency and Performance:**
        
        With its lightweight architecture, Docker minimizes the overhead of virtualization, resulting in faster application start times and better resource utilization.
        
    * **Scalability:**
        
        Docker's design allows for effortless scaling of applications, both horizontally and vertically, to handle changing workloads and demand spikes.
        
    * **Integration and Ecosystem:**
        
        Docker integrates seamlessly with various tools and platforms, making it an essential part of the DevOps ecosystem.
        

## **What is a Container?**

![](https://miro.medium.com/v2/resize:fit:726/1*C0f49NLHQum2hVsqJ7TFOg.png align="left")

### Docker Container

* In the above image, two applications are running on the same machine. These applications are run in a container and any changes made on this container do not affect the other container. Each of them can have a different Operating System running on the same physical machine.
    
* Containers are instances of Docker images that can be run using the Docker run command.
    
* The basic purpose of Docker is to run containers.
    
* You can create, start, stop, move, or delete a container using the Docker API or CLI. You can connect a container to one or more networks, attach storage to it, or even create a new image based on its current state.
    

> *A Docker container is an isolated, Secured shipping box produced or created when the docker image is run.*
> 
> *A container packages up the code and all its dependencies so the application runs quickly and reliably from one computing environment to another.*

# **What is a Docker Image**

A Docker Image is a read-only file with a bunch of instructions. When these instructions are executed, it creates a Docker container.

> *Docker Image is a read-only template, composed of the layered file system, needed to build a running docker container, basically the running instance of the image.*

# **What is a Dockerfile**

Dockerfile is a simple text file that consists of instructions to build Docker images.

# **Why should you use docker?**

Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package.

![](https://miro.medium.com/v2/resize:fit:847/1*V8qi9LJv0w4gQ1xQ64SlcA.png align="left")

* Previously for developing purposes, we are using monolithic Architecture, but nowadays we are using microservices architecture, monolithic architecture is built as one large system and usually on a code base.
    
* To overcome this we used Docker. built as a small independent module based on business functionality.
    

# **Before –**

* Monolithic application
    
* Long development cycles
    
* Single environment
    
* Slowly scaling up
    

# **Now -**

* Decoupled services
    
* Fast and iterative improvement
    
* Multiple environments
    
* Quickly scaling out.
    

## **Installing Docker**

Note: *Since we are using the Amazon Linux machine.*

```dockerfile
$ sudo yum install docker
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
amzn2-core                                               | 3.7 kB     00:00
Package docker-20.10.17-1.amzn2.0.1.x86_64 already installed and the latest version
10:30
$ docker -v
Docker version 20.10.17, build 100c701
```

```dockerfile
$ docker login
Authenticating with existing credentials...
WARNING! Your password will be stored unencrypted in /root/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
```

## **Some Docker Basic Commands**

1. Docker -v
    

Used to get the exact installed version of docker.

```dockerfile
$ docker -v
Docker version 20.10.12, build e91ed57
```

2\. docker pull

Used to pull images from the docker repository

```dockerfile
$ docker pull centos
Using default tag: latest
latest: Pulling from library/centos
a1d0c7532777: Pull complete
Digest: sha256:a27fd8080b517143cbbbab9dfb7c8571c40d67d534bbdee55bd6c473f432b177
Status: Downloaded newer image for centos:latest
docker.io/library/centos:latest
```

3\. docker images

Lists all the locally stored docker images.

```dockerfile
$ docker images 
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
centos       latest    5d0da3dc9764   14 months ago   231MB
```

4\. docker ps

```dockerfile
$ docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
e4c6c5bafc59 centos:7 “/bin/bash” 9 months ago Up 44 minutes nikhil
```

5\. docker exec -itd &lt;container id&gt;

Used to access the running container.

```dockerfile
$  docker exec -itd centos basha
[root@726b8691b8c5 /]# ls -lrth
total 0
drwxr-xr-x   2 root root   6 Nov  3  2020 srv
lrwxrwxrwx   1 root root   8 Nov  3  2020 sbin -> usr/sbin
drwxr-xr-x   2 root root   6 Nov  3  2020 opt
drwxr-xr-x   2 root root   6 Nov  3  2020 mnt
drwxr-xr-x   2 root root   6 Nov  3  2020 media
lrwxrwxrwx   1 root root   9 Nov  3  2020 lib64 -> usr/lib64
lrwxrwxrwx   1 root root   7 Nov  3  2020 lib -> usr/lib
drwxr-xr-x   2 root root   6 Nov  3  2020 home
lrwxrwxrwx   1 root root   7 Nov  3  2020 bin -> usr/bin
drwx------   2 root root   6 Sep 15  2021 lost+found
drwxr-xr-x  12 root root 144 Sep 15  2021 usr
drwxr-xr-x  20 root root 262 Sep 15  2021 var
drwxrwxrwt   7 root root 171 Sep 15  2021 tmp
drwxr-xr-x  11 root root 163 Sep 15  2021 run
dr-xr-x---   2 root root 162 Sep 15  2021 root
drwxr-xr-x   1 root root  66 Nov 26 17:08 etc
dr-xr-xr-x  13 root root   0 Nov 26 17:08 sys
dr-xr-xr-x 171 root root   0 Nov 26 17:08 proc
drwxr-xr-x   5 root root 360 Nov
```

6\. docker stop &lt;container id&gt;

To stop the running container use the below CLI command.

```dockerfile
>docker ps
CONTAINER ID   IMAGE      COMMAND       CREATED        STATUS             PORTS     NAMES
e4c6c5bafc59   centos:7   "/bin/bash"   9 months ago   Up About an hour             shubham
>docker stop e4c6c5bafc59
e4c6c5bafc59
```

7\. docker kill &lt;container id&gt;

To kill the container use the below CLI command.

```plaintext
>docker ps
CONTAINER ID   IMAGE     COMMAND       CREATED              STATUS              PORTS     NAMES
3bbe86726870   centos    "/bin/bash"   21 seconds ago       Up 18 seconds                 
50ff3fd19ff0   centos    "/bin/bash"   About a minute ago   Up About a minute            

>docker kill 3bbe86726870
3bbe86726870s

>docker ps
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS         PORTS     NAMES
50ff3fd19ff0   centos    "/bin/bash"   3 minutes ago   Up 3 minutes
```

8\. docker rmi &lt;image-id&gt;

To remove the docker image use the below command.

```plaintext
>docker rmi f2ad9f23df82
Untagged: mysql:latest
Untagged: mysql@sha256:fc77d54cacef90ad3d75964837fad0f2a9a368b69e7d799665a3f4e90e600c2d
Deleted: sha256:f2ad9f23df82a3e5efabd1574b862a94c0657c73a6179efec07d5cf9ae5a307f
```

## **Creating a first Dockerfile**

```dockerfile
docker]# cat dockerfile
FROM ubuntu
MAINTAINER xyx@gmaxx.com
RUN apt-get update
CMD ["echo","hello world..! from my first docker image"]
```

## **Build the docker image**

```dockerfile
docker]# docker build -t myimage:1.0 .
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
 docker]# systemctl unmask docker.service
 docker]# systemctl unmask docker.socket
 docker]# systemctl start docker.service
```

```dockerfile
 docker]# docker build -t myimage:1.0 .
Sending build context to Docker daemon  14.85kB
Step 1/4 : FROM ubuntu
latest: Pulling from library/ubuntu
e96e057aae67: Pull complete
Digest: sha256:4b1d0c4a2d2aaf63b37111f34eb9fa89fa1bf53dd6e4ca954d47caebca4005c2
Status: Downloaded newer image for ubuntu:latest
 ---> a8780b506fa4
Step 2/4 : MAINTAINER xyx@gmaxx.com
 ---> Running in 7507411dbda9
Removing intermediate container 7507411dbda9
 ---> 1dc383421bfa
Step 3/4 : RUN apt-get update
 ---> Running in 99066139b234
Get:1 http://archive.ubuntu.com/ubuntu jammy InRelease [270 kB]
Get:2 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [114 kB]
Get:4 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [99.8 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 Packages [1792 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy/restricted amd64 Packages [164 kB]
Get:7 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [266 kB]
Get:8 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [17.5 MB]
Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [8056 B]
Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [956 kB]
Get:11 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [579 kB]
Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [924 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [3175 B]
Get:14 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [7275 B]
Get:15 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [775 kB]
Get:16 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [522 kB]
Get:17 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [618 kB]
Get:18 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [4642 B]
Fetched 24.7 MB in 2s (12.0 MB/s)
Reading package lists...
Removing intermediate container 99066139b234
 ---> 791615a3c734
Step 4/4 : CMD ["echo","hello world..! from my first docker image"]
 ---> Running in 0f453aa4bd35
Removing intermediate container 0f453aa4bd35
 ---> f10eb158c223
Successfully built f10eb158c223
Successfully tagged myimage:1.0
```

```dockerfile
docker]# docker images
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
myimage      1.0       f10eb158c223   7 minutes ago   118MB
ubuntu       latest    a8780b506fa4   3 weeks ago     77.8MB

docker]# docker run f10eb158c223
hello world..! from my first docker image
```

## **Automate Jenkins setup with Docker**

1. Use the CLI command listed below to pull the Jenkins image.
    

```dockerfile
docker]# docker pull jenkins:2.60.3
2.60.3: Pulling from library/jenkins
55cbf04beb70: Pull complete
1607093a898c: Pull complete
9a8ea045c926: Pull complete
d4eee24d4dac: Pull complete
c58988e753d7: Pull complete
794a04897db9: Pull complete
70fcfa476f73: Pull complete
0539c80a02be: Pull complete
54fefc6dcf80: Pull complete
911bc90e47a8: Pull complete
38430d93efed: Pull complete
7e46ccda148a: Pull complete
c0cbcb5ac747: Pull complete
35ade7a86a8e: Pull complete
aa433a6a56b1: Pull complete
841c1dd38d62: Pull complete
b865dcb08714: Pull complete
5a3779030005: Pull complete
12b47c68955c: Pull complete
1322ea3e7bfd: Pull complete
Digest: sha256:eeb4850eb65f2d92500e421b430ed1ec58a7ac909e91f518926e02473904f668
Status: Downloaded newer image for jenkins:2.60.3
docker.io/library/jenkins:2.60.3
```

Now run the Jenkins Image assigning the port via -p Internal port as well as External port and also the volume path /jenkins\_home with -v flag.

```dockerfile
[root@ip-172-31-24-227 docker]# docker run --name myjenkins -p 8080:8080 -p 50000:50000 -v :/var/jenkins_home jenkins:2.60.3
Running from: /usr/share/jenkins/jenkins.war
webroot: EnvVars.masterEnvVars.get("JENKINS_HOME")
Nov 28, 2022 12:00:29 PM Main deleteWinstoneTempContents
WARNING: Failed to delete the temporary Winstone file /tmp/winstone/jenkins.war
Nov 28, 2022 12:00:29 PM org.eclipse.jetty.util.log.JavaUtilLog info
INFO: Logging initialized @662ms
```

Open a web browser and start browsing on localhost using port 8080.

![](https://miro.medium.com/v2/resize:fit:847/1*u0y5Yt2G5pgiVyZwZarprw.png align="left")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">references : <a target="_blank" rel="noopener noreferrer nofollow" href="https://docs.docker.com/get-started/overview/" style="pointer-events: none">https://docs.docker.com/get-started/overview/</a></div>
</div>