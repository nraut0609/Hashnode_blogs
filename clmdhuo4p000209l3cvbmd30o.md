---
title: "Day 35: Mastering ConfigMaps and Secrets in Kubernetes🔒🔑🛡️"
datePublished: Sun Sep 10 2023 13:31:42 GMT+0000 (Coordinated Universal Time)
cuid: clmdhuo4p000209l3cvbmd30o
slug: day-35-mastering-configmaps-and-secrets-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694352589651/ff26032f-72ab-4eed-ba77-8a25a7f0c435.png
tags: docker, kubernetes, devops, devops-articles, trainwithshubham

---

## What are ConfigMaps and Secrets in k8s In Kubernetes

ConfigMaps and Secrets are used to store configuration data and secrets, respectively. ConfigMaps store configuration data as key-value pairs, while Secrets store sensitive data in an encrypted form.

*<mark>Example</mark> :-*

1. *Imagine you're in charge of a big spaceship (Kubernetes cluster) with lots of different parts (containers) that need information to function properly. ConfigMaps are like a file cabinet where you store all the information each part needs in simple, labeled folders (key-value pairs).*
    
2. *Secrets, on the other hand, are like a safe where you keep the important, sensitive information that shouldn't be accessible to just anyone (encrypted data). So, using ConfigMaps and Secrets, you can ensure each part of your spaceship (Kubernetes cluster) has the information it needs to work properly and keep sensitive information secure! 🚀*
    

## Task 1: Create a ConfigMap for your Deployment

Create a ConfigMap for your Deployment using the command line. Update the deployment.yml file to include the ConfigMap . Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n todo-namespace` . Verify that the ConfigMap has been created by checking the status of the ConfigMaps in your Namespace.

***Steps to create a ConfigMap for your Deployment:***

1. Create a ConfigMap using the `kubectl create configmap` command. Here's an example:
    
    ```yaml
     kubectl create configmap todo-config --from-literal=database_host=localhost --from-literal=database_port=5432 -n todo-namespace
    ```
    
    This command creates a ConfigMap named `todo-config` in the `todo-namespace` namespace with two key-value pairs: `database_host` and `database_port`.
    
2. Update your Deployment YAML file to include the ConfigMap. Here's an example:
    
    ```yaml
     apiVersion: apps/v1
     kind: Deployment
     metadata:
       name: todo-deployment
       labels:
         app: todo-app
     spec:
       replicas: 1
       selector:
         matchLabels:
           app: todo-app
       template:
         metadata:
           labels:
             app: todo-app
         spec:
           containers:
             - name: todo-app
               image: my-todo-app
               ports:
                 - containerPort: 8000
               env:
                 - name: DATABASE_HOST
                   valueFrom:
                     configMapKeyRef:
                       name: todo-config
                       key: database_host
                 - name: DATABASE_PORT
                   valueFrom:
                     configMapKeyRef:
                       name: todo-config
                       key: database_port
    ```
    
    In this example, the `env` section of the container specifies two environment variables that are sourced from the `todo-config` ConfigMap. The `valueFrom` field specifies that the values should be taken from the ConfigMap's `database_host` and `database_port` keys.
    
3. Apply the updated Deployment using the `kubectl apply` command:
    
    ```basic
     kubectl apply -f deployment.yml -n todo-namespace
    ```
    
    This command applies the updated Deployment YAML file to your K8s cluster.
    
4. Verify that the ConfigMap has been created by checking the status of the ConfigMaps in your Namespace:
    
    ```basic
     kubectl get configmaps -n todo-namespace
    ```
    
    This command lists all the ConfigMaps in the `todo-namespace` namespace. You should see a `todo-config` ConfigMap listed. You can also inspect the ConfigMap by running `kubectl describe configmap todo-config -n todo-namespace`.
    

## Task 2: Create a Secret for your Deployment

Create a Secret for your Deployment using a file or the command line. Update the deployment.yml file to include the Secret. Apply the updated deployment using the command: `kubectl apply -f deployment.yml -n todo-namespace.` Verify that the Secret has been created by checking the status of the Secrets in your Namespace.

To create a Secret for your Deployment using the command line, you can follow these steps:

1. Create a file containing the secret data in key-value format. For example, create a file named `db-secret.txt` with the following content:
    
    ```basic
     username=mydbuser
     password=mydbpassword
    ```
    
2. Create a Secret using the `kubectl create secret generic` command and specify the file as the source of the secret data:
    
    ```bash
     kubectl create secret generic db-secret --from-file=db-secret.txt -n todo-namespace
    ```
    
    This will create a Secret named `db-secret` in the `todo-namespace` Namespace, with the contents of the `db-secret.txt` file stored as key-value pairs.
    
3. Update the `deployment.yml` file to include the Secret. You can add a `volume` and a `volumeMount` section to the Deployment definition, like this:
    
    ```yaml
     spec:
       containers:
       - name: todo-app
         image: <image-name>
         volumeMounts:
         - name: db-secret-volume
           mountPath: /etc/secret-volume
           readOnly: true
       volumes:
       - name: db-secret-volume
         secret:
           secretName: db-secret
    ```
    
    This will mount the contents of the `db-secret` Secret to the `/etc/secret-volume` directory inside the container.
    
4. Apply the updated deployment using the `kubectl apply` command:
    
    ```yaml
     kubectl apply -f deployment.yml -n todo-namespace
    ```
    
5. Verify that the Secret has been created by checking the status of the Secrets in your Namespace:
    
    ```yaml
     kubectl get secrets -n todo-namespace
    ```
    
    You should see the `db-secret` Secret listed among the other Secrets in the Namespace.
    

## Conclusion

ConfigMaps and Secrets play pivotal roles in overseeing application configurations and safeguarding sensitive data within a Kubernetes framework. ConfigMaps facilitate the administration of configuration details like environment variables, command-line arguments, and configuration files. On the flip side, Secrets serve as secure repositories for confidential information such as passwords, API keys, and various credentials.

Throughout this tutorial, we have guided you through the procedure of crafting and utilizing ConfigMaps and Secrets in a Kubernetes environment. We initiated the creation of ConfigMaps and Secrets through command-line instructions, integrated them into our Deployment definitions, and implemented these alterations in our Kubernetes cluster.

Having followed the steps delineated in this tutorial, you should now possess a more comprehensive grasp of the methods for managing your application configurations and safeguarding your secrets within a Kubernetes context. Regardless of whether you're a novice or a seasoned Kubernetes practitioner, ConfigMaps and Secrets stand as robust instruments that streamline the administration of your applications.