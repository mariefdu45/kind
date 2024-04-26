# Kind
This repository is for installing a kind cluster on a fresh Ubuntu Linux system
> Ce dépot a pour but d'installer un cluster kind sur un serveur Linux Ubuntu fraichement installé.


## Some theory about components
> Un peu de théorie à propos des composants

Kind is used to simulate a kubernetes cluster with nodes as docker containers instead of physical or virtual servers. It is a good alternative to K3S or Minikube when you want to learm Kubernetes components (etcd, kube-api-server, scheduler, controller) because they are installed with kubeadm.

> Kind simule un cluster Kubernetes en utilisant des conteneurs docker au lieu de serveurs physiques ou virtuels. C'est une bonne alternative à K3S ou à Minikube quand on veut apprendre les composants internes de Kubernetes (etcd, kube-api-server, scheduler, controller) car ils sont installés avec kubeadm.

Cilium is a good alternative CNI (Container Network Interface) to Flannel, Calico or Weave.
> Cilium est une excellente alternative de CNI (Container Network Interface) à Flannel, Calico or Weave.

## Installing  your cluster
### Prerequisite
- An Ubuntu Linux server (tested with Ubuntu 22.04)
- root access
- git

### Get repository
```bash
# Get repository
git clone https://github.com/mariefdu45/kind.git
cd kind
echo ${PWD} > /tmp/.KIND_DIR
```
### Customizing variables
Modify variables.env for convenience.

### kind cluster installation
```bash
su -
```
```bash
path=`cat /tmp/.KIND_DIR`
cd $path
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
```
### Cluster Components checking
kind get clusters
kubectl get nodes
k get nodes
kubectl get pods -n kube-system 

### Creating a pod in the Kind Cluster
```bash
kubectl run monpod --image nginx
kubectl get pod
```
### Destroying the pod in the Kind Cluster
```bash
kubectl delete pod monpod
```


