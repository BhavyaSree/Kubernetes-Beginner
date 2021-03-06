---
title: Introduction
---

## What is Kubernetes?

Kubernetes is a open-source container orchestration system for automating application development, scaling and management.

## What are Containers?

Docker deliver softwares in packages called Containers.   
Containers are isolated from one another and bundle their own software, libraries and configuration files.  

Container are isolated environments, they will have their own processes or services, own networks.

## What is Docker??

Docker is a container management system.
The main purpose of docker is to containarize the applications, ship them and run them.

!!! Note
    "We cannot run windows based container on a docker host with a linux based OS on it."   
    "To run windows based container, we need to have a docker on the windows server." 

Unlike virtual machines, docker is not meant to virtualize and run different operation systems on the same hardware.

## Containers vs Virtual Machines

* Each virtual machine will have its own operating system inside it.
  This causes higher utilization of underlying resources as they have multiple virtual operationg system running.  
  Docker containers won't be having separate OS.
* Virtual Machines also consumes higher disk space usually in GBs, whereas   docker containers are light weight usually size in MBs.
* Virtual machines takes minutes to bootup(because of size), whereas containers bootup in seconds.
* Docker has less isolation as more resources are shared between the containers(OS), whereas VMs have complete isolation from the kernel. Since VMs don't rely on underlying OS, we can have different OS on the virtual machine.

## Container vs Image

* Image is a template which is used to create one or more containers.
* Containers are running instances of images that are isolated with their own environment and set of processes.

## Container Orchestration

The process of automatically deploying and managing conatiners(scaling) is known as container orchestration.

Kubernets is one of the container Orchestration Technology.

## Kubernetes Advantage

* With conatiner orchestration, application is now highly available as hardware failures do not bring application down as we have multiple instances of application is running on different nodes.
* The user traffic is load balanced across various container, as the demand increases deploy more instances of application within seconds.

!!! Note
    "kubernetes is a container orchestration technology, used to orchestrate the deployment and management of hundreds and thousands of containers in a clustered environment."

A cluster is a group of multiple server instances, spanning across morethan one node,all running identical configuration.

## Kubernetes Architecture

### Node
A Node is a machine (physical or virtual) on which kubernetes is installed.  
A Node is a worker machine on which conatiners will be launced by kubernetes.  
If the node on which application running fails, the application goes down.
Therefore, we need to have morethan one node(there comes the cluster concept).

### Cluster
A cluster is a set of nodes grouped together, this way if one node fails, application is still accessable from the other nodes.  
Having multiple nodes help in sharing load as well.

### Master
Master is an another node with kubernetes installed in it and configured as a master.  
Master watches over the nodes in the cluster and is responsible for the actual orchestration of containers on the worker nodes.

### Components
When we install Kubernetes on the system, we actually install the following components. 

* API Server
* etcd service
* kubelet service
* Container Runtime
* Controllers
* Schedulers

API Server acts as the frontend for kubernetes. The users, management devices, command line interfaces all talk to the API servers to interact with kubernetes cluster.

etcd is a distributed key value store used by kubernetes to store all the data used to manage the cluster.

Scheduler is responsible for distributing work or container across multiple nodes. It looks for newly created containers and assigns them to nodes.

Controllers are the brain behind orchestration, they are responsible for noticing and responding when the nodes, containers or end points goes down.  
Controllers make decisions to bringup new containers in such cases.  

Container Runtime is the underlying software that is used to run containers, in our case it will be docker.

Kubelet is the agent that runs in the each node of the cluster. The agent is responsible for making sure that the containers are running on the nodes as expected.

## Master vs Worker Nodes

* Worker Node or Minion is where the containers are hosted. To run containers on the system, we need container runtime installed. Therefore, worker nodes will have container runtime (docker).
* Master node will have Kube-API server and thats make it a master.
* Worker node will have kubelet agent that is responsible to interact with the master to provide health information of the worker node and to carry out actions requested by the master on the worker nodes.
* All the information gathered is stored in the key-value store on the master. The key-value store is based on the popular etcd framework.
* The master also has Controller and Scheduler.

## Kubectl

Kubectl tool is used to deploy and manage application on kubernetes cluster like to get the cluster information, to get status of nodes and to manage many other things.

`kubectl run hello-minikube`  
kubetcl command is to deploy application on the cluster.  

`kubectl cluster-info`  
To view information about the cluster.  

`kubectl get nodes`   
To list all the nodes of the cluster.












