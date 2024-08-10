# kuberenetes
launch aws EC2 instance with 2cpu 4gb ram
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

Check Minikube status: minikube staus


create deployment 
kubectl create -f deployment.yaml
kubectl get deploy
kubectl get pods

create service with nodeport 
kubectl create -f service.yaml
kubectl get svc 
minikube service servicename --url   without proxy it will work 

 to connect minikube cluste
 minikube ssh
 try to access the application wih curl


 AWS CLI instalation 

 To install the AWS CLI on Ubuntu running on WSL (Windows Subsystem for Linux), follow these steps:

1. **Update your package list and install prerequisites**:
    ```bash
    sudo apt update
    sudo apt install curl unzip -y
    ```

2. **Download the AWS CLI installer**:
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"


3. **Unzip the downloaded package**:
    unzip awscliv2.zip


4. **Run the installer**:
  sudo ./aws/install


5. **Verify the installation**:
    
    aws --version





