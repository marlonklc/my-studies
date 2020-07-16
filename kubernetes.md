## Requirements
### ---- docker (https://docs.docker.com/install/)
### ---- kubernetes (to this example use minikube)
- install minikube (choco, windows installer or docker)
- install kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)

#### start minikube
```
minikube start
  --vm-driver=<driver-name>
    virtualbox
    hyperv - (driver installation) Note that the IP below is dynamic and can change. It can be retrieved with minikube ip.
    none - Runs the Kubernetes components on the host and not in a virtual machine. You need to be running Linux and to have Docker installed.
  --memory=4096 (in MB)
  --cpus=4
```
#### describe specific or all services on cluster 
`kubectl describe services <serviceName>`
#### redirect service directly on command line
`minikube service <service-name>`

## NAMESPACE
That way organize your projects (like a "folder" or a group)
#### create namespace: `kubectl create namespace <name>`
#### set current context namespace: `kubectl config set-context --current --namespace=<name>`

### ---- istio

### check pods on istio
`kubectl get pods -n istio-system`
