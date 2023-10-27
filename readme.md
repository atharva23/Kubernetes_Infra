# Declarative Way (Using YAML Files)
---
# Get Node Information
kubectl get node

# Create Deployment
kubectl create -f deploy.yaml

# Get Pod Information
kubectl get pod

# Describe a Pod
kubectl describe pod <pod_name>

# Delete a Pod
kubectl delete pod <pod_name>

# Imperative Way (Using kubectl Command)
---
# Create a Pod
kubectl run <pod_name> --image=<image_name> --port <port> --restart=Never

# Create Deployment
kubectl create -f <file_name>

# Scale Replica Set
kubectl scale rs <pod_name> --replicas=4

# Delete Replica Set
kubectl delete rs <pod_name>

# Rollout, Update, and Rollback
---
# View Deployment History
kubectl rollout history deploy <deployment_name>

# Download Deployment YAML
kubectl get deploy <deployment_name> -o yaml > <file_name>

# Apply Deployment Changes
kubectl apply -f <file_name>

# Create Namespace
kubectl create namespace <namespace_name>

kubectl get pods --all-namespaces

# Permanently switch the namespace
kubectl config set-context --current --namespace=<namespace_name>

# Resource Quota to limit usage of resource consumption by user

# How service help to access dynamic IP of pods on nodes.
# Types of service node port , clusterip load balancer external name
kubectl expose pod <pod_name> --type=NodePort  --name=<name>

kubectl get svc

kubectl expose pod <pod_name> --type=NodePort --name=<name>  --dry-run -o yaml > <file_name>


kubectl expose pod blue-pod --type=NodePort --name=blue-svc --dry-run -o yaml > blue-svc.yaml

# manual schedulding change node name in configuration file

# Taint and Toleration effects Taints and tolerations work together to ensure that pods are not scheduled onto inappropriate nodes.

# One or more taints are applied to a node; this marks that the node should not accept any pods that do not tolerate the taints.

# One or more taints are applied to a node; this marks that the node should not accept any pods that do not tolerate the taints.

k taint node node01 run=mypod:NoSchedule

# for untaianted node
k taint node node01 run=mypod:NoSchedule-

# labels and selectors
kubectl get pods my-pod --show-labels

kubectl label nodes <node-name> disktype=ssd


# DAEMON SETS
# kube proxy installed throgh daemon set
# it might used to install monitoring solutions