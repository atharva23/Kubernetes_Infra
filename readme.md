# Declarative Way (Using YAML Files)
---
# Get Node Information
kubectl get node

# Create Deployment from YAML
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
