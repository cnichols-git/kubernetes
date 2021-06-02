# kubernetes

commands for minikube

kubectl get nodes  
kubectl get pod  
kubectl get services  

Create pod in kubectl  
**you will not be interacting with pods while using Kubernetes, you will interact with deployments

ex. kubectl create deployment NAME --image=image [--dry-run] [options]

you can have a deployment that creates one replica

kubectl edit depolyment nginx-depl

**debugging
kubectl logs nginx-depl-8971409845
kubectl describe pod nginx-depl-8971409845

kubectl exec - this gives and interactive terminal to the dpecified pod  
ec. kubectl exec -it mongo-depl-507234871234087325 -- bin/bash  

Remove your pod, depl or replicaset

Creating a basic deployment
---

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replica: 1
  selector:
    matchlables: 
      app: nginx
  template:
    metadata:
      lables:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.16
        ports"
        - containerPort:80
