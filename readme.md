daclarative way: using a yaml file
imerative way : using kubectl command

kubectl get node

kubectl create -f deploy.yaml
# f for file

kubectl get pod
# to get info abt pod


kubectl describe pod <pod_name>
# to describe pods


kubectl delete pod <pod_name>

# Replica sets

kubectl run <pod_name> --image=<iamge_name> --port <port> --restart=Never

kubectl create  -f <file_name>

kubectl scale rs <pod_name> --replicas=4

kubectl delete rs <pod_name>


# Rollout, Update and Rollback
kubectl rollout history deploy <deployment_name>

# download deployemnt file deployed using imperative way
kubectl get deploy <deployment_name> -o yaml > <file_name>

# migth need to remove resource idgit st
# after change deployment file apply command 
kubectl apply -f <file_name>
