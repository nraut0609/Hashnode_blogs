---
title: "Day 17 Task: Docker Project for DevOps Engineers."
datePublished: Mon Aug 14 2023 20:18:11 GMT+0000 (Coordinated Universal Time)
cuid: cllbbhfdk000309mqfydg4mat
slug: day-17-task-docker-project-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691869453619/23222878-80ca-4ee7-8eb0-b6671c0a3818.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1691870803259/6983505f-57b7-4a58-93f4-0c912ff3e9d6.jpeg
tags: docker, devops, dockerfile, docker-compose, docker-images

---

### **Dockerfile:**

A Dockerfile is a script that contains instructions for building a Docker image. It is used to automate the process of creating and configuring a container image. The Dockerfile specifies the base image to use, the commands to run to install dependencies, and any other configuration options.

A Dockerfile is like a set of instructions for making a container. It tells Docker what base image to use, what commands to run, and what files to include. For example, if you were making a container for a website, the Dockerfile might tell Docker to use an official web server image, copy the files for your website into the container, and start the web server when the container starts.

## **Dockerfile Commands:**

Here's a more concise and specific list of common Dockerfile commands:

1. `FROM`: Specifies the base image to build upon.
    
2. `COPY` or `ADD`: Copies files from the host machine to the image.
    
3. `RUN`: Executes commands during the image build process.
    
4. `CMD`: Sets the default command to run when the container starts.
    
5. `ENTRYPOINT`: Sets the main executable for the container.
    
6. `ENV`: Sets environment variables inside the container.
    
7. `EXPOSE`: Informs Docker about the ports the container will listen on.
    
8. `VOLUME`: Creates a mount point for data persistence.
    
9. `WORKDIR`: Sets the working directory for the image.
    
10. `USER`: Specifies the user context for the container.
    

### **🗄️Docker Storage:**

Consider you have a critical containerized application that stores and fetches data, unfortunately, if that container gets crashed or delete then you will lose crucial data, that is how Docker volumes come into the picture. Docker volumes are persistent storage which gives you the capability to persist your data and stored it outside the container, so need to worry about what if the container goes down.

let's understand docker volumes and their features,

**📌Sharing Data:**

Multiple containers can use the same volume to share and exchange information. It's like having a common space/folder where multiple containers can read or write their data.

**📌Performance:**

Volumes are designed to handle data efficiently, making reading and writing data faster. It's similar to having a dedicated desk for writing or reading that's optimized for your tasks.

**📌Isolation:**

The data in the volume is separate from the container, making it easier to manage and back up

### **Task:**

**1.   Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)**

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEX-sKIsblnhA/article-inline_image-shrink_1500_2232/0/1674624580856?e=1697068800&v=beta&t=_f4PyDXJ-_JDvfWC-3Sp9Racn4wDbjeW78ImcbUh92Q align="left")

·      **FROM** : Specifies the base image to use as the starting point for the new image.

·      **RUN** : Runs commands in the container, such as installing software or updating system settings.

·      **COPY** : Copies files or directories from the host machine to the container file system.

·      **CMD** : Specifies the command that should be run when the container is started.

**2.   Build an Image using Dockerfile.**

To build an image using a Dockerfile, you can use the “docker build” command.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQGQjcsd_uRDRw/article-inline_image-shrink_1500_2232/0/1674624700165?e=1697068800&v=beta&t=XSPQT7fm8kt0nnUzjp_L4mFRt8_JODWJmJ1ExRKZ45s align="left")

**3.   Run the image to create a container.**

To run a container from an image, you can use the “docker run” command.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQF1GJJi9jRQVA/article-inline_image-shrink_1500_2232/0/1674624741132?e=1697068800&v=beta&t=ckp2cuz8iVOJgQrTmTyrfirobsAKw5tMEVlMqtmU888 align="left")

**4.   Verify that the application is working as expected by accessing it in a web browser.**

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQF1yMf1DviykA/article-inline_image-shrink_1500_2232/0/1674624790090?e=1697068800&v=beta&t=Co26O1Fa8hOAyyR7gmal8Ii8PkVoXORBuKfzQTjf0CM align="left")

**5.   Push the image to a public or private repository (e.g. Docker Hub )**

To push an image to a public or private repository, you first need to have an account on the repository platform (e.g. Docker Hub) and be logged in.

Once you are logged in, you can use the **“docker push”** command to push your image to a specific repository.

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQEHBHGU3ujzcw/article-inline_image-shrink_1500_2232/0/1674624845240?e=1697068800&v=beta&t=IT4ySMoMqfIWaXRee-q3fOHSLOFbyMTMAFwkaWbzqpk align="left")

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQGx-2B_1c3pcw/article-inline_image-shrink_1500_2232/0/1674624856225?e=1697068800&v=beta&t=HHcQSxtBlatgNhois3didJexDeV7c5pi7C_gKKoP0jk align="left")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">You can check your DockerHub repositories which will show you have a new repository</div>
</div>

---

### *Thank you for reading! I hope you find this article helpful.*

### *Happy Learning 😊* [*follow me on Linkedin*](http://www.linkedin.com/in/nikhil-raut-965133b4)