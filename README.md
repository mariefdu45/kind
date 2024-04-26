# Kind
This repository is for installing a kind cluster on a fresh Ubuntu Linux system

> Ce dépot a pour but d'installer un cluster kind sur un serveur Linux Ubuntu fraichement installé.


## Some theory about components
> Un peu de théorie à propos des composants

Kind cluster with 2 nodes (1 master and 1 worker) is installed using Cilium CNI.
> Le script installe un cluster kubernetes kind avec par défaut un master et un worker. Il installe ensuite le CNI Cilium


## Installing on your cluster
### Prerequisite
- An Ubuntu Linux server (tested with Ubuntu 22.04)
- root access
- installed git

### Get repository
```bash
# Get priviledged access
su -
```
```bash
# Get repository
cd /tmp
git clone https://github.com/mariefdu45/kind.git
```
### Customizing variables
- Modify variables.env for your convenience.
  
```bash

### kind cluster installation
# using installation script
source main.sh
```

## Checking your cluster
### Individual Components checking
```bash
helm version
docker version
docker ps
kubectl version
kind version
### Cluster Components checking
kind get clusters
kubectl get nodes
k get nodes
kubectl get pods -n kube-system 
```


### Using Kind Cluster
```bash
kubectl run monpod --image nginx
kubectl get pod
```

