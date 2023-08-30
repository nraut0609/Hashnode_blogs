---
title: "Day 30 Task: It is all about Kubernetes with Architecture"
datePublished: Wed Aug 30 2023 19:45:31 GMT+0000 (Coordinated Universal Time)
cuid: clly5d1et000a09l53c2p2kqk
slug: day-30-task-it-is-all-about-kubernetes-with-architecture
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1693424617481/03f7c765-679b-462b-97c9-9a43e5d6e87c.png
tags: kubernetes, devops, devops-articles, 90daysofdevops, trainwithshubham

---

## What is Kubernetes?

Kubernetes is an open-source orchestration tool developed by Google for managing microservices or containerized applications across a distributed cluster of nodes. Kubernetes provides a highly resilient infrastructure with zero downtime deployment capabilities, automatic rollback, scaling, and self-healing of containers (which consists of auto-placement, auto-restart, auto-replication, and scaling of containers on the basis of CPU usage). Kubernetes was created from Borg & Omega projects by Google as they used it to orchestrate their data center since 2003. Google open-sourced Kubernetes in 2014

## **Advantages of Utilizing Kubernetes**

1. **Scalability:** Kubernetes facilitates the effortless scaling of applications, both horizontally and vertically, as dictated by demand. It automatically adapts the number of application instances to sustain optimal performance.
    
2. **Enhanced Availability:** Kubernetes ensures heightened availability by dispersing application instances across distinct nodes. In the event of node failures, it automatically reassigns instances, maintaining continuous operation.
    
3. **Optimized Resource Management:** Resource allocation to containers is intelligently managed, preventing resource conflicts and wastage, thereby optimizing resource utilization.
    
4. **Automated Recovery:** Kubernetes promptly identifies and replaces failed containers or nodes, guaranteeing the uninterrupted operation of your applications.
    
5. **Declarative Configuration:** You establish the intended state of your applications through configuration files. Kubernetes then consistently works to align the actual state with the desired state.
    
6. **Smooth Deployments and Reversals:** Kubernetes supports seamless updates and reversals of applications, permitting the introduction of changes without causing disruptions to the user experience.
    

**Versatility:** The functionality of Kubernetes can be expanded through a diverse array of plugins, custom resources, and APIs, fostering extensibility

## Kubernetes Components and Architecture

* **K8s Master Node:** the master server that will create the cluster and it has all the components and services that manage, plan, schedule and monitor all the worker nodes.
    
* **Worker Node:** the server that hosts the applications as Pods and containers.
    
* Can make more than the master server to make HA for the K8s components
    

**Kubernetes Master Node Components**

Below are the main components on the master node:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693422269415/c12f6e6b-6b13-4ee3-97f2-6d6455588b2c.jpeg align="center")

**API server** – is the primary management component of Kubernetes and is responsible for orchestrating all operations (scaling, updates, and so on) in the cluster. It also acts as the gateway to the cluster, so the API server must be accessible by clients from outside

**Add-ons:**

* **DNS:** all Kubernetes clusters should have cluster DNS to resolve name of the containers inside master node as all the above components is containers inside master node
    
* **Web UI:** web-based UI for Kubernetes clusters. It allows users to manage and troubleshoot applications running in the cluster, as well as the cluster itself.
    
* **Container runtime:** The container runtime is the software that is responsible for running containers. Kubernetes supports several container runtimes: Docker , containers , CRIO
    
    **Node (worker) components**
    
    Below are the main components on a (worker) node:
    
    * **kubelet** - the main service on a node, connect between Master and Node and ensuring that pods and their containers are healthy and running in the desired state. This component also reports to the master on the health of the host where it is running.
        
    * **kube-proxy** - a proxy service that runs on each worker node to deal with individual host subnetting and expose services to the external world. It performs request forwarding to the correct pods/containers across the various isolated networks in a cluster.
        
    
    **Kubectl**
    
    kubectl command is a line tool that interacts with kube-apiserver and send commands to the master node. Each command is converted into an API call.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693422968547/f8aa2ec9-ae5a-4747-ac52-aa5d7d8e96c6.jpeg align="center")
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693423006579/3efc7a67-235a-49e9-b6a6-d9499e615266.jpeg align="center")

## **Difference between kubectl and kubelet**

1. **kubectl:** kubectl stands for **Kubernetes Control**, and it is a command-line tool used for interacting with Kubernetes clusters. It serves as the primary interface for administrators, developers, and users to manage and control various aspects of the cluster and the resources within it. Some key features and functions of Kubectl include:
    
    * **Cluster Management:** kubectl enables users to create, modify, and delete Kubernetes resources such as pods, services, deployments, namespaces, and more.
        
    * **Deployment Operations:** It allows users to manage application deployments, scaling, rolling updates, and rollbacks.
        
    * **Debugging and Logging:** Users can access logs and events from pods for troubleshooting and monitoring purposes.
        
    * **Resource Inspection:** kubectl provides detailed information about resources, including their configuration, status, and other metadata.
        
    * **Port Forwarding and Proxying:** It facilitates local access to Kubernetes resources by forwarding ports or creating proxy connections.
        
    * **Resource Interactions:** Users can apply configuration files (YAML or JSON) to create or update resources, making automation and infrastructure-as-code practices possible
        
2. **kubelet**: kubelet is a core component running on each node within a Kubernetes cluster. It's responsible for maintaining the health and execution of pods on the node, ensuring that the containers specified in the pod specifications are up and running. Key responsibilities and characteristics of kubelet include:
    
    * **Pod Management:** kubelet supervises the state of pods scheduled on its node, ensuring they match the desired state as specified by the control plane.
        
    * **Container Execution:** It interacts with the container runtime (e.g., Docker, containers) to start, stop, and manage containers within pods.
        
    * **Resource Allocation:** kubelet monitors node resource utilization and enforces resource limits and requests for containers, preventing resource contention.
        
    * **Health Checks:** It periodically checks the health of containers and restarts them if they crash or become unresponsive.
        
    * **Pod Networking and Storage:** kubelet sets up networking and attaches storage volumes as required by the pod specifications.
        
    * **Node Reporting:** kubelet reports node status and health to the control plane, allowing the scheduler and other components to make informed decisions.
        

In essence, **kubectl** serves as the command-line interface for managing and interacting with the Kubernetes cluster from a centralized point. For example, to create a new deployment, you would use a command like:

```bash
kubectl create deployment my-app --image=my-container-image
```

**kubelet** operates on each node, overseeing the execution and health of containers within the pods on that node.

## **Role of the API Server**

At the heart of Kubernetes lies the API Server, assuming a pivotal role.

It serves as the conduit for the Kubernetes API, connecting disparate components with the cluster.

When engagement with the cluster occurs through Kubectl or any other client, the API server becomes the recipient of these requests.

Subsequently, the API server undertakes the validation and processing of these requests, safeguarding the consistency and precision of the cluster's state.

---

### Thank you for reading this blog! 📖 Hope you have gained some value.

Please follow me on Linkedin- [www.linkedin.com/in/nikhil-raut-965133b4](http://www.linkedin.com/in/nikhil-raut-965133b4)