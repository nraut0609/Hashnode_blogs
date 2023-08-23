---
title: "Getting Started with Jenkins"
datePublished: Tue Aug 22 2023 16:44:42 GMT+0000 (Coordinated Universal Time)
cuid: cllmjdp8d000v08jvemns73tf
slug: getting-started-with-jenkins
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692719635767/ee97affa-fffb-4ce4-a79e-111ddd35a097.jpeg
tags: devops, jenkins, jenkins-devops, 90daysofdevops, jenkins-installation

---

### What is Jenkins? 🤖

Jenkins is like a magical wand 🪄 for developers! It's an open-source tool written in Java ☕ that dances to the rhythm of Continuous Integration and Continuous Delivery 🚀. Think of it as a DevOps genie 🧞 that automates tasks. Jenkins helps make building, testing, and deploying software a breeze 🌬️ for all the devs out there. It's like having a helpful robot buddy in your coding adventure.

Jenkins is your trusty sidekick that speaks Java 🚀. With its superpowers, it weaves CI/CD workflows called pipelines 🛠️. These pipelines are like well-choreographed dance routines for your code. 🩰 Just like adding toppings to a pizza 🍕, Jenkins uses plugins to mix and match DevOps tools. Need to work with Git, Maven, Amazon EC2, or other cool stuff? 🛠️🔌 Plugins got you covered!

Imagine being a bit lazy 😴 and letting technology do the heavy lifting. Jenkins is your tech butler 🤖. No more babysitting jobs! It takes care of completing one job and gracefully moving on to the next, all on its own. Isn't that awesome?

Curious about how to get started with this tech wizardry? Here's a spell for creating a Jenkins freestyle project: 🪄

1. 1. Enter Jenkins and find the main dashboard 🖥️.
        
    2. Spot the "New Item" button in the sidebar and give it a tap 👆.
        
    3. Whisper a name for your project, pick "Freestyle project" as the job style, and hit "OK" 👌.
        
    4. On the project setup page, choose source code management, set up triggers, create a comfy build environment, and define build steps. It's like decorating your project headquarters! 🏰
        
    5. In the build step, you can tell Jenkins the cool tasks you want it to do. Think of it like giving your robot buddy a to-do list 🗒️.
        
    6. Once everything's set, chant "Save" and your project will come to life! 🎉
        
    7. Ready to see the magic happen? Click "Build Now" and watch Jenkins do its thing ✨.
        
    
    Now you've got the power of Jenkins in your hands! 🌟 Let it automate, simplify, and sparkle up your coding journey. 🚀🌈
    

### **2\. Create a freestyle pipeline to print "Hello World!!**

**Steps:**

1. Install Jenkins on AWS EC2 Ubuntu instance.
    
2. For Jenkins used port 8080, browse instance-public-IP/8080 it will open the Jenkins dashboard.
    
3. Click on the "New Item" button on the left sidebar.
    

Note: By now Jenkins should be installed on your machine(as it was a part of previous tasks, if not follow [**Installation Guide**](https://www.jenkins.io/doc/book/installing/linux/))

Step 1: Log into the EC2 instance. After logging in to the EC2 instance update the server as. First, we will update the system

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691462960574/0bf938bb-5c51-4e7a-8fcb-3bdb7630cb23.png?auto=compress,format&format=webp align="left")

Step 2: Install Java

```dockerfile
sudo apt install openjdk-11-jre
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463025347/344a8137-c6a7-41b4-8299-1a007004fa4e.png?auto=compress,format&format=webp align="left")

step 3: Copy the curl command to install Jenkins

```bash
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io.key | sudo tee \   /usr/share/keyrings/jenkins-keyring.asc > /dev/null 
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \   https://pkg.jenkins.io/debian binary/ | sudo tee \   /etc/apt/sources.list.d/jenkins.list > /dev/null
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463120912/44081b57-274a-4f8a-98e8-98375b1be20a.png?auto=compress,format&format=webp align="left")

And then we will update the server using the get update command

step 4: Install Jenkins using the command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463177561/2df8ba51-cb7b-44dc-8c3e-9b673a8f06a8.png?auto=compress,format&format=webp align="left")

step 5: Let's start Jenkins, before that open port 8080 on AWS in security groups as Jenkins listen to port 8080

First, we will enable Jenkins, then we will start Jenkins and then we will see the status of Jenkins

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463270416/356f6909-dd95-4935-a173-0368629f956b.png?auto=compress,format&format=webp align="left")

```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
```

After this copy-paste the public address URL you will see Jenkins home screen as

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463611877/b45dc08c-4194-4cb2-bbce-3e50d6324695.png?auto=compress,format&format=webp align="left")

1. Now to login into Jenkins we need an admin password to get that copy paste the path and execute in your server as
    

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Once you login inyo jenkins click on Install suggested Plugins as will install the plugins

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463833217/765662b1-f7d7-437d-8f83-6ef1350eef68.png?auto=compress,format&format=webp align="left")

1. After installation, it will ask you to add an admin user as add your details and continue
    

After setting up we will be redirected to Jenkins's home screen

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691463940644/f106bb2a-19f7-4af0-bc3c-3aaa68574c5a.png?auto=compress,format&format=webp align="left")

Now let us create the pipeline for Hello World in Jenkins

Click on the "New Item" button on the sidebar

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691464035805/4bfc4dfa-d8c6-4c65-8e58-f101a9ed1672.png?auto=compress,format&format=webp align="left")

1. Give your project a name, select "Freestyle project" as the job type, and click on the "OK" button
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692816945784/ba892b04-c85f-4b37-b34c-1921b7056c85.png align="center")

1. In the build section, we have an option ‘Execute Shell’ by which we can write some commands or code:
    

![No alt text provided for this image](https://media.licdn.com/dms/image/D4D12AQGH8EIcVhkb2g/article-inline_image-shrink_1000_1488/0/1674557935626?e=1698278400&v=beta&t=_u4M6e65jBLBkXH53gMpq-WyHPrtm4ceVBx6e4mxPEg align="left")

6\. In the command field, enter the command to print "Hello World", such as **echo "Hello World!!"**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692816822620/7779a84c-127c-4402-af1c-c5185ec3418a.png align="center")

7\. Click on the "Save" button at the bottom of the page to create the project.

8\. Once the project is created, click on the "Build Now" link to run the project.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692816735587/56f2fac7-82ad-40e6-9d15-fdd12182345c.png align="center")

You can now see changes in the Console output

---

### *Thank You ..... Happy Learning 😊* [*follow me on Linkedin*](http://www.linkedin.com/in/nikhil-raut-965133b4)

### I appreciate you reading!! ✅🐳