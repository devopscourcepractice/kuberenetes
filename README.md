Launch an EC2 Instance:
Choose an Ubuntu AMI (e.g., Ubuntu Server 20.04 LTS).
Select an instance type with at least 2 vCPUs (e.g., t3.micro).
Configure security groups to allow SSH access.
Connect to Your EC2 Instance:
ssh -i <your-key-pair>.pem ubuntu@<your-ec2-public-ip>

Update the System:
sudo apt update && sudo apt upgrade -y

Install Docker:
sudo apt install -y docker.io
sudo usermod -aG docker $USER
newgrp docker

Install kubectl:
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

Install Minikube:
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
chmod +x minikube
sudo mv minikube /usr/local/bin/

Start Minikube:
sudo minikube start --driver=none

Verify the Installation:
minikube status


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






