# kubectl Cheat Sheet

This README provides a quick reference for common `kubectl` commands used for managing Kubernetes clusters.

 `Refferences` ([kubectl Cheat Sheet](https://k8s-docs.netlify.app/en/docs/reference/kubectl/cheatsheet/))

## Prerequisites

Before using `kubectl`, ensure you have:

- Installed and configured `kubectl` ([installation guide](https://kubernetes.io/docs/tasks/tools/install-kubectl/))
- Access to a Kubernetes cluster (local or remote)

## Basic Commands

### View Cluster Information

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
  
- View cluster pods' more details:
  ```bash
  kubectl get pods -o wide
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
  
