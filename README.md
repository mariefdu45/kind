# Kind
This repository is for installing a kind cluster on a fresh Ubuntu Linux system

> Ce dépot a pour but d'installer un cluster kind sur un serveur Linux Ubuntu fraichement installé.


## Some theory about components
> Un peu de théorie à propos des composants

To be developped.
> A faire.




## Installing on your cluster
### Prerequisite
- An Ubuntu Linux server (tested with Ubuntu 22.04)
- root access
- installed git

### Kind cluster Installation
```bash
# Get priviledged access
su -
cd /tmp
# Get repository
git clone https://github.com/mariefdu45/kind.git
```
- Customizing variables.env for customization.
  
```bash

# using installation script
source main.sh
```

### Components checking
```bash
helm version
docker ps
kubectl version
kind version
kind get clusters
kubectl get pods -n kube-system 
```


### Using Kind Cluster
```bash
kubectl run monpod --image nginx
kubectl get pod
```

