---
title: "Day 24 Task: Jenkins CICD with GitHub Integration"
datePublished: Thu Aug 24 2023 18:43:14 GMT+0000 (Coordinated Universal Time)
cuid: cllpihtow000509kzg8tsb94h
slug: day-24-task-jenkins-cicd-with-github-integration
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692903083041/8857841a-7a96-4207-a828-437d00c57b99.png
tags: github, devops, jenkins, github-actions-1, jenkins-devops

---

### **Task-01**

**1)Fork** [**this**](https://github.com/LondheShubham153/node-todo-cicd.git) **repository.**

[![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693240286895/7bf9dacb-3847-484c-9bcf-0243c130ff74.png align="center")](https://github.com/LondheShubham153/node-todo-cicd.git)

**2)Create a connection to your Jenkins job and your GitHub Repository via GitHub Integration.**

Generate the SSH keys for integrating your Jenkins project with your git repository. Use the ssh-keygen command to create public and private key.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693246503056/6b5d93fa-b4b7-4a20-a272-1a1966bbdeee.png align="center")

**Configuring GitHub:**

1)Go to your GitHub account settings.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693246732768/bc1769a2-8f15-4c41-93d8-78d6b92d5f55.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693247571517/6cd62a57-872b-49ec-a313-702ea33905bf.png align="center")

Thus with above command you will get Public key and add this public key in “Key” Section of “SSH & GPG Keys”

**For GitHub-Webhook:**

**Webhooks** provide a way for notifications to be delivered to an external web server whenever certain actions occur on a repository or organization.

1)Go to your GitHub repository and click on **Settings**.

2)Click on **Webhooks** and then click on **Add webhook**.

3)In the ‘Payload URL’ field, paste your Jenkins environment URL. At the end of this URL add /github-webhook/. In the ‘Content type’ select: ‘application/json’ and leave the ‘Secret’ field empty.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692443967864/13a6b13e-81b4-4f13-89b4-8f10fe9d0e0f.png?auto=compress,format&format=webp align="left")

**For Installing the GitHub Integration plugin in Jenkins**

1)Open your jenkins dashboard.

2)Click on the Manage Jenkins button on your Jenkins dashboard

3)Click on Manage Plugins

4)Install GitHub Integration plugin

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444114354/85f740c4-8fd3-4f6d-8cd8-b4a03d93bafe.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444174383/1ff4b518-8996-41ef-a79c-790c0be8c255.png?auto=compress,format&format=webp align="left")

**Configuring Jenkins:**

1)Create a Jenkins job

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444296913/2045f1fb-bb34-453b-9a9e-a31fe58cffaa.png?auto=compress,format&format=webp align="left")

4)Select the “Git” and provide the below credentials

Click on ADD and for the “kind” label select from the drop down list for

5)Add private key which we created using ssh-keygen command.

Provide Unique ID, Description and then paste the “Private key “ at last as “Paraphrase” and click on ADD

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444427338/777412fb-4150-4fb5-9e93-0b561acd335a.png?auto=compress,format&format=webp align="left")

6)Click on the ‘Build Triggers’ tab and then on the ‘GitHub hook trigger for GITScm polling’.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444498693/e0893119-cf41-4a37-ae59-f6f1b1d60e9d.png?auto=compress,format&format=webp align="left")

Once the connection between the Jenkins server and Github is successful a green tick as highlighted below will be shown.

### **Task-02**

1)In the Execute shell run the application using Docker compose

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444663660/a6c5cb6c-662a-4f13-8c94-1d4f5239aeca.png?auto=compress,format&format=webp align="left")

2)You will have to make a Docker Compose file for this Project

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693250094370/8e584775-5950-43d8-b71f-8b5661d1501c.png align="center")

3)After the build you can check the console output.

Now browse the URL with your public IP address with 8000 port. Before that allow 8000 ports in security groups.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693250024240/bcb2c2f2-d7fa-43fb-b4a9-4cd76e408d31.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692444787101/ea390609-daed-48db-86eb-ca636700261f.png?auto=compress,format&format=webp align="left")