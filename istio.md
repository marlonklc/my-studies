## Requirements
### docker (https://docs.docker.com/install/)
### kubernetes (to this example use minikube)
- install minikube (choco, windows installer or docker)
- minikube start
  - `option --vm-driver`
    - virtualbox
    - hyperv (driver installation) Note that the IP below is dynamic and can change. It can be retrieved with minikube ip.
    - none (Runs the Kubernetes components on the host and not in a virtual machine. You need to be running Linux and to have Docker installed.)
  - `option --memory=4096 --cpus=4`
- install kubectl (https://kubernetes.io/docs/tasks/tools/install-kubectl/)
#### verify ip address of running cluster in kubeconfig
`minikube update-context`

### istio
