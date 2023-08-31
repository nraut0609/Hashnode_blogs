---
title: "Jenkins Declarative Pipeline:- An Overview"
datePublished: Wed Aug 30 2023 10:48:02 GMT+0000 (Coordinated Universal Time)
cuid: cllxm5u6b000e09moh0j87jlu
slug: jenkins-declarative-pipeline-an-overview
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693392408613/858415b8-925d-4f22-b3d0-f1be2f7bce08.png
tags: devops, jenkins, jenkins-devops, trainwithshubham, jenkins-pipeline

---

## 👉 What is a Pipeline?

🚀 A pipeline is like a software journey 🛤️, moving from development to deployment. It automagically guides the process, making software sparkle with continuous integration ⚙️, testing 🧪, and smooth delivery 🚚. It's like a GPS 🗺️ for error-free, efficient software crafting and launching.

### 🤖 What's a Declarative Pipeline?

📝 Declarative is like the CliffsNotes 📖 of pipeline scripts. Instead of listing every single step, you just tell it what you want 🧞. Jenkins does the rest, making things simpler to grasp and maintain, without fussing about the tiny details. 🧐

### 💻 What about Scripted Pipeline?

📜 Scripted is the old-school pipeline wizardry 🔮, where developers spell out each step like a magical incantation. More power, more control, but it's like using an ancient spellbook 📜. Developers need to define it all, so it's heavier on code ⌨️ and trickier to keep polished compared to the declarative magic.

### 🌟 Why should you wield a Pipeline?

⏩ Having a pipeline is like having a personal assistant 🧞 for software. It automates everything, keeping deliveries smooth and consistent 🏎️. It vanishes manual blunders, makes testing a breeze, and lets integration and deployment flow like a river 🌊. A pipeline saves time ⏳, supercharges productivity 🚀, and turns out software that's as solid as a rock.

### 📜🤖 What's a Jenkins Pipeline, anyway?

Imagine the definition of a Jenkins Pipeline as a text love letter 💌 (aka Jenkinsfile) that you tuck into your project's code treasure chest. It's like treating the CD pipeline as a VIP club 🎉, where it's versioned and pampered with reviews like any other precious code. 💎

🚧 Making a Jenkinsfile and hugging it 🤗 (into source control) brings perks! 🌟 Instantly crafts a pipeline-building spree for all branches and pull requests. 🌟 Code gossip and tinkering with the Pipeline (and the rest of the code gang).

```bash
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Commands for building your code
                echo 'Building the code...'
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                // Commands for testing your code
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                // Commands for deploying your application
                echo 'Deploying the application...'
                sh './deploy_script.sh'
            }
        }
    }
}
```

Let's break down the syntax step by step:

1. `pipeline`: This is the start of the declarative pipeline definition. It indicates that you're defining a pipeline for your CI/CD process.
    
2. `agent any`: This specifies that the pipeline can be executed on any available agent/node. An agent/node is a machine or environment where the pipeline stages will be executed. `any` means Jenkins will allocate any available agent for this pipeline.
    
3. `stages`: This is where you define the different stages of your CI/CD process. Stages are individual steps that your code goes through during the pipeline execution.
    
    * `stage('Build')`: This defines the "Build" stage. In this stage, you typically perform tasks like compiling your source code, creating artifacts, and preparing your application for testing.
        
        * `steps`: This is where you define the actual tasks to be executed within the "Build" stage. It could include commands for compiling code, running lines, setting up dependencies, etc.
            
    * `stage('Test')`: This defines the "Test" stage. Here, you conduct various tests on your built artifacts to ensure the code functions correctly.
        
        * `steps`: Similar to the "Build" stage, this is where you define commands to run your tests, generate reports, and assess code quality.
            
    * `stage('Deploy')`: This defines the "Deploy" stage. In this stage, you deploy your application to a specific environment, such as a production server or a staging environment.
        
        * `steps`: Here, you might have commands to deploy your application, configure servers, set up databases, and perform any other necessary tasks for deployment.
            

**Note**: Each `stage` block contains `steps`, which represent the specific actions to be performed in that stage.

The actual commands or scripts you provide within the `steps` block will depend on your project's requirements and technology stack.

## **Task-01:Create a New Job using Pipeline Hello World Example**

This example demonstrates the basic process of creating and executing a pipeline in Jenkins. Here's a more detailed breakdown of each step:

**Step 1: Navigate to the Jenkins Home Page and Create a New Job**

1. Open a web browser and navigate to the Jenkins home page.
    
2. Log in if required.
    
3. Click on "New Item" to create a new job.
    
4. Give a job a name and select "Pipeline" as the job type.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693391416002/7430a7b7-0c73-4b76-a50e-e08d32301c0d.png align="center")
    
5. Click "OK" to create the job.
    

**Step 2: Configure the Project with a Valid Description**

1. In the job configuration page, scroll up to the top section where we can edit the job's details.
    
2. Add a valid description for the project.
    
3. Save the changes.
    

**Step 3: Follow the Official Jenkins** [**Hello World Example**](https://www.jenkins.io/doc/pipeline/tour/hello-world/)

1. In the configuration page of the new job, scroll down to the "Pipeline" section.
    
2. Select the "Pipeline script" option.
    
3. Choose the "Pipeline script from SCM" option and provide the necessary repository details. (In this case, you're following the "Hello World" example, so you might choose to use a simple script or select Hello World or a Jenkinsfile in your repository.
    
    ```bash
      pipeline {
          agent any
          stages {
              stage('Build') {
                  steps {
                      echo 'Hello World'
                  }
              }
          }
      }
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692262933741/17bfe4af-a3a7-4b97-b351-208f8ec96c66.png?auto=compress,format&format=webp align="left")
    
4. Save the changes.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692263052567/3a2c8818-e3f9-4d72-b26c-5c543a4982c7.png?auto=compress,format&format=webp align="left")
    

**Step 4: Click on Save and Then Build Now**

1. After saving our pipeline configuration, we can manually trigger a build by clicking "Build Now." This will initiate the pipeline execution based on the code we've written.
    

**Step 5: Check the Full Stage View for Execution Time**

1. Once the pipeline execution starts, we can navigate to the "Full Stage View" to see the different stages of our pipeline and the time it takes for each stage to complete.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692263405575/86484fcc-cb44-4727-95fe-95318a898c8d.png?auto=compress,format&format=webp align="left")
    

**Step6: Verify Hello World Using Console Output**

1. After the pipeline has been completed, we can check the "Console Output" to see the detailed logs of each step's execution.
    
2. If everything went as expected, we should see a "Success" status in the console output, indicating that the "Hello World" pipeline was executed successfully.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692528279933/b09d0ac5-d1a6-48d4-8664-f1cfbc6e6240.png?auto=compress,format&format=webp align="left")