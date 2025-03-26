# MongoDB and Mongo Express Deployment on Kubernetes

This repository contains Kubernetes YAML files to deploy MongoDB on a Minikube cluster.

## Prerequisites

Before running this setup, ensure you have the following installed:
- [Minikube](https://minikube.sigs.k8s.io/docs/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/)

## Setup Instructions

### 1. Start Minikube
Start Minikube if it is not already running:
```sh
minikube start
```

### 2. Create Secrets
Create the MongoDB secret for authentication:
```sh
kubectl apply -f mongo-secret.yaml
```

### 3. Create ConfigMap
Apply the ConfigMap for MongoDB:
```sh
kubectl apply -f mongo-configmap.yaml
```

### 4. Deploy MongoDB
Deploy the MongoDB database:
```sh
kubectl apply -f mongo-deployment.yaml
```

### 5. Deploy MongoDB Express (if applicable)
If you are using Mongo Express, deploy it:
```sh
kubectl apply -f mongo-exp-deployment.yaml
```

### 6. Verify Deployments
Check if the pods are running:
```sh
kubectl get pods
```

### 7. Access Mongo Express (Optional)
If Mongo Express is deployed, use Minikube to expose the service:
```sh
minikube service mongo-express-service
```
This will map port `8081` to `30000` and open Mongo Express in your default browser.

## License
This project is licensed under the Apache-2.0 License.

