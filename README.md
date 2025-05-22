# Interacting with Kubernetes Cluster

This repository contains the necessary files and instructions for deploying a Node.js application to a Kubernetes cluster and interacting with it. This project was developed as part of the SIT323/SIT737 Cloud Native Application Development unit.

## Part I: Interacting with the Kubernetes Cluster

### Verify Application Status
kubectl get pods

Check if the service is properly created:

kubectl get services

### Port Forwarding
kubectl port-forward service/node-app-service 3000:80

### Access the Application
http://localhost:300


## Part II: Updating the Application

### 1. Modify Application Code

### 2. Build a New Docker Image
docker build -t node-kubernetes-app:v2 .

### 3. Update the Kubernetes Deployment
kubectl apply -f deployment.yaml

### 4. Verify the Update

Check the rollout status:

kubectl rollout status deployment/node-app-deployment


Check that new pods are being created:

kubectl get pods


### 5. Access the Updated Application
kubectl port-forward service/node-app-service 3000:80

Visit `http://localhost:8080` to see the updated application.

