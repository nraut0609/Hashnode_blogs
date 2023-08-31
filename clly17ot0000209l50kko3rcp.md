---
title: "Day-28  Jenkins Agent"
datePublished: Wed Aug 30 2023 17:49:23 GMT+0000 (Coordinated Universal Time)
cuid: clly17ot0000209l50kko3rcp
slug: day-28-jenkins-agent
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693417538469/0ec28047-987f-4d18-99e2-9107ccf709c1.png
tags: aws, devops, jenkins, 90daysofdevops, trainwithshubham

---

### **Jenkins Master (Server)**

Jenkins’s server or master node holds all key configurations. The Jenkins master server is like a control server that orchestrates all the workflow defined in the pipelines. For example, scheduling a job, monitoring the jobs, etc.

### **Jenkins Agent**

An agent is typically a machine or container that connects to a Jenkins master and this agent executes all the steps mentioned in a Job. When you create a Jenkins job, you have to assign an agent to it. Every agent has a label as a unique identifier.

When you trigger a Jenkins job from the master, the actual execution happens on the agent node that is configured in the job.

A single, monolithic Jenkins installation can work great for a small team with a relatively small number of projects. As your needs grow, however, it often becomes necessary to scale up. Jenkins provides a way to do this called “master to agent connection.” Instead of serving the Jenkins UI and running build jobs all on a single system, you can provide Jenkins with agents to handle the execution of jobs while the master serves the Jenkins UI and acts as a control node.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693408731848/3dc649b0-840f-4f28-b732-5006944c347e.png align="center")

### **Pre-requisites**

Let’s say we’re starting with a fresh Ubuntu 22.04 Linux installation. To get an agent working make sure you install Java ( same version as Jenkins master server ) and Docker on it.

<mark>Note:-</mark> While creating an agent, be sure to separate rights, permissions, and ownership for Jenkins users.

## **Task-01**

**Create an agent by setting up a node on Jenkins**

**Create a new AWS EC2 Instance and connect it to the master(Where Jenkins is installed)**

**The connection of the master and agent requires SSH and the public-private key pair exchange.**

**Verify its status under the "Nodes" section.**

**Steps:**

### **1) Create 2 EC2 instances for the master and agent**

Make new EC2 instances which will be treated as a “**Master**” and "**Agent**" While creating an EC2 instance, you need to install Jenkins and Java too.

1. Jenkins-master:
    

In the 'Jenkins-agent' instance install Jenkins, the docker.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672073226/c591aebe-c3f6-4f93-979b-4cac9737fc1b.png?auto=compress,format&format=webp align="left")

**2)Generate SSH keys on the “Jenkins-master” EC2 instance**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693494967507/168d8c65-46f1-46ce-b249-b528c11ed102.png align="center")

Add public key from “Jenkins-master” instance to “Jenkins-agent” instance under location “.ssh/authorized\_keys”

**Jenkins-master instance:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672234141/a7a48d94-666d-4ea3-8bbe-d7b6eb28ce53.png?auto=compress,format&format=webp align="left")

**Jenkins-agent instance:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672359509/7abe09aa-5e8f-4272-97b9-70bdbbf066e6.png?auto=compress,format&format=webp align="left")

**3)Create an agent by setting up a node on Jenkins**

Go to the Jenkins dashboard, and click on “Manage Jenkins” Then

Click on “Manage Nodes and Clouds”

To create a node click on "New Node" on the left side

Create your first agent.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672509177/221bdd6d-1eea-4bd4-8f7c-bcb70abbcc4d.png?auto=compress,format&format=webp align="left")

Add details of your node, accordingly.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672570127/efb81d8e-8fa9-4ce4-9389-7ba658721771.png?auto=compress,format&format=webp align="left")

Select the launch method as “**Launch agents via SSH**”. Give public IP of agent in the host field.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692672796585/13e9ece5-41a0-43a8-a21c-864f2128b5fd.png?auto=compress,format&format=webp align="left")

Click on “**Add**” under Credentials.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676134842070/596827e9-8f87-44f0-80a7-7ce59ba50b5e.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

Add the private key that we created in the 'Jenkins-master' instance using ssh-keygen.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676135332215/af4bbc7c-cf2c-41bd-aa43-2356b3d37d86.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

Click on 'save' that will create node. You can see agent will be connected and online.

Your agent is made.

## **Task-02**

**Run your previous Jobs on the new agent**

<mark>Use labels for the agent, your master server should trigger builds for the agent server.</mark>

Firstly we will create a freestyle project and deploy it.

In Jenkins, click on “New Item” and enter the desired name in “**Enter an item name**”, select “**Freestyle project**” and click on OK.

Enter the description field. Select the “GitHub project” checkbox and enter your repository URL from where you will clone all files of your project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693417025373/22aa2d5f-6276-48b5-90de-6d740141fcdb.png align="center")

Go to the configuration of your job, Add label expressions, in add the node label that you created.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676139036641/1f437ca6-df23-4ea9-9fcd-1433545202ed.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

Click on Save, and your project will be tied to Agent1.

Now, build your project. Check console output.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676140283023/b95ec987-06e7-484b-8302-1f13f77bed83.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")

Now, the web app will be running on the “Jenkins-agent” instance and can be accessible via Jenkins-agent-instance-**IP:8000**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676140426873/ac3f4251-f613-4d21-a255-3f6da5b3f30f.png?auto=compress,format&format=webp&auto=compress,format&format=webp align="left")