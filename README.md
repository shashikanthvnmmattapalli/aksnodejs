## Overview
This sample shows you how to run a simple Node.js and mongoDB app on Kubernetes using Minikube.

![Kubernetes Relationships](doc/images/kubernetes-relationships.png)


## Please follow below steps to build your app
##### [Install Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

- To check if virtualization is supported on macOS, run the following command on your terminal. 

`sysctl -a | grep -E --color 'machdep.cpu.features|VMX'`

##### [Hypervisor Setup for HyperKit ](https://minikube.sigs.k8s.io/docs/start/macos/)

- To work with the Docker daemon on your Mac/Linux host, use the docker-env command in your shell:

`eval $(minikube docker-env)`

- Minikube start

Start a cluster using the hyperkit driver:

`minikube start --vm-driver=hyperkit`

To make hyperkit the default driver:

`minikube config set vm-driver hyperkit`


`minikube start`

- Prepare Dockerfile

- Build image

`docker build -t <your username>/<image name>:<ver> .`


- Deployment mongo

`kubectl create -f pod-nodejs-mongo.yaml`


- Deployment your app

`kubectl create -f pod-nodejs.yaml`


- View the Deployment

`kubectl get deployments`

- View the Pod:

`kubectl get pods`

- Check your service is running now

`kubectl get service`

- Show your service url

`minikube service <image name> --url`
 

- Show kubernetes dashboard

`minikube dashboard`
