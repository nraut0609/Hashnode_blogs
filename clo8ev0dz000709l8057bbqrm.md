---
title: "Day 40 AWS EC2 Automation"
datePublished: Fri Oct 27 2023 09:28:32 GMT+0000 (Coordinated Universal Time)
cuid: clo8ev0dz000709l8057bbqrm
slug: day-40-aws-ec2-automation
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698398815276/4509396a-ba70-4820-a351-5fb65ac08b4c.png
tags: cloud, aws, automation, devops, trainwithshubham

---

# **Define EC2:**

EC2 stands for Amazon Elastic Compute Cloud. It is a core service provided by Amazon Web Services (AWS) that offers scalable virtual server instances in the cloud. EC2 enables users to rent virtual machines, known as instances, on which they can run applications and perform various computing tasks.

## Key features of EC2:

1. **<mark>Instances</mark>**: EC2 allows users to launch virtual machine instances with various specifications, such as CPU, memory, storage, and networking capacity. Users have control over the operating system and software installed on these instances.
    
2. **<mark>Scalability</mark>**: EC2 provides the ability to scale instances up or down based on demand. Users can easily add or remove instances to match their workload requirements, ensuring optimal performance and cost efficiency.
    
3. **<mark>Instance Types</mark>**: EC2 offers a wide range of instance types optimized for different use cases, such as general-purpose, memory-intensive, compute-optimized, storage-optimized, and GPU instances.
    
4. **<mark>Elastic IP Addresses</mark>**: EC2 allows users to allocate and associate static IP addresses with their instances. This provides a consistent IP address for the instance, even if it is stopped and started.
    
5. **<mark>Storage Options</mark>**: EC2 provides various storage options, including Amazon Elastic Block Store (EBS) for persistent block-level storage, Amazon Simple Storage Service (S3) for object storage, and instance store volumes for temporary storage.
    
6. **<mark>Networking</mark>**: EC2 instances can be launched within virtual private clouds (VPCs), allowing users to define their network configurations, subnets, route tables, and security settings. EC2 instances can also be associated with elastic network interfaces (ENIs) and security groups to control inbound and outbound traffic.
    
7. **<mark>Load Balancing and Auto Scaling</mark>**: EC2 integrates with other AWS services, such as Elastic Load Balancing (ELB) and Auto Scaling, to distribute incoming traffic across multiple instances and automatically adjust the instance capacity based on demand.
    
8. **<mark>Pricing</mark>**: EC2 offers different pricing models, including On-Demand instances for pay-as-you-go pricing, Reserved instances for discounted pricing with long-term commitments, and Spot instances for bidding on spare compute capacity at lower costs.
    

# Automation in EC2:

Automation in EC2 refers to the process of automating the management and provisioning of EC2 instances and associated resources. This automation can be achieved using various AWS services and features, allowing users to streamline and simplify the deployment, configuration, and management of EC2 instances.

## Key aspects of automation in EC2:

1. <mark>EC2 Auto Scaling</mark>
    
    * EC2 Auto Scaling is a service that automatically adjusts the number of EC2 instances in a fleet based on predefined scaling policies.
        
    * With Auto Scaling, you can set up dynamic scaling based on factors such as CPU utilization, network traffic, or application-specific metrics.
        
2. <mark>Launch Templates and Configuration Management</mark>
    
    * EC2 Launch Templates enable you to define the configuration parameters for your EC2 instances, such as instance type, AMI, storage, networking, and security settings.
        
3. <mark>AWS CloudFormation</mark>
    
    * CloudFormation is a service that allows you to define and provision AWS resources using templates written in JSON or YAML.
        
    * With CloudFormation, you can create a template that describes your EC2 instance and its associated resources, including networking, security groups, and storage.
        
4. <mark>AWS Elastic Beanstalk</mark>
    
    * Elastic Beanstalk is a fully managed platform-as-a-service (PaaS) offering from AWS. It simplifies the deployment and management of applications by automatically handling the underlying infrastructure, including EC2 instances.
        
5. <mark>AWS Lambda</mark>
    
    * AWS Lambda is a serverless computing service that can be used to automate tasks and perform actions based on events.
        
    * You can use Lambda functions to trigger actions like starting or stopping EC2 instances, creating snapshots, or performing other tasks related to EC2 management.
        
6. <mark>AWS Systems Manager</mark>
    
    * AWS Systems Manager provides a suite of tools for managing and automating EC2 instances at scale.
        
    * It includes features like Run Command for executing commands remotely on instances, State Manager for managing instance configuration, and Automation for creating and executing workflows to perform tasks across multiple instances.
        

# Launch template in AWS EC2:

* You can make a launch template with the configuration information you need to start an instance. You can save launch parameters in launch templates so you don't have to type them in every time you start a new instance.
    
* For example, a launch template can have the AMI ID, instance type, and network settings that you usually use to launch instances.
    
* You can tell the Amazon EC2 console to use a certain launch template when you start an instance.
    
* It can be created via the AWS Management Console, CLI, or SDKs. Once created, they can be used for manual instance launches or integrated with other services like Auto Scaling or AWS CloudFormation for automated provisioning.
    

# Instance Types:

Amazon EC2 has a large number of instance types that are optimized for different uses. The different combinations of CPU, memory, storage and networking capacity in instance types give you the freedom to choose the right mix of resources for your apps. Each instance type comes with one or more instance sizes, so you can adjust your resources to meet the needs of the workload you want to run.

### Commonly used instance types in EC2:

1. **General Purpose**: These instances provide a balance of computing, memory, and networking resources. They are suitable for a wide range of workloads, including web servers, small databases, and development environments. Examples include <mark>t2.micro, m5.large</mark>.
    
2. **Compute Optimized**: These instances are designed for compute-intensive workloads that require high-performance processors. They offer a higher ratio of CPU power to memory and are suitable for tasks like batch processing, media encoding, and high-performance scientific computing. Examples include <mark>c5.large, c5n.4xlarge</mark>.
    
3. **Memory Optimized**: These instances are optimized for memory-intensive workloads that require large amounts of RAM. They are suitable for data-intensive applications, in-memory databases, and analytics workloads. Examples include <mark>r5.xlarge, x1e.2xlarge.</mark>
    
4. **Storage Optimized**: These instances are designed for storage-intensive workloads that require high I/O performance and large amounts of local storage. They are suitable for data warehousing, distributed file systems, and large-scale databases. Examples include <mark>i3.large, d2.xlarge.</mark>
    
5. **GPU Instances**: These instances are equipped with powerful GPUs (Graphics Processing Units), which are ideal for tasks like graphics rendering, machine learning, and scientific simulations. They provide high-performance parallel processing capabilities. Examples include <mark>p3.2xlarge, g4dn.xlarge.</mark>
    
6. **FPGA Instances**: These instances are equipped with Field-Programmable Gate Arrays (FPGAs), which can be customized to accelerate specific workloads. They are suitable for tasks like real-time video processing, financial analysis, and genomics research. Example: <mark>f1.2xlarge.</mark>
    
7. **Burstable Performance Instances**: These instances provide a baseline level of performance with the ability to burst when additional CPU capacity is required. They are suitable for workloads with variable CPU utilization, such as small web applications and development/test environments. Examples include <mark>t3.micro, t3a.small.</mark>
    

## AMI:

* AMI stands for **Amazon Machine Image**. In AWS (Amazon Web Services), an AMI is a pre-configured template used to create virtual machines, known as instances, within EC2 (Elastic Compute Cloud). It serves as a baseline for launching instances with specific operating systems, software configurations, and application stacks.
    
* An AMI is an image that AWS supports and keeps up to date. It contains the information needed to start an instance. When you launch an instance, you must choose an AMI. When you need multiple instances with the same configuration, you can launch them from a single AMI.
    

### **Task1:**

> ***1) Create a launch template with Amazon Linux 2 AMI and t2.micro instance type with Jenkins and Docker setup (You can use the Day 39 User data script for installing the required tools.***
> 
> ***2) Create 3 Instances using Launch Template, there must be an option that shows the number of instances to be launched, can you find it?***  

Navigate to the Launch template section in AWS and create a template.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698385440049/d59a2503-7c94-40f6-af79-9a07b73c63df.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698385867460/abbc3117-371b-45ec-ac2e-4c4e3b5ba705.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698386451619/f774f3be-eed8-4ee6-a4a1-40b08e27732c.png align="center")

```bash
 #!/bin/bash
 sudo apt update
 sudo apt install openjdk-11-jre -y

 curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
 echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
   https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
   /etc/apt/sources.list.d/jenkins.list > /dev/null
 sudo apt-get update
 sudo apt-get install jenkins -y

 sudo systemctl enable jenkins
 sudo systemctl start jenkins

 sudo apt-get update
 sudo apt-get install docker.io -y
 sudo systemctl start docker
```

Now click to create a template and then navigate to the Action section to launch an instance out of the created template.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698386701149/b3413736-0603-4270-a1f9-e777cd04c5a0.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698387588221/969224de-84eb-42c7-a0e8-a448e96b084c.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698387928815/7d7f64b4-b0b4-49c9-9403-3d407338ee3a.png align="center")

## **Create an Auto-Scaling group.**

1. Navigate to the Autoscaling group section and give a name to the group that will be created. Select the template that we have created in the above task.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698388620090/9dcef7f3-1049-4168-a995-2e4f93dd786b.png align="center")
    
    1. Provide the subnet you want to keep your servers at.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687706279/d77fb46d-8be6-44fe-bbfc-004f5ba9c47c.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687731695/53d22306-8243-4153-a750-da5673b2fcdf.png?auto=compress,format&format=webp align="left")
        
    2. No Load Balancer and No VPC are required for this Auto Scaling.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687844274/1c7e248f-b279-4f52-8529-fa3e5250ddff.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687856944/c654f966-98a2-4ffd-9b29-a7adfa76345c.png?auto=compress,format&format=webp align="left")
        
    3. Provide the desired capacity and maximum capacity of the group to create servers. For this task I'm choosing 2 as Desired capacity, minimum 1 and maximum 4 capacity.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687935002/26596f22-f8dc-4694-9fa6-d76a228ced43.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684687954947/c3c1c9d8-46bf-451e-9f65-7fe1147b27e0.png?auto=compress,format&format=webp align="left")
        
    4. Skip the adding notifications and tags
        
    5. Review and now create the group.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684688032908/fefd6af9-6631-4def-a88c-61d19f163a26.png?auto=compress,format&format=webp align="left")
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684688045604/f35df095-3c88-4f43-b789-acea8ea2faac.png?auto=compress,format&format=webp align="left")
        
    6. Now the Auto Scaling group is deployed and it will create 2 instances as we are desired for it.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684688351327/d844243b-ed10-4386-9600-ff9c1b43b02c.png?auto=compress,format&format=webp align="left")
        
    7. Now, navigate to the EC2 instance section and you can see 3 servers.
        
        Out of 3, 1 server were created for above task 1 and the rest 2 are spun up by the Auto-Scaling group as the desired field we gave is 2.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684688412289/30087c68-2e8f-44ea-bcb2-34c8e1311e89.png?auto=compress,format&format=webp align="left")