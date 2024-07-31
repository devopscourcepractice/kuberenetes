# kuberenetes
launch aws account with 2cpu 4gb ram
Certainly! To install Minikube on an Ubuntu EC2 instance, follow these steps:
 Install Kubectl (command-line client for Kubernetes): curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
 chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl

Install Docker (if not already installed): You can use the following shell script to install Docker: curl -fsSL https://get.docker.com -o get-docker.sh
 sh get-docker.sh

 Install Minikube: curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube
 sudo mv minikube /usr/local/bin/

 Start Minikube : minikube start --driver=docker --force

Check Minikube status: minikube status
