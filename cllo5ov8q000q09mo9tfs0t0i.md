---
title: "Jenkins Freestyle Project for DevOps Engineers."
datePublished: Wed Aug 23 2023 19:57:01 GMT+0000 (Coordinated Universal Time)
cuid: cllo5ov8q000q09mo9tfs0t0i
slug: jenkins-freestyle-project-for-devops-engineers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1692820116522/ca018ba6-400e-4428-bd07-ada092f3d3d1.jpeg
tags: docker, jenkins, ci-cd, docker-images, jenkins-devops

---

## ⚡Introduction

In the previous blog post on Day 22, we learned about Jenkins, CI/CD concepts, and how to install Jenkins.

Now, let's break down what Continuous Integration (CI) and Continuous Delivery (CD) mean.

Imagine CI as teamwork for developers' code. It automatically puts their code together and checks it.

CD ensures that changes in the code are given to customers without mistakes. Both CI and CD help create better software more quickly.

Think of a "Build Job" as a set of instructions for making software. Jenkins assists with different types of these jobs, like freestyle projects, which are flexible and powerful.

So, a Jenkins Freestyle Project is like a toolbox. It helps you build, test, and release software in different ways. Today, we'll dive deep into what you can do with it. Excited to learn? Let's get started! 🛠️

## 🔄What is CI/CD?

CI, or Continuous Integration, is like automatically putting together code changes from different developers into one single codebase.

In software development, developers often add their work to a main code place, like GitHub.

Special tools then build the new code and do important tasks like checking the code.

Continuous Integration aims to find and fix problems quickly, make it easy for developers to add their code together, make software better, and release new features faster.

**CD, or Continuous Delivery**, comes after Continuous Integration. It makes sure that changes are given to customers quickly and without mistakes.

This includes testing the changes in a place that's very similar to where the final product will be (like a practice run) to catch any problems before the real release.

Automation is really important here. It makes sure the product is always ready to be released. This way, the software can be put out whenever needed, with a big focus on being efficient and correct.

## 🏗️What Is a Build Job?

A Jenkins build job is a set of instructions that automates a specific task in making software. These tasks can be things like gathering what's needed, turning code into something that works, saving important stuff, changing code, checking if everything works, and putting code in different places.

Jenkins has different types of build jobs to do different things:

1. **Freestyle Projects**: These projects are flexible. They help with simpler tasks or projects.
    
2. **Pipelines:** Pipelines do more complex stuff. They help with making plans for the work using special instructions.
    
3. **Multi-Configuration Projects:** These projects are for testing on different setups, like different computer systems.
    
4. **Folders:** Folders help keep things organized, especially for big projects.
    
5. **Multibranch Pipelines:** This type is used when dealing with different versions of the code, making plans for each version.
    
6. **Organization Folders:** These are good for keeping track of many projects in a big group.
    

Basically, Jenkins builds jobs to help make software automatically. They help developers do things without repeating the same steps, and they make sure the results are always good. Depending on what a project needs, there are different types of build jobs to choose from. This helps teams work better, faster, and with high-quality software.

## 📝What is Freestyle Project?

A Freestyle Project in Jenkins is a way to build, test, and release software using different setups. It's like a toolbox that lets you create workflows for specific needs. It can do various tasks related to making software.

For example, in a Freestyle Project in Jenkins, you can:

1. **Compile Code**: Change the code into something that works.
    
2. **Run Tests**: Test the code to see if it works well.
    
3. **Save Important Stuff**: Keep important files safe for later.
    
4. **Use External Tools**: Work with other tools and services.
    

Freestyle Projects are versatile. They let developers make workflows, use different tools, and do different tasks based on what the project needs. Whether it's turning code into something that works or releasing software, a Freestyle Project in Jenkins helps create a personalized plan that matches what the project requires.

So now you're all set to start doing things with a freestyle project in Jenkins!

# **Task 1 :**

Let's create a freestyle project todo app in node js which will create an image

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691466300508/b753288f-ea23-48f7-9a52-c57a781f75b7.png?auto=compress,format&format=webp align="left")

clone of the git hub repo of that project

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691552550863/26358026-bc70-4424-b2cb-eda9d49643cd.png?auto=compress,format&format=webp align="left")

Now let's build docker steps

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691552708306/4c8ca976-8fff-47de-a3b0-211a321926ee.png?auto=compress,format&format=webp align="left")

Click on the "Save" button to save the project configuration.

Build the project: You can manually build the project by clicking on the "Build Now" link on the project's main page. This will start the build process and execute the steps specified in the project configuration.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">..........</div>
</div>

## **Task-02**

**Create a Jenkins project to run the "docker-compose up -d" command to start the multiple containers defined in the compose file**

**Set up a cleanup step in the Jenkins project to run the "docker-compose down" command to stop and remove the containers defined in the compose file.**

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">.........</div>
</div>

## 👏Conclusion

To sum it all up, our journey through the world of DevOps and Jenkins has highlighted how important it is to use automation and integration in making software.

We've learned about Jenkins Freestyle Projects and how they're connected with Docker. These tools help us work better and have more control. We've also seen how Continuous Integration and Continuous Delivery are useful for finding mistakes quickly and releasing software smoothly.

Jenkins has different ways to automate tasks, like freestyle projects and pipelines. Docker helps us make deployment and management easier, especially when we use Docker Compose.

When we bring together Jenkins, automation, and Docker, we give DevOps engineers the power to come up with new ideas, speed up work, and create really good software. This connection is like a strong base that helps us work well in the fast-changing world of technology.

Thanks a lot for reading this blog. I hope you got useful and interesting information from it. To stay updated with my latest thoughts and articles about DevOps 🚀, just follow me on: