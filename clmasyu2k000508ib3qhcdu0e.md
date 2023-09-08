---
title: "Day 34 Task: Working with Services in Kubernetes"
datePublished: Fri Sep 08 2023 16:19:33 GMT+0000 (Coordinated Universal Time)
cuid: clmasyu2k000508ib3qhcdu0e
slug: day-34-task-working-with-services-in-kubernetes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1694189883157/73ecbcf5-7287-44b0-91cf-c3b9e9992e00.png
tags: docker, kubernetes, devops, 90daysofdevops, trainwithshubham

---

## **Services in Kubernetes**

The Kubernetes Service API simplifies the process of exposing groups of Pods over a network. Each Service defines a logical set of endpoints, typically represented by Pods, and specifies how to make those Pods accessible.

For instance, consider a stateless image-processing backend with 3 replicas. The frontend clients don't need to be aware of the specific backend Pods; the Service abstraction decouples them. You can define the set of Pods targeted by a Service using a selector.

If your workload uses HTTP, Ingress can control web traffic access. While not a Service type, Ingress serves as the entry point for your cluster, allowing you to consolidate routing rules for multiple workload components running separately.

Beyond Ingress and Service, Kubernetes offers the Gateway API, which extends capabilities for configuring network service access in your cluster. You can add Gateway to your cluster using CustomResourceDefinitions to configure these services.

## **Service Types in Kubernetes**

Kubernetes supports four types of services, each with a different purpose:

1. <mark>ClusterIP</mark>: This is the default service type in Kubernetes. It provides a stable IP address and DNS name for accessing pods within the cluster. The ClusterIP service is only accessible from within the cluster.
    
2. <mark>NodePort</mark>: This service type exposes the service on a static port on each node in the cluster. It provides a way to access the service from outside the cluster.
    
3. <mark>LoadBalancer</mark>: This service type provides a load balancer for the service in cloud environments that support load balancers. It automatically creates a load balancer and assigns a public IP address to the service.
    
4. <mark>ExternalName</mark>: This service type provides a way to access an external service by creating a DNS CNAME record. It does not create any endpoints or perform any load balancing.
    

## **Task 1: Create a Service for your todo-app Deployment**

1. **Create a Service definition YAML file:** Begin by creating a YAML file named `service.yml` to define your Service for the `todo-app` Deployment.
    
    ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: todo-app-deployment
       namespace: todo-app
     spec:
       type: NodePort
       selector:
         app: todo-app
       ports:
         - port: 80
           targetPort: 8000
    ```
    
    1. **Apply the Service definition:** Execute the following command to apply the Service definition to your Kubernetes cluster.
        
    
    Don't forget to replace `<namespace-name>` with the actual namespace where your `todo-app` Deployment resides.
    
    ```yaml
     kubectl apply -f service.yml -n <namespace-name>
    ```
    
    1. **Verification:** To ensure that the Service is working correctly, access the `todo-app` using the Service's IP and Port within your specified Namespace.
        
    
    ```yaml
     kubectl get svc -n <namespace-name>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693999968989/9f405237-4dec-414a-a18a-72fb1fe20654.png?auto=compress,format&format=webp align="left")
    

## **Task 2: Create a ClusterIP Service for accessing the todo-app within the cluster**

**Create a ClusterIP Service definition YAML file:** Now, create another YAML file named `cluster-ip-service.yml` to define a ClusterIP Service for your `todo-app` Deployment.

```yaml
 apiVersion: v1
 kind: Service
 metadata:
   name: todo-app-clusterip
   labels:
     app: todo-app
 spec:
   selector:
     app: todo-app
   ports:
     - protocol: TCP
       port: 8000
       targetPort: 8080
   type: ClusterIP
```

1. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000037008/e973ed2d-279b-483f-8bda-1ae9815d9971.png?auto=compress,format&format=webp align="left")
    
2. **Apply the ClusterIP Service definition:** Use the following command to apply the ClusterIP Service definition to your Kubernetes cluster within the specified namespace.
    
    ```basic
     kubectl apply -f cluster-ip-service.yml -n <namespace-name>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000140923/c03b5135-e149-4f63-8979-dcb8c550d447.png?auto=compress,format&format=webp align="left")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000434076/993aa950-18de-4639-9209-c980ee0c838c.png?auto=compress,format&format=webp align="left")
    
3. **Verification:** To confirm that the ClusterIP Service is functioning correctly, access the `todo-app` from another Pod within the cluster, still in your specified Namespace.
    
    Create a YAML file named `test-pod.yml` for a testing pod:
    
    ```yaml
     apiVersion: v1
     kind: Pod
     metadata:
       name: test-pod
     spec:
       containers:
         - name: busybox
           image: busybox
           command: ['sh', '-c', 'while true; do wget -q -O- clusterip:8000; done']'
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000603113/81b845de-2532-4b62-be69-de497ef14447.png?auto=compress,format&format=webp align="left")
    
    Apply the ClusterIP Service definition to your K8s cluster using the command & verify todo-app is running
    
    ```yaml
     kubectl apply -f test-pod.yml -n <namespace-name>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694000697659/5b5e2d5c-7f31-4c9f-9e4d-3df036fe1396.png?auto=compress,format&format=webp align="left")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694004467827/8fe0946f-90de-4b32-8068-001640295724.png?auto=compress,format&format=webp align="left")
    

## **Tsk 3: Create a LoadBalancer Service for accessing the todo-app from outside the cluster**

1. **Create a LoadBalancer Service definition YAML file:** Create a YAML file named `load-balancer-service.yml` to define a LoadBalancer Service for your `todo-app` Deployment.
    
    w you can do it:
    
    ```yaml
     apiVersion: v1
     kind: Service
     metadata:
       name: todo-app-loadbalancer
     spec:
       selector:
         app: todo-app
       ports:
         - protocol: TCP
           port: 80
           targetPort: 8000
       type: LoadBalancer
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694004574029/1339d4ad-9ebd-4c63-a977-3d9e5d941104.png?auto=compress,format&format=webp align="left")
    
2. **Apply the LoadBalancer Service definition:** Apply the LoadBalancer Service definition to your Kubernetes cluster within the specified namespace using the following command:
    
    ```yaml
     kubectl apply -f load-balancer-service.yml -n <namespace-name>
    ```
    
3. **Verification:** To verify the functionality of the LoadBalancer Service, access the `todo-app` from outside the cluster, within your specified Namespace with the command:
    
    ```yaml
     kubectl get svc -n <namespace-name>
    ```
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1694004685439/674dede3-782f-49da-bad1-ec70aadf4d6d.png?auto=compress,format&format=webp align="left")
    

# **Conclusion**

Today, you've acquired essential skills in managing Kubernetes Services, a critical component for establishing dependable network communication within your cluster. Through these practical tasks, you've honed your abilities in both creating and setting up various Service types like ClusterIP and LoadBalancer. This expertise will serve as a valuable asset as you progress further in your Kubernetes exploration.