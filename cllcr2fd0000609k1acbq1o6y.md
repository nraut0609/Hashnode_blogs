---
title: "Day 18 Task: Docker for DevOps Engineers"
datePublished: Tue Aug 15 2023 20:22:12 GMT+0000 (Coordinated Universal Time)
cuid: cllcr2fd0000609k1acbq1o6y
slug: day-18-task-docker-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691870734140/11acbc59-2b08-48d3-b478-b21d80a4f8fd.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691871032119/e6adb79d-1f65-45ef-a019-a48536352c08.png
tags: docker, devops, dockerfile, docker-compose, docker-images

---

### **Docker Compose:**

Docker Compose is a tool for defining and running multi-container Docker applications. It allows users to configure multiple containers and their settings in a single "docker-compose.yml" file, and then start and stop all of the containers with a single command. This makes it easier to manage and deploy complex applications that consist of multiple components. Additionally, Compose also allows to define the network, volumes, and environment variables for the containers.

## **Docker Compose Commands**

Here's a list of common Docker Compose commands:

1. `docker-compose up`: Create and start containers.
    
2. `docker-compose down`: Stop and remove containers.
    
3. `docker-compose build`: Build or rebuild services.
    
4. `docker-compose start`: Start services.
    
5. `docker-compose stop`: Stop services.
    
6. `docker-compose restart`: Restart services.
    
7. `docker-compose logs`: View service logs.
    
8. `docker-compose ps`: List running containers.
    
9. `docker-compose exec`: Execute a command in a running container.
    

### **What is YAML?**

YAML (short for "YAML Ain't Markup Language") is a human-readable data serialization format. It is often used for configuration files, data exchange between systems, and other uses where a plain-text format is required. YAML is designed to be easy for humans to read and write, and it is often used in place of JSON or XML for these types of applications.

YAML files use indentation and simple punctuation to indicate the structure of the data. For example, a list of items might be represented like this in YAML:

\- item1

\- item2

\- item3

YAML also supports more complex data structures, such as nested lists and dictionaries, and it allows for the use of special characters, such as the **#** symbol for commenting.

YAML files use the file extension **.yml** or **.yaml**

It is also used in many applications, like ansible, kubernetes, docker-compose and more.

### **Task-1:**

**Learn how to use the docker-compose.yml file, to set up the environment, configure the services and links between different containers, and also to use environment variables in the docker-compose.yml file.**

* We need to install docker-compose.
    
* After installation of docker-compose, create docker-compose.yml file.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEamp9lfHlcbw/article-inline_image-shrink_1500_2232/0/1674626375964?e=1697068800&v=beta&t=Lb--jhwKbop4EmuW70TtT9mjy94m3mXC_0OR-2VTlT4 align="left")

* Now run the docker-compose.yml file.
    

The **“docker-compose up”** command is used to start and run a Docker Compose application. It reads the configuration defined in the docker-compose.yml file and creates and starts the specified services (containers) and networks.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFf3hSEU53EYw/article-inline_image-shrink_1500_2232/0/1674626489061?e=1697068800&v=beta&t=Zj216T1ysJUjiikptyl0j7YhqEQySOiK00TWtk7jMgY align="left")

* Verify that application is working by accessing it in a web browser.
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQG6FdkOxmTP4Q/article-inline_image-shrink_1500_2232/0/1674626571453?e=1697068800&v=beta&t=Ob0uPGNKFDi-Bs8gnI9XGMNoC6qdec8ZtKjKCIXEhcs align="left")

**The “docker-compose down**” command stops all the services and cleans up the containers, networks, and images.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFbOvcPxASNgA/article-inline_image-shrink_1500_2232/0/1674626600368?e=1697068800&v=beta&t=qJKo2orKtQmke36a6wBuBrotNiNGuq9Y3UtonlksExQ align="left")

### **Task-2:**

* **Pull a pre-existing Docker image from a public repository (e.g. Docker Hub) and run it on your local machine. Run the container as a non-root user (Hint- Use usermod command to give user permission to docker). Make sure you reboot instance after giving permission to user.**
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFLYQ4nuXkWLg/article-inline_image-shrink_1500_2232/0/1674626688939?e=1697068800&v=beta&t=F4RLmCLIOachqKV2YPiZNDK-bVw8eleRGd2BolG1cM4 align="left")

* **Inspect the container's running processes and exposed ports using the docker inspect command.**
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQHsBCPEIBw3pQ/article-inline_image-shrink_1500_2232/0/1674626721650?e=1697068800&v=beta&t=5HhtLK7z8zl2yfhOJH24beAEMJhlDFuVhqpSzrVxULU align="left")

* **Use the docker logs command to view the container's log output.**
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEeG3HGLIDjKg/article-inline_image-shrink_1500_2232/0/1674626760053?e=1697068800&v=beta&t=oogcdoaRCyJ3xH8qJXqfwUSk5_pB2_qjjJJsZIdPJTo align="left")

* **Use the docker stop and docker start commands to stop and start the container.**
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQFhnE8mPGDA4g/article-inline_image-shrink_1500_2232/0/1674626785904?e=1697068800&v=beta&t=TagDJDJi4gS5ZuZQcM7vyKv_LnISWSwRS9cB13RwTC0 align="left")

* **🌟 <mark>Use the docker rm command to remove the container when you're done.</mark>**
    
    To remove the container...  
    **step 1:** First, stop the container using the `docker stop <container_id>`command.  
    **step 2:** Then, remove the container `docker rm <container_id>` command as shown below.
    
    first, you have to stop the container then you can remove the container :
    
    so first you have to run the docker stop &lt;container\_id&gt;
    
    then remove the container using
    
    docker rm&lt;container\_id&gt;
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQE12gF_RFGHfw/article-inline_image-shrink_1500_2232/0/1674626829204?e=1697068800&v=beta&t=5xT_JVlQu2XGti3k_dL9tTTD6958R4Er616SB8-El20 align="left")

---

### *Happy Learning 😊* [*follow me on Linkedin*](http://www.linkedin.com/in/nikhil-raut-965133b4)

### I appreciate you reading!! ✅🐳