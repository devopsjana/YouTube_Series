# Minikube on AWS

### Install docker
```
sudo yum update -y
sudo yum install docker -y
sudo systemctl status docker
sudo systemctl enable --now docker
```

### Install Kubectl
```
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
```
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
mv kubectl /bin/kubectl
chmod a+x /bin/kubectl
```

### Install Minikube
```
https://aws.plainenglish.io/running-kubernetes-using-minikube-cluster-on-the-aws-cloud-4259df916a07
https://minikube.sigs.k8s.io/docs/start/
```
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/bin/minikube
sudo yum install conntrack-tools -y
```

### Start Minikube
```
minikube start --vm-driver=none
```

### Test the setup
```
kubectl run hello-minikube --image=gcr.io/google_containers/echoserver:1.4 --port=8080
kubectl expose pod hello-minikube --type=NodePort

```

