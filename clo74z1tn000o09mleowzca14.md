---
title: "Day-38 About AWS Cloud -(Basic)"
datePublished: Thu Oct 26 2023 12:03:59 GMT+0000 (Coordinated Universal Time)
cuid: clo74z1tn000o09mleowzca14
slug: day-38-about-aws-cloud-basic
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698240460968/eb0d10c0-b956-4880-945c-dd927b8f3517.png
tags: cloud, aws, devops, iam, trainwithshubham

---

## What is AWS

Amazon Web Services (AWS) is a cloud computing platform and API provider that operates as a subsidiary of Amazon. It offers a range of on-demand services, including computing power, storage, databases, machine learning, analytics, content delivery, Internet of Things (IoT), and security.

AWS operates on a metered pay-as-you-go basis, making it an affordable option for individuals, companies, and governments.

Some of its key services include Amazon EC2, Amazon S3, Amazon RDS, AWS Lambda, Amazon DynamoDB, Amazon SNS, Amazon CloudFront, Amazon Elastic Beanstalk, Amazon Machine Learning, and Amazon SageMaker.

AWS is renowned for its reliability, scalability, and flexibility, and has a global network of data centers that enable users to deploy applications and services worldwide. It caters to a diverse range of industries, from startups to large-scale enterprises.

## I AM

AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. With IAM, you can centrally manage permissions that control which AWS resources users can access. You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698240127265/9e17c85f-bb5d-4fad-bb30-70fba62a7e92.png align="center")

### **Task1:**

Create an IAM user with the username of your wish and grant EC2 Access. Launch your Linux instance through the IAM user that you created now and install Jenkins and Docker on your machine via a single Shell Script.

Log in to the AWS Management Console. Login as root user and type “**<mark>IAM</mark>**” in the search box. Go to the IAM service and click on "Users" in the left menu.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698245745121/34e1acd6-01a6-4e59-9ab0-b83ffd6f4757.png align="center")

Click on "<mark>Create user</mark>" and enter a username of your choice.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698245828618/02df9969-706d-4dc5-9b43-d63b45ab03ba.png align="center")

Select "<mark>Programmatic access</mark>" and click "Next".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698245957745/8f02a629-9c72-488a-bc83-b3fcc346c566.png align="center")

Select "<mark>Attach existing policies directly</mark>" and select the policy "<mark>AmazonEC2FullAccess</mark>".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698246305820/bc1bb16d-16d4-4ebd-ad1a-a801c2d8ef3f.png align="center")

Click "Next" until you reach the end, and then click "<mark>Create user</mark>".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698246517584/7f5bf60d-3f71-4714-b318-2dc675a82f17.png align="center")

### **To launch a Linux instance using your IAM user, follow these steps:**

Sign in AWS account as an <mark>IAM user</mark> which we created above.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698308905946/e970a7a0-997a-4e6e-8507-12cf17445a79.png align="center")

Go to the EC2 service and click on <mark> "Launch instance".</mark>

Choose a Linux AMI.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698309224051/fbcc473f-e5d6-4971-82a5-035a927cb572.png align="center")

After launching the instance let's connect to the server.

Install *Jenkins* and *Docker* on your machine via a single Shell Script.

```bash
#!/bin/bash
sudo apt update
sudo apt install openjdk-8-jdk
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
sudo apt update
sudo apt install docker.io
sudo systemctl start docker
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698319425052/e481db55-9cab-4bfa-9327-7c509a07ca0e.png align="center")

Check the Docker and Jenkins version

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698320269246/5ca02eba-e94f-49cc-8475-fb0ac1c589f9.png align="center")

---

## Task-2

In this task, you need to prepare a DevOps team of avengers. Create 3 IAM users of Avengers and assign them to devops groups with IAM policy.

**Go to Home** ----&gt; *User-group* ----&gt; Create a user group. then add the Created user to the group.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698321393358/872383b4-84dc-489f-b64b-651f3d426f2d.png align="center")

In the "Attach Policy" step, search for and select the "AmazonEC2FullAccess", "AmazonS3FullAccess", and "AmazonRDSFullAccess" policies.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1698321194348/d77e7b55-f03c-4190-a710-0a9df8d6c811.png align="center")