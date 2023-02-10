## Example Voting App Kubernetes

This is based on the original [example-voting-app](https://github.com/dockersamples/example-voting-app) repository from the [docker-examples](https://github.com/dockersamples) GitHub page

and modified it to work on the Kubernetes cluster.

Prerequisites: minikube

kubectl create -f voting-app-deploy.yaml 
kubectl create -f voting-app-service.yaml 
kubectl create -f redis-deploy.yaml 
kubectl create -f redis-service.yaml  
kubectl create -f postgres-deploy.yaml 
kubectl create -f postgres-service.yaml   
kubectl create -f worker-app-deploy.yaml  
kubectl create -f result-app-deploy.yaml 
kubectl create -f result-app-service.yaml 


  kubectl get pods,svc 
  kubectl get deployment,svc  

  minikube service voting-service --url 


  minikube service result-service --url

visit both urls

Issue in Mac
Run below for both services

First terminal
ps -ef | grep docker@127.0.0.1

Second terminal
ssh -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no -N docker@127.0.0.1 -p 55972 -i /Users/FOO/.minikube/machines/minikube/id_rsa -L TUNNEL_PORT:CLUSTER_IP:TARGET_PORT


Visit http://127.0.0.1:TUNNEL_PORT

