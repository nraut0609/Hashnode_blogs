---
title: "Docker Commands Cheat Sheet- in detail with example"
datePublished: Fri Aug 18 2023 10:44:58 GMT+0000 (Coordinated Universal Time)
cuid: cllggro1z000509ktf0wn7a7i
slug: docker-commands-cheat-sheet-in-detail-with-example
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692355323584/9678f953-1438-4383-8134-cc3df75f506e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692355484458/b4dde682-b412-44c7-8332-9f46b48ee578.png
tags: docker, devops, dockerfile, docker-compose, docker-images

---

## **Docker Container Commands**

### **List all the Running Containers**

```dockerfile
docker ps
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps.png align="left")

We can also use `docker container ps` or `docker container ls` to list all the running containers.

There is no difference between `docker ps` and `docker container ps` commands with respect to the result of their execution.

`docker ps` is an old syntax and is supported for backward compatibility.

The `docker container ls` command is an appropriate version of the command compared to `ps` as `ls` is a shortcut for `list`.

### **List all the Containers (irrespective of the state)**

```bash
docker ps -a
```

Please note: `-a` is the short form for `--all` and they both can be used interchangeably.

```bash
docker ps -all
```

This command is used for listing all the containers (active and inactive).

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-all.png align="left")

As can be seen from the screenshot above, the container `objective_margulis` is not running while the container `sharp_cori` is up since the last hour.

### **List all the Running Containers with the File Size**

```bash
docker ps -s
```

```bash
docker container ls -s
```

`-s` is the short form `--size`

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-s.png align="left")

This command adds `SIZE` column to the output.

As it can be seen from the screenshot above, `1.09kB` is the disk space used by the container (writable layer). In simple words, the value in the `SIZE` column represents the size of the data that is written by the container in its writable layer.

This text `virtual 133MB` represents the amount of disk space used by the image of this container.

### **List the IDs of the Running Containers**

```bash
docker ps -q
```

```bash
docker container ls -q
```

`-q` is the short form for `--quiet`. This command modifies the `docker ps` output and displays only the Ids of the running containers.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-q.png align="left")

### **List the IDs of all the Containers (irrespective of the state)**

```bash
docker ps -a -q
```

We can also write the above command by combining `a` and `q` as:

```bash
docker ps -aq
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-a-q.png align="left")

### **Filter container list**

We can filter the output of `docker ps` or `docker ps -a` commands using the `--filter` option as:

```bash
docker ps -f name=un
```

`-f` is the short form for `--filter`

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-f-name.png align="left")

In the above screenshot, the command filters the containers and only displays the ones whose name starts with `un`

Similarly, we can add `-f` option with the `docker ps -a` command:

```bash
docker ps -a -f name=ar
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-a-f-name.png align="left")

We can also filter the containers on the basis of the status as:

```bash
docker ps -a -f status=running
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-a-f-status.png align="left")

As seen in the above screenshot, the filter command filters the containers and displays only the running ones in the list!

You can check the other filter options available from the [official Docker documentation](https://docs.docker.com/engine/reference/commandline/ps/#filtering)

### **Creating a new Container using Docker Image**

```bash
docker create <image_name>
```

The `docker create` command is used to create a new container using a Docker image. It does not run the container but just adds a writable layer on top of the Docker image. We'll have to run the `docker start` command to run the created container.

As `docker create` command interacts with the `container`object, we can also use the below command:

```bash
docker container create <image_name>
```

Let's create a container using an `nginx` Docker image:

```bash
docker create nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-create-nginx.png align="left")

Perfect! The container is created. Let's verify that using the `docker ps` command:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-create.png align="left")

The status of the container is `Created` as expected!

Please note the name of the `nginx` container `trusting_bouman` is some random string and would be different on your system.

We can also create a Docker container with some fixed names. Let's do that right away!

### **Creating a new Container using Docker Image with some fixed name**

```bash
docker create --name <container_name> <image_name>
```

```bash
docker container create --name <container_name> <image_name>
```

Let's create a container named `nginx-container` using `nginx` image:

```bash
docker create --name nginx-container nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-create-name-nginx.png align="left")

Neat! The container `nginx-container` is created!

### **Start a Docker Container**

We can run an already created command using the below command:

```bash
docker start <container_id or container_name>
```

OR

```bash
docker container start <container_id or container_name>
```

We can use the `docker start` command either using the container ID or name.

Let's start the `nginx-container`:

```bash
docker start nginx-container
```

We can also start it as:

```bash
docker start df1c49ee5275
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-start-nginx-container.png align="left")

As seen from the above screenshot, `nginx-container` is created and the `docker ps` command is used to verify the status of the container.

### **Stop a running Docker Container**

```bash
docker stop <container_id or container_name>
```

OR

```bash
docker container <container_id or container_name>
```

Here's the command for stopping the `nginx-container`:

```bash
docker stop nginx-container
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-stop-nginx-container.png align="left")

As seen in the above screenshot, the container `nginx-container` is exited 17 seconds ago. This container won't be listed in the `docker ps` command.

### **Restart a Docker container**

```bash
docker restart <container_id or container_name>
```

OR

```bash
docker container restart <container_id or container_name>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-restart-nginx-container.png align="left")

The `nginx-container` is now restarted and is up for the last 8 seconds.

### **Pause a running Container**

```bash
docker pause <container_id or container_name>
```

OR

```bash
docker container pause <container_id or container_name>
```

Let's try to pause the `nginx-container`:

```bash
docker pause nginx-container
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-pause-nginx-container.png align="left")

### **Unpause a paused Container**

To again run the paused container, we can use the below command:

```bash
docker unpause <container_id or container_name>
```

```bash
docker container unpause <container_id or container_name>
```

To unpause the `nginx-container`, we can use the below command

```bash
docker unpause nginx-container
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-unpause-ngxinx-container.png align="left")

### **Docker Run command**

As implied from the name, this command is used to run the container!

It is a combination of the `create` and the `start` commands. This command creates the container and starts it in one go!

The `docker create` or `docker container create` command creates the container and to run the container, we have to use the `docker start` command.

It rarely happens that we will create the container and run it later. Generally, in real-world cases, we would create and run the container in one go using the `docker run` command.

Here's how we can run a Docker container:

```bash
docker run <image_name>
```

```bash
docker container run <image_name>
```

If the Docker image is locally available, Docker will run the container using that image otherwise it would download the image from the [remote repository](https://hub.docker.com/).

#### **Docker Run command in Foreground and Detached Modes**

The Docker container can run in two modes:

1. Foreground mode
    
2. Background or detached mode
    

Docker runs the container in the foreground mode by default. In this mode, Docker starts the root process in the container in the foreground and attaches the standard *input(stdin)*, *output(stdout)*, and *error(stderr)* of the process to the terminal session.

In the foreground mode, you cannot execute any other command on the terminal session until the container is running. This is the same as running a Linux process in the foreground mode.

Let's create and run a container in the foreground mode using the `nginx` Docker image:

```bash
docker container run nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-container-run-nginx.png align="left")

The above screenshot shows the output of the Nginx container on the terminal. The Nginx process is running in the foreground and hence this terminal session cannot be used for executing other commands or performing any other operation.

If you end the terminal session by closing the terminal tab or by using the exit command, the container will die automatically and the Nginx process would stop running.

Please open a new terminal tab to verify if the container is running:

```bash
docker ps
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-run.png align="left")

The `run` command worked as expected - it created the container and also started the container.

The long-running processes such as `Nginx` are run in the background mode and so are not dependent on the terminal session.

If we end the terminal session by closing the terminal tab or by pressing `CTRL + C`, the container will die automatically.

Let's stop the `nginx` process using `CTRL+C`!

Now if you execute the `docker ps` command, you can see that the container is in *exited* stated but it is not deleted. This is because when the container exits or when we stop the container, the filesystem of the container continues to persist on the host machine.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-run-a.png align="left")

#### **Delete the container on the exited state**

If you want to also delete the container after it is exited, you can start the container in the foreground using this command:

```bash
docker run --rm nginx
```

This command would start the `nginx` container in the foreground mode. If you kill the terminal session, it would stop the container and delete it!

`--rm` option removes the filesystem of the container once it is stopped or when the container exits automatically.

### **Run the container in daemon mode**

To run the container in the background or in daemon mode, we can use the `-d`(`--detach`) option.

```bash
docker run -d <image_name>
```

`-d` option will run the container in the background mode and print the container ID

Let's run a container with `nginx` image in the background mode:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-run-d-nginx.png align="left")

From the above image, we can see that the container process is not attached to the terminal session and the container is running in the background mode.

Let's verify if the container is in the running state using the `docker ps` command:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-ps-run-d.png align="left")

### **Run Docker Container with a name using the run command**

We can use `--name` option to assign a name to the container as shown below:

```bash
docker container run -d --name <container_name> <image_name>
```

Let's create a container named `nginx-container` from `nginx` image:

```bash
docker container run -d --name nginx-container nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-container-run-d-name.png align="left")

### **Listing Processes running in a Docker Container**

```bash
docker top <container_name or container_id>
```

OR

```bash
docker container top <container_name or container_id>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-top.png align="left")

Here, we can see that inside `nginx-container` there are two processes running with the Ids `4685` and `4747`.

### **Map ports of a Docker Container**

Docker exposes the same port on the host machine that is exposed by the container.

We know that `nginx` process listens on port 80. Hence, a container running an `nginx` process will expose port 80 on the container.

Docker will map port 80 of the `nginx` container with port 80 of the host machine. The `nginx` container will be accessible to the outside world from port 80 of the host machine.

> We know that one port cannot be used by multiple processes.

*But what if we want to run multiple* `nginx` containers on the same host machine?

We can use port mappings provided by Docker to achieve this!

The port mappings allow us to map a port on the container with a different port on the host machine.

We can map the ports of the container while creating the container as shown below:

```bash
docker container run --name <container_name? -d -p <host_post>:<container_port> <image_name>
```

To expose `nginx` container (port 80) on port `8080` of the host machine, we can use the below command:

```bash
docker container run --name nginx-container -d -p 8080:80 nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-run-with-name-map.png align="left")

The port mappings are also indicated in the `docker ps` command as shown in the above screenshot!

As the container is mapped to the port `8080` of the host machine, we can access the Nginx container on `8080` using the curl command. Let's try that out!

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/nginx-output.png align="left")

This works as expected!

### **Rename a Docker Container**

```bash
docker rename <old_name> <new_name>
```

OR

```bash
docker container rename <old_name> <new_name>
```

Let's rename `nginx-container` to `nginx-cont`:

```bash
docker rename nginx-container nginx-cont
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-rename.png align="left")

### **Run the Docker Container in an Interactive Mode**

When we run the container in an interactive mode, Docker will attach the stdin(standard input) of the container to the terminal.

This will give us entry inside the container and now we can run any command inside the container.

Let's understand this with an example:

```bash
docker container run -it <image_name> /bin/bash
```

This command simply means that we want to start the bash shell inside the container.

Let's create a container from an Nginx image and run the bash command inside the container:

```bash
docker container run -it nginx /bin/bash
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-container-run-bin-bash.png align="left")

*Super! We're inside the container!*

We can now execute any command inside the container.

Please open another tab and let's list down the processes running inside the container:

```bash
docker top wonderful_visvesvaraya
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-container-name-top.png align="left")

As seen in the above screenshot, only one process is running inside the nginx container. This is the same process that we have opened in `Tab 1`.

When we had checked the processes running inside the `nginx-container` earlier, we saw two processes (nginx master and worker) inside the nginx container but now there is just one process - *bash shell*.

This is because we passed `/bin/bash` command to the `docker run` command. This command overrides the dockerfile `CMD` or `Entrypoint` commands and so the Nginx processes were not started inside the Nginx container.

### **Get Inside the Running Container (Literally!)**

If you have a container that is already running and you want to go inside that container, here's a command that will take you to the container world:

```bash
docker exec -it <contaner_id or container_name> /bin/bash
```

Let's start the nginx container in the daemon mode:

```bash
docker run -d --name nginx-container nginx
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-exec-ps.png align="left")

We can go inside this container as:

```bash
docker exec -it nginx-container  /bin/bash
```

The `docker exec` command executes the `/bin/bash` command and starts a bash shell session inside the container as shown in the below screenshot:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-exec.png align="left")

Sweet! This is quite a handy command and is used more often to get into the running container and perform some operations.

Note: Apart from `/bin/bash`, we can pass any command that we want to execute inside the container. Here's a quick example:

```bash
docker exec -it nginx-container echo "Hello, from container"
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-exec-command.png align="left")

### **Start a Docker Container and keep it running**

The life of a container depends on the root process inside the container. So far we have run `nginx` process inside the containers.

`nginx` is a long and continuous running process and hence the Nginx container continues to run and does not die!

*If we run a process that is short-lived inside the container, it will die once that process dies!*

For example, if we run a container using the `centos` Docker image, it will die as soon as the process inside the `centos` dies.

`centos` has a default command `bash`. The `bash` command runs and dies immediately.

Hence, the `centos` container also dies immediately as shown below:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-run-d-centos.png align="left")

To continue running the container that has a short-lived process, we can use the below command:

```bash
docker run -dt <image_name>
```

`-d` will run the ubuntu container in the background and `-t` option allocates a "pseudo-tty"

To continuously run the container created from `centos` image, we can use the below command:

```bash
docker run -dt centos
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-run-dt-centos.png align="left")

### **Copy a File from a Container to a Host**

The Docker container and the host file systems are isolated from each other. We cannot use the normal `cp` or copy command to copy content from the container to the host and vice-versa.

To copy content from the container to the host machine, we can use the below command:

```bash
docker cp <container_id or container_name>:<source_file_path> <destination_path>
```

Let's understand this with the help of an example:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-copy-container-to-host.png align="left")

As seen in the above screenshot, we have created a file `file_insider_container.txt` inside the `centos-container`.

Let's copy this file from the container to the host machine:

```bash
docker cp centos-container:file_insider_container.txt .
```

The `.` in the above command signifies that the destination path is the current location on the host machine.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-copy-container-to-host-example.png align="left")

We can see that `file_inside_container.txt` has been copied on the current directory of the host machine.

### **Copy a File from the Host to the Docker Container**

We can copy a file from the host system to the Docker container as:

```bash
docker cp <location_of_file_on_host> <container_id or container_name>:<file_desinaion>
```

Let's create a file `file_on_host.txt` on the machine and copy it inside the container.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-copy-host-to-container.png align="left")

As seen in the above screenshot, we have created a file `file_on_host.txt` on the host machine.

Let's copy this file inside the `centos-container` using the below command:

```bash
docker cp file_on_host.txt centos-container:/
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-copy-host-to-container-example.png align="left")

The file `file_on_host.txt` has been copied inside the `centos-container` container.

### **Remove a specific Docker Container**

To remove a Docker container, you first have to stop the running container and then delete it:

```bash
docker stop <container_name or container_id>
```

OR

```bash
docker container stop <container_name or container_id>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-remove-stop.png align="left")

Once the container stops, you can remove it using the below command:

```bash
docker rm <container_name or container_id>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-rm-container.png align="left")

If you want to directly remove the container without stopping it, you can use the below command:

```bash
docker rm -f <container_name or container_id>
```

`-f` is for forcefully removing the running container

### **Remove a Docker Container after it exits**

```bash
docker run --rm <image_name>
```

This will create and run a container that will be deleted automatically once the container stops.

### **Delete all the Stopped Containers**

To delete all the stopped containers, we can use the below command:

```bash
docker container prune
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-prune.png align="left")

### **Delete all the Docker Containers**

This command is used to delete all the running as well as the stopped containers:

```bash
docker rm -f $(docker ps -a -q)
```

```bash
docker container rm -f $(docker ps -a -q)
```

We know that `docker ps -a -q` will list all (running as well as not running) container Ids. Once we get the Ids using the `rm` option, we can then remove all the containers.

### **Create a Docker image from a Docker Container**

```bash
docker container commit <container_id or container_name> <new_image_name>
```

OR

```bash
docker commit <container_id or container_name> <new_image_name>
```

Consider the example below:

We'll create a file `file_inside_container.txt` inside the running container `centos-container`:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-commit.png align="left")

Let's now create an image `(centos-with-new-file)` from `centos-container` using the below command:

```bash
docker container commit centos-container centos-with-new-file
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-commit-with-new-file.png align="left")

As shown in the above image, we created a new image `centos-with-new-file` and using this image, we created a new container `centos-with-new-file-container`.

As `centos-with-new-file` image was created from `centos-container` that had a file `file_inside_container.txt`, the containers created from `centos-with-new-file` image would also have `file_inside_container.txt`.

### **Run command inside the Docker Container**

We have already seen that we can directly go inside the container using the `docker exec` command.

Let's see how we can execute commands inside the container without actually going inside the container.

To run any command inside the container, we can use the `docker exec` command as shown below:

```bash
docker exec -it <container_id or container_name> <command>
```

For example, to get the list of processes running inside the `centos` image, we can use the below command:

```bash
docker exec -it f40cc2e51d5b ps -afe
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/exec-ps-afe.png align="left")

### **Set Environment Variable in a Docker Container**

We can set environment variables inside the container environment using the below command:

```bash
docker run --env ENV_VAR1=value1 --env ENV_VAR1=value2 --name <container_name> <image_name>
```

To create an environment variable with the name `NAME` and value `Buddy` inside the centos image, we can use the below command:

```bash
docker run -dt --env NAME=Buddy --name centos-container centos
```

`-dt` is added to run the `centos-container` in daemon mode and to prevent it from dying immediately.

To check if the environment variable has been set inside the container, we can use the below commands:

```bash
docker exec -it centos-container printenv
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-container-printenv.png align="left")

The `docker exec` command executes `printenv` (to print environment variable) inside the `centos-container` container and prints the output on the terminal.

### **Set Environment Variable in a Docker Container using a File**

We can also set environment variables inside the container using a file.

The file `file1.txt` consists of key-value pairs as shown below:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/env-file1.png align="left")

To create environment variables from a file we can use the below command:

```bash
docker run --env-file <path_to_the_file> --name <container_name> <image_name>
```

The `--env-file` flag takes a filename as an argument. Each line in the file should be in the format `VAR=VAL`.

Let's create environment variables inside the `centos-container-1` container using the file `file1.txt`:

```bash
docker run -dt --env-file file1.txt --name centos-container-1 centos
```

`-dt` is added to run the `centos-container` in daemon mode and to prevent it from dying.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/env-docker-container-from-file.png align="left")

## **Docker Image Commands**

In this section, we will look at the Docker image commands.

### **List all the Docker Images**

Here's a command to list all the images that are locally stored:

```bash
docker images
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-images.png align="left")

### **List the Docker Image Ids**

```bash
docker images -q
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-images-q.png align="left")

### **List all the Docker Images (including dangling images)**

```bash
docker images -a
```

`-a` stands for `all`

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-images-a.png align="left")

### **Build a Docker Image**

We can build a Docker image from a Dockerfile using the below command:

```bash
docker build -t <image_name> <context_dir>
```

Docker will try to find a file named `Dockerfile` inside the `context_dir` and it would then create a Docker image using the `Dockerfile` file.

Let's create a `Dockerfile` as shown below in the current directory:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-build-t.png align="left")

We can now build a Docker image `centos` from this `Dockerfile` using the below command:

```bash
docker build . -t centos_buddy
```

Here, dot (`.`) indicates that the context directory is the current directory.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-build-t-dot.png align="left")

Let's verify if the image has been created:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-build-images.png align="left")

### **Build Docker Images with a different tag**

```bash
docker build . -t <image_name>:<tag or version>
```

The above command will build an image with `imagename` and tag `1.8`.

Here's an example:

```bash
docker build . -t centos_buddy:1.8
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-build-t-version.png align="left")

### **Build a Docker Image using a custom named Dockerfile**

We can build a Docker image from a `Dockerfile` which is not named `Dockerfile` using the below command:

```dockerfile
docker build -f <custom_docker_file_name> -t <image_name> .
```

Let's create a `Dockerfile` with name `custom_docker_file`:

```bash
docker build -f custom_docker_file -t centos_custom .
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-build-custom-dockerfile.png align="left")

### **Build a Docker Image from a Dockerfile that is not in the Current Directory**

```bash
docker build -f </path/to/dockerfilename>  -t <image_name> .
```

### **Show History of a Docker Image**

```bash
docker history <imagename or imageid>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-history.png align="left")

The above screenshot shows the history for the image `centos_buddy`.

### **Rename an existing Docker Image**

```bash
docker tag <imagename> <newname>:<version>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-iamge-rename.png align="left")

### **Remove Docker images**

```bash
docker rmi <image_name or image_id>
```

This command will delete the Docker image if the image is not used by any container.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-rmi.png align="left")

### **Force delete a Docker Image**

```bash
docker rmi -f <image_name or image_id>
```

### **Unused Docker Images**

Unused Docker images are not used by any containers.

The images that are displayed when we do `docker ps -a` are used by some of the existing containers.

So, the unused images are:

> (All images from `docker images -a`) - (all images from `docker ps -a`)

### **Dangling Docker Images**

When we build a Docker image using Dockerfile, Docker creates an image with the given name.

Here's a simple example:

```bash
docker build . -t imagename
```

Docker will create an image from the Dockerfile in the current directory with the name `imagename`.

If we do some changes in the Dockerfile and rebuild the image again with the same name, Docker will update the name of the previous image to `<none>` and tag it `<none>`.

These images with the name `<none>` and tag `<none>` are called dangling images.

### **List Dangling Docker Images**

```bash
docker images -f dangling=true
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-images-f.png align="left")

### **Remove all the Dangling Docker Images**

```bash
docker image prune
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-remove-all-dangling-images.png align="left")

If the dangling images are referenced by containers (either running or not running), Docker will not prune these dangling images.

To remove dangling images, we've to make sure that they are not referenced by any container.

We can first run `docker container prune` to remove all the stopped containers and the `docker images` command will now remove the dangling images that were referenced by these stopped containers.

We can also use the below command to remove the dangling images:

```bash
docker rmi $(docker images -f dangling=true -q)
```

`docker images -f dangling=true -q` would return the Ids of all the dangling images.

### **Remove all the Dangling and Unused Docker Images**

```bash
docker image prune -a
```

### **Login to Docker**

To login to Docker hub, we can use the below command:

```bash
docker login
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-login.png align="left")

You can enter your username and password to log in to Docker hub.

### **Push a Docker Image to the Docker Registry**

Once we are logged in to Docker hub, we can push the Docker images to the registry using the below command:

```bash
docker push repository_name/imagename:tag
```

### **Download a Docker Image from the registry**

```bash
docker pull imagename:tag
```

If the image is not present on the host machine, Docker will pull the image from the Docker registry.

If no tag is specified, Docker will pull the latest image.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-pull-nginx.png align="left")

## **Docker logs**

Let's now look at some commands useful for checking logs in a Docker container:

### **Get Logs of the Docker container**

We can get the logs of the Docker container as:

```bash
docker container logs <container_id or container_name>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-log.png align="left")

The above screenshot shows the logs of the container `nginx-container`.

### **Monitor the Docker Container Logs**

To display the last few lines of the container logs and monitor them, we can use the below command:

```bash
docker container logs -f <container_id or container_name>
```

The new messages in the container would be displayed here! This is similar to the `tail -f` command.

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-logs-f.png align="left")

### **Get the last 2 lines of the Container Logs**

```bash
docker container logs --tail 2 <container_id or container_name>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-logs-last-two-lines.png align="left")

## **Docker Network Commands**

Here are some of the useful Docker Network commands:

### **List all the Networks**

```bash
docker network ls
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-network-ls.png align="left")

### **Create a Network**

```bash
docker network create --driver <driver-name> <bridge-name>
```

`driver-name` can be either `bridge` or `overlay`

`bridge` would be used by default if `--driver` option is not provided.

```bash
docker network create --driver bridge new-network
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-network-create.png align="left")

The network called `new-network` is created successfully!

### **Connect a Docker Container to a Network:**

```bash
docker network connect <network_id or network_name> <container_id or container_name>
```

The above command will connect the container with the specified network. Let's look at an example:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-network-connect.png align="left")

The container `nginx-container` is connected to the network `new-network` and we can verify this using `docker network inspect`:

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-network-inspect.png align="left")

### **Connect a Docker Container to a Network on Start**

This command connects a Docker container to a network as soon as it starts:

```bash
docker run -d --network=<network_name or id> <contaienr_name>
```

### **Disconnect a Docker container from a Network:**

```bash
docker network disconnect <network_name_or_id> <container_name_or_id>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-network-disconnect.png align="left")

### **Remove a Network**

```bash
docker network rm <network_id or network_name>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/network-rm.png align="left")

### **Show Information about one or more Networks**

```bash
docker network inspect <network_id or network_name>
```

### **Get the IP Address of the running Docker Container**

```bash
sudo docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container_name or container_id>
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/container-ip-address.png align="left")

## **Docker Volumes**

In this section, we'll look at some of the commonly used Docker volumes commands!

### **Create Docker Volume**

```bash
docker volume create --name volume-name
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/vol-create.png align="left")

### **List Docker Volumes**

```bash
docker volume ls
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/volume-ls.png align="left")

### **Mounting Docker Volume using the -v Flag**

We can mount the volume inside the Docker container once it is created using the below command:

```bash
docker run -it --name <container-name> -v <volume-name>:<path-in-container-where-volume-is-mounted> <image-name>
```

We are creating a new container with the container name `<container-name>` using the image `<image-name>` and then mount the volume `volume-name` inside the container at `path-in-container-where-volume-is-mounted`.

### **Mounting Docker Volume using the --mount Flag**

```bash
docker run -it --name <container-name> --mount soure=<volume-name>, destination=<path-in-container-where-volume-is-mounted> <image-name>
```

### **Get Details about a Docker Volume**

```bash
docker volume inspect <volume-name>
```

### **Remove a Docker Volume**

To remove the volume, we first have to remove the containers using that volume and then only we can remove the volume.

To remove the volume we can use the below command:

```bash
docker volume rm <volume-name>
```

### **Volume Mount using bind-mount**

To mount any specific host directory inside the container, we have to use the below Docker run command:

```bash
docker run -it -v /path/on/host:/path/in/contianer/where/volume/has/to/be/mounted <image-name>
```

### **Creating Bind Mount Volume using the --mount flag**

```bash
docker run -it --name <container_name> --mount type=bind,source=/path/on/host/,target=/path/on/container first-image
```

If a directory in a container has some content and you mount the volume with type `bind` onto that directory, the existing content of that directory would be lost and you get an empty directory.

## **Docker System-wide Commands**

### **Docker Info**

```bash
docker info
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-info.png align="left")

#### **Docker Stats of the running Container**

```bash
docker stats
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-stats.png align="left")

#### **Docker Stats of all the Containers**

```bash
docker stats --all
```

### **Show the Docker Version**

```bash
docker version
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-version.png align="left")

### **Get Detailed Info about an Object (Container, Image, Volume, etc)**

```bash
docker inspect <name or id>
```

```bash
docker inspect nginx
```

### **Get the Summary of Docker Usage**

```bash
docker system df
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/docker-usage.png align="left")

This gives the information about:

1. The total size of all the containers
    
2. The total size of all the images
    
3. The total size of the volumes
    
4. Cache
    

### **Clean your Docker system**

```bash
docker system prune
```

![](https://buddy.works/tutorials/assets/posts/docker-commands-cheat-sheet/system-prune.png align="left")

This command will clean:

1. All the stopped containers
    
2. All the networks not used by at least one container
    
3. All the dangling images
    
4. All the dangling build cache
    

---

## **Conclusion**

This is an extensive guide on using Docker. We learned many useful commands related to Docker containers, images, networks and volumes in this article.