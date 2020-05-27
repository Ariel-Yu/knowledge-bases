# Kubernetes control tool - kubectl

- [General](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#general)
- [Pods](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#pods---po)
- [Nodes](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#nodes---no)
- [ReplicaSets](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#replicasets---rs)
- [Deployments](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#deployments---deploy)
- [Services](https://github.com/Ariel-Yu/knowledge-bases/blob/master/kubernetes/kubectl.md#services---svc)

## General

```
kubectl create -f <definition_file>

kubectl get <all|object> [<certain_object>]
kubectl get <all|object> [<certain_object>] -o wide
kubectl get <all|object> -l <label_name>=<label_value>
kubectl get <all|object> -n <namespace>
kubectl get <all|object> --all-namespaces
kubectl describe <object> [<certain_object>]
kubectl explain <object> [--recursive] [| wc] [| less]

kubectl delete <object> <certain_object>
kubectl delete -f <definition_file>
```

## Pods - po

```
kubectl run <pod_name> --image=<image_name> --restart=Never
kubectl create -f <pod_definition_file>

kubectl get pods [<pod_name>]
kubectl get pods [<pod_name>] -o wide
kubectl describe pods [<pod_name>]
kubectl explain pods
kubectl logs <pod_name>

kubectl delete pods <pod_name>
```

## Nodes - no

```
kubectl get nodes [<node_name>]
kubectl get nodes [<node_name>] -o wide
kubectl describe nodes [<node_name>]
kubectl explain nodes
```

## ReplicaSets - rs

```
kubectl create -f <replicaset_definition_file>

kubectl get replicasets [<replicaset_name>]
kubectl get replicasets [<replicaset_name>] -o wide
kubectl desribe replicasets [<replicaset_name>]
kubectl explain replicasets

kubectl delete replicasets <replicaset_name>

kubectl replace -f <replicaset_definition_file>
kubectl edig replicasets <replicaset_name>
kubectl scale --replicas=<new_number> -f <replicaset_definition_files>
kubectl scale --replicas=<new_number> replicasets <replicaset_name>
```

## Deployments - deploy

```
kubectl create -f <deployment_file>
kubectl create deployment <deployment_name> --image=<image_name> -> Create a deployment with a replicaset and a pod

kubectl get deployments [<deployment_name>]
kubectl get deployments [<deployment_name>] -o wide
kubectl describe deployments [<deployment_name>]
kubectl explain deployments

kubectl delete deployments <deployment_name>
```

## Services - svc

```
kubectl create -f <service_file>
kubectl expose <replicaset|deployment> <replicaset|deployment_name> --port=<port> [--name=<service_name>] [--type=<PortNode|ClusterIP>]

kubectl get services [<service_name>]
kubectl get services [<service_name>] -o wide
kubectl describe services [<service_name>]
kubectl explain services

kubectl delete services <service_name>
```