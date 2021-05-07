# Kubernetes
	
## Introduction

* Open-source orchestration system for docker containers
* Implemented by google.
* Removes manual process of deploying containerized application.
* K8 is used to manage state of containers.
	
	

# Challenges without orchestration
	
* Increase human cost of running a service.
* Increase complexity of Infrastructure.
* Scaling was very difficult.
* Setting up services manually.
* Manual Fix if any node is crashes.

# Features of K8

* Automated Scheduling 
	* Kubernetes provides advanced scheduler to launch container on cluster nodes based on their resource requirements and other constraints. 

* Healing Capabilities
	* Kubernetes replaces and reschedules containers when nodes die. Kubernetes doesn’t allow using containers, until they are ready.
	
* Auto Upgrade and RollBack
	* Kubernetes rolls out changes to the application or its configuration.
	* Monitoring Application ensure that Kubernetes doesn’t kill all Instance at once.If something goes wrong, with Kubernetes you can rollback the change

* Horizontal Scaling
	* : Kubernetes can scale up and scale down the application as per the requirements with a simple command, using a UI, or automatically based on CPU usage.

* Storage Orchestration
	* With Kubernetes, you can mount the storage system of your choice. You can either opt for local storage, or choose a public cloud provider.

* Secret & Configuration Management
	*  Kubernetes can help you deploy and update secrets and application configuration without rebuilding your image and without exposing secrets in your stack configuration .
	
* You can Run Kubernetes Anywhere
	* On-Premise(Own DataCenter)
	* Public Cloud(Google, AWS, Azure, DigitalOcean…)
	* Hybrid Cloud