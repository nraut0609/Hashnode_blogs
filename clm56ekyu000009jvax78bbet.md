---
title: "Day: 31 Launching your First Kubernetes Cluster with Nginx running"
datePublished: Mon Sep 04 2023 17:49:06 GMT+0000 (Coordinated Universal Time)
cuid: clm56ekyu000009jvax78bbet
slug: day-31-launching-your-first-kubernetes-cluster-with-nginx-running
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693849541499/413b2f86-532e-4291-a766-19b8af88083c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1693849739414/e94a3f66-1a37-4f4f-af54-3f79f7b90d56.png
tags: docker, kubernetes, devops, containers, trainwithshubham

---

### **What is minikube?**

Before, we discussed the many Kubernetes parts that go into creating a master and worker node, including the API server, etcd key-value store, controllers, and scheduler on the master, and kubelets and container runtime on the worker nodes. Setting up and installing these components on different systems individually would require a lot of time and work.

Minikube combines all these various parts into a single image and offers us a single-node Kubernetes cluster that is already configured, allowing us to get going quickly.

The entire program is bundled into an ISO image and may be downloaded online.

### **Understanding Minikube: A Closer Look**

Minikube emerges as a lightweight and open-source solution that empowers developers to establish a singular-node Kubernetes cluster right on their local machines. This ingenious tool is tailored for streamlining local application testing and development within the Kubernetes framework, eliminating the need for complex cluster setups.

### **The functionality of minikube:**

* Easy-to-install Kubernetes application add-ons
    
* enables typical CI scenarios
    
* Supports the most recent Kubernetes release (+6 previous minor versions)
    
* Cross-platform (Linux, macOS, Windows)
    
* Direct API endpoint for blazing-fast image load and build
    

and many more.

### **Features of minikube**

(a) Supports the latest Kubernetes release (+6 previous minor versions)

(b) Cross-platform (Linux, macOS, Windows)

(c) Deploy as a VM, a container, or on bare-metal

(d) Multiple container runtimes (CRI-O, containers, docker)

(e) Direct API endpoint for blazing-fast image load and build

(f) Advanced features such as LoadBalancer, filesystem mounts, FeatureGates, and network policy

(g) Addons for easily installed Kubernetes applications

(h) Supports common CI environments

## **Task-01:**

[**Install minikube on your local**](https://minikube.sigs.k8s.io/docs/start/)

Launch EC2 instance with Instance type as “**t2.medium**”.

* CPU: 2
    
* Memory: 4GB
    
* Disk Space: more than 10GB
    
    <mark>Install docker </mark> using commands such as “`sudo apt-get update`” and “`sudo apt-get install` [`docker.io`](http://docker.io)**”.**
    
    ```bash
    sudo usermod -aG docker $USER 
    sudo systemctl start docker
    sudo systemctl enable docker
    ```
    
    ```bash
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    ```
    
    After running the CURL command you will see the Minikube folder
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692932462371/61a6be53-d741-4466-a418-9c86848cfa75.png?auto=compress,format&format=webp align="left")
    
    Download the Minikube binary using `curl` Make it executable and move it into your path:
    
    ```bash
     chmod +x minikube
     sudo mv minikube /usr/local/bin/
    ```
    

To check the version of miniKube -- add below command

```bash
minikube version
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692932671335/a9e18b00-7601-4f9a-bca5-75ceabf5f5d7.png?auto=compress,format&format=webp align="left")

To confirm successful installation of both a hypervisor and Minikube, you can run the following command to start up a local Kubernetes cluster:

Now lets install kubectl which is command line tool

```bash
 curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692932799684/4295b924-1ac8-45b0-a94b-1f3485e433de.png?auto=compress,format&format=webp align="left")

Make it executable and move it into your path

```bash
 chmod +x kubectl
 sudo mv kubectl /usr/local/bin/
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692932849762/511cdec7-5523-4e87-a808-74996b361d81.png?auto=compress,format&format=webp align="left")

**Activating Minikube and Checking Status**

minikube start --driver=docker

In below image, we used driver\_name=docker, so first you need to install docker in your machine.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692932246553/cbb67972-085d-4865-a138-b94971ec3031.png?auto=compress,format&format=webp align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933006460/a7c7197a-fb2f-49e0-a5de-61289b6e22cf.png?auto=compress,format&format=webp align="left")

Once minikube start finishes, run the command below to check the status of the cluster:

```bash
minikube status
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933111601/9d1b61dc-7aeb-4bc0-858b-b4bb43a6272d.png?auto=compress,format&format=webp align="left")

If you have previously installed Minikube, and run:

```bash
minikube start
```

and minikube start returned an error: **<mark>machine does not exist</mark>**

then you need to clear minikube local state:

```bash
minikube delete
```

For log in to minikube use command:

```bash
minikube ssh
```

### **Pod:**

Pods are the smallest deployable units of computing that you can create and manage in Kubernetes.

A Pod (as in a pod of whales or pea pod) is a group of one or more containers, with shared storage and network resources, and a specification for how to run the containers. A Pod's contents are always co-located and co-scheduled and run in a shared context. A Pod models an application-specific "logical host": it contains one or more application containers that are relatively tightly coupled.

## **Task-02:**

**Create your first pod on Kubernetes through minikube.**

Install kubectl using command

```bash
sudo snap install kubectl --classic
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933313225/28913ffa-58f0-4d5a-a5e1-55b1c9e4a814.png?auto=compress,format&format=webp align="left")

Create a file, inside folder create pod.yaml file for nginx.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
# After creating this file , run below command:
# kubectl apply -f <yaml file name>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933907961/35d0af4d-18aa-45f8-b2ef-43da5934e2c3.png?auto=compress,format&format=webp align="left")

To create a pod using pod.yaml file use below command:

```bash
tl apply -f <pod.yaml>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933963581/9614fc3c-ce69-4fcd-ac38-5a02af1b438a.png?auto=compress,format&format=webp align="left")

To check list of pods:

```bash
kubectl get pods
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692933998484/d75e71c2-5003-4a3e-a744-b52e8e205981.png?auto=compress,format&format=webp align="left")

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Great job! Minikube has been successfully installed on your Ubuntu system, and you're ready to begin deploying Kubernetes applications for development and testing. <strong>🚀 Stay tuned for more insightful Kubernetes blogs in the days ahead! 🎉</strong></div>
</div>