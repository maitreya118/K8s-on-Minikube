# K8s-on-Minikube
--mini kube installation on AWS ec2 instance.

curl -LO https://storage.googleapis.com/kubernetes-release/release/ curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin/kubectl
--install docker
sudo apt-get update && \
    sudo apt-get install docker.io -y
--Install Minikube

curl -Lo minikube https://https//:storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

--Check Minikube Version
minikube version

--Running Minikube on EC2 Ubuntu
sudo -i
minikube start --vm-driver=none
minikube status

--Let us run our first container
kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080

kubectl get pods

kubectl create deployment hello-minikube --image=gcr.io/google_containers/echoserver:1.4 

kubectl get deployments

kubectl expose deployment hello-minikube --type=NodePort --port=8080

kubectl get services


if you get error while starting minikube please use the below command 
sudo apt-get install -y conntrack

