### BASIC COMMANDS FOR INSTALLTION AND KUBECTL ###

### INSTALL KIND(Requires Docker Installed and Configured) ###

On Linux

curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
mv ./kind /some-dir-in-your-PATH/kind

On Mac Via HomeBrew
brew install kind

On MacOS via MacPort
sudo port selfupdate && sudo port install kind

On MacOs via Bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-darwin-amd64
chmod +x ./kind
mv ./kind /some-dir-in-your-PATH/kind

On Windows
curl.exe -Lo kind-windows-amd64.exe https://kind.sigs.k8s.io/dl/v0.11.1/kind-windows-amd64
Move-Item .\kind-windows-amd64.exe c:\some-dir-in-your-PATH\kind.exe

### CREATE KIND CLUSTER ###

kind create cluster --name NAME #can be used with out name flag (default name 'kind')
kind get cluster
kubectl cluster-info --context kind-NAME

DELETE KIND CLUSTER

kind delete cluster --name Name (--name is optional)

LOAD AN IMAGE INTO MY CLUSTER
kind load docker-image my-custom-image-0 my-custom-image-1


### INSTALL HYPERKIT AND MINIKUBE ###

On MacOS
brew update
brew install hyperkit
brew install minikube
kubectl
minikube

### CREATE MINIKUBE CLUSER ###

minikube start --vm-driver=hyperkit
kubectl get nodes
minikube status
kubectl version

DELETE CLUSTER AND RESTART IN DEBUG MODE
minikube delete
minikube start --vm-driver=hyperkit --v=7 --alsologtostderr
minikube status

KUBECTL COMMANDS
kubectl get nodes
kubectl get pod
kubectl get services
kubectl create deployment nginx-depl --image=nginx
kubectl get deployment
kubectl get replicaset
kubectl edit deployment nginx-depl

DEBUGGING
kubectl logs {pod-name}
kubectl exec -it {pod-name} -- bin/bash

CREATE MONGO DEPLOYMENT
kubectl create deployment mongo-depl --image=mongo
kubectl logs mongo-depl-{pod-name}
kubectl describe pod mongo-depl-{pod-name}

DELETE DEPLOYMENT
kubectl delete deployment mongo-depl
kubectl delete deployment nginx-depl

CREATE OR EDIT CONFIG
vim nginx-deployment.yaml
kubectl apply -f nginx-deployment.yaml
kubectl get pod
kubectl get deployment

DELETE WITH CONFIG
kubectl delete -f nginx-deployment.yaml

#Metrics
kubectl top The kubectl top command returns current CPU and memory usage for a cluster’s pods or nodes, or for a particular pod or node if specified.

Reference

### Janashia, N., 2021. Files · master · Nana Janashia / youtube-tutorial-series. [online] GitLab. Available at: <https://gitlab.com/nanuchi/youtube-tutorial-series/-/tree/master/> [Accessed 2 September 2021]. ### 


### Kind.sigs.k8s.io. 2021. kind – Quick Start. [online] Available at: <https://kind.sigs.k8s.io/docs/user/quick-start/#installation> [Accessed 2 September 2021].###
 
