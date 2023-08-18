---
title: "day19-Docker Project"
datePublished: Fri Aug 18 2023 07:37:22 GMT+0000 (Coordinated Universal Time)
cuid: cllga2ehi00000ak01ydc64z2
slug: day19-docker-project
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692343943215/aeca01bd-f1fa-4271-97d4-fcde1618a201.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1692344218132/7d63d434-14a8-46a5-9fdd-9accb5aee745.png
tags: docker, devops, dockerfile, docker-compose, docker-images

---

## **Docker-Volume**

Docker allows you to create something called volumes. Volumes are like separate storage areas that can be accessed by containers. They allow you to store data, like a database, outside the container, so it doesn't get deleted when the container is deleted. You can also mount from the same volume and create more containers having the same data.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692343540968/6a65697f-e667-428a-92b8-519172fa4d74.avif align="center")

### Docker Volume Commands -

Here's a list of Docker volume commands:

1. `docker volume create <VOLUME_NAME>`: Create a named volume.
    
2. `docker volume ls`: List available volumes.
    
3. `docker volume inspect <VOLUME_NAME>`: Display detailed volume information.
    
4. `docker volume rm <VOLUME_NAME>`: Remove a named volume (must be unused).
    
5. `docker volume prune`: Remove all unused volumes.
    
6. `docker run -v <VOLUME_NAME>:<CONTAINER_PATH>`: Mount a named volume to a container.
    
7. `docker run -v <HOST_PATH>:<CONTAINER_PATH>`: Mount a host directory to a container.
    

# Docker Network

Docker allows you to create virtual spaces called networks, where you can connect multiple containers (small packages that hold all the necessary files for a specific application to run) together. This way, the containers can communicate with each other and with the host machine (the computer on which the Docker is installed). When we run a container, it has its own storage space that is only accessible by that specific container. If we want to share that storage space with other containers, we can't do that.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692343588791/6826b451-91fe-4244-9dc2-9c67027ca39c.avif align="center")

### Docker Network Commands -

Here's a list of Docker network commands:

1. `docker network create <NETWORK_NAME>`: Create a new user-defined network.
    
2. `docker network ls`: List available networks.
    
3. `docker network inspect <NETWORK_NAME>`: Display detailed network information.
    
4. `docker network rm <NETWORK_NAME>`: Remove a user-defined network (must be unused).
    
5. `docker network prune`: Remove all unused networks.
    
6. `docker run --network <NETWORK_NAME>`: Specify a network for a container to join.
    
7. `docker network connect <NETWORK_NAME> <CONTAINER_NAME>`: Connect a container to a user-defined network.
    

`docker network disconnect <NETWORK_NAME> <CONTAINER_NAME>`: Disconnect a container from a user-defined network.

### **Task-1:**

**Create a multi-container docker-compose file which will bring UP and bring DOWN containers in a single shot (Example - Create application and database container)**

* The **docker-compose up** command with the **\-d** flag is used to start and run a multi-container application defined in a **docker-compose.yml** file in detached mode. The **\-d** flag stands for "detached" mode and it runs the container in the background.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQGi_MTIIuIXjQ/article-inline_image-shrink_1500_2232/0/1674795946167?e=1697673600&v=beta&t=0e2RIgmiGbMuVj9iQOxs_lQyUKSt0s9ILexYmiE3wBQ align="left")

* The **docker-compose scale** command is used to adjust the number of containers for a service defined in a **docker-compose.yml** file. This command allows you to easily scale the number of containers running for a particular service, which can be useful for handling changes in traffic or load.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQHTiC5svqJUYw/article-inline_image-shrink_1500_2232/0/1674796008143?e=1697673600&v=beta&t=3uMW3B85CVJnKi6JAFMrsGyJ1PjMv4NEEiLQHwVztFM align="left")

* The **docker-compose ps** command is used to list the containers that are running for a multi-container application defined in a **docker-compose.yml** file. This command will display the status of each container, including the container name, service name, and the command that was used to start the container.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQFLnzMVuQlw4w/article-inline_image-shrink_1500_2232/0/1674796065986?e=1697673600&v=beta&t=EApSuFXOgm0jYEfmZin1AoIvapA-xjDkuebKUYrwaBo align="left")

* The **docker-compose logs** command is used to view the logs for all the services defined in a **docker-compose.yml** file. This command will display the logs for all the running containers for the specified services, in real-time.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQEOxhcXy1zBwg/article-inline_image-shrink_1500_2232/0/1674796101988?e=1697673600&v=beta&t=D-8wCgWJZpPKL7wJ6IDvwSQEK3HwJ9iPNQWpoj_JNlA align="left")

* The **docker-compose down** command is used to stop and remove all the containers, networks, and volumes defined in a **docker-compose.yml** file. This command will stop and remove all the containers that were created by the **docker-compose up** command, as well as any networks and volumes that were created for the application.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQH8J6Z48RtZIg/article-inline_image-shrink_1500_2232/0/1674796336097?e=1697673600&v=beta&t=IOcA3iiO1BKytoVphXUEOvauhAr3FaaymYphaYoINtc align="left")

### **Task-2:**

* **Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.**
    
* **Create two or more containers that read and write data to the same volume using the docker run --mount command.**
    
* **Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.**
    
* **Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you're done**.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D5612AQHWSEIrVS55rQ/article-inline_image-shrink_1000_1488/0/1674796246647?e=1697673600&v=beta&t=IU9DkSrQJBqIyq7x02_N7EY4m75KBSZsEk2pRWDR5Os align="left")

## conclusion

Using Docker Volumes and Named Volumes, you've successfully shared data between multiple containers. These volumes act like shared folders, making it easy for containers to communicate and collaborate. Named volumes keep your data organized and allow containers to access it even after they're stopped or removed. It's a fantastic way to make sure your data sticks around even in the dynamic world of containers! 📂🐳

---

### Thank you for reading this blog! 📖 Hope you have gained some value.

please Follow me on Linkedin- [www.linkedin.com/in/nikhil-raut-965133b4](http://www.linkedin.com/in/nikhil-raut-965133b4)