# kubectl Cheat Sheet

This README provides a quick reference for common `kubectl` commands used for managing Kubernetes clusters.

 `Refferences` ([kubectl Cheat Sheet](https://k8s-docs.netlify.app/en/docs/reference/kubectl/cheatsheet/))

## Prerequisites

Before using `kubectl`, ensure you have:

- Installed and configured `kubectl` ([installation guide](https://kubernetes.io/docs/tasks/tools/install-kubectl/))
- Access to a Kubernetes cluster (local or remote)

## Basic Commands

### View Cluster Information
- Create a pod or deployment:
  >NOTE: Before this, you should have created a ymal file including all configurations
  ```bash
  kubectl apply -f pod.yaml
  ```
  ```bash
  kubectl apply -f development.yaml
- View cluster nodes:
  ```bash
  kubectl get nodes
- View cluster nodes' entire details:
  ```bash
  kubectl get nodes -o wide
- View cluster pods:
  ```bash
  kubectl get pods
- To login to the Kubernete cluster:
  
  #### if we use minikube as our K8s distribution,
  ```bash
  minikube ssh
  ```
  ```bash
  curl <cluster IP address>
  ```
  
- View cluster pods' more details (To get IP Address of the pods):
  ```bash
  kubectl get pods -o wide
  ```
  If you want to understand how kubectl is talking to kubernetes API server and what is happening
  behind the scenes when you run the "kubectl get pods" command, then use this
  ````
  kubectl get pods -v=7
  ````
  ````
  kubectl get pods -v=9
  ````
  > NOTE: 9 is the maximum verbosity level. It will return more information about
  > API call rather than v=7
- View specific pod's entire details:
  ```bash
  kubectl describe pod <pode_name>
  ```
  This command will give us all the information for us. We'll be able to know whether pod is 
  runnning, if there is any issue, what is the issue with the pod, if there is any error, what 
  is the error with the pod,, etc.
  >NOTE: This command (kubectl describe pod) is mostly used for debugs the pods/application.
  >Additionaly, we can use kubectl logs command for debugging. 
- Remove a pod:
  ```bash
  kubectl delete pod <pode_name>
- To verify logs of a specific  pod:
  ```bash
  kubectl logs <pode_name>
- List-out all deployements:
  ```bash
  kubectl get deploy
- List-out all replicaSets:
  ```bash
  kubectl get rs
 - List out all resources that are available in particular namespace
   #### It will list out all kubernetes pods, deployments, services.
  ```bash
  kubectl get all
```
   #### If you want list out information for all the namespaces,
  ```bash
  kubectl get all -A
  ````
 It will list out  for all the namespaces, all the application in your cluster  
 - Watch at pods what's going on:
   
  It will display all actions which happend to the pods
  ```bash
  kubectl get pods -w
```
- Go inside the pod:
  ````bash
  docker exec -it <pod_name> -- /bin/bash
  ````
  ```bash
  kubectl exec -it <pod-name> /bin/bash

