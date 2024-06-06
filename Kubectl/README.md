# kubectl Cheat Sheet

This README provides a quick reference for common `kubectl` commands used for managing Kubernetes clusters.

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
- View cluster pods' more details:
  ```bash
  kubectl get pods -o wide
- View specific pod's entire details:
  ```bash
  kubectl describe pod <pode_name> 
- Remove a pod:
  ```bash
  kubectl delete pod <pode_name>

  
