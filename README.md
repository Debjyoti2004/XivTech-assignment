# Hello World Kubernetes Deployment
This project demonstrates deploying a simple "Hello, World" web application using NGINX on a local Kubernetes cluster with Minikube.

## 📁 Project Structure
```
.
├── app
│   └── index.html              # Simple HTML page served by NGINX
├── Dockerfile                  # Dockerfile to build the NGINX image
└── k8s
    ├── deployment.yaml         # Kubernetes Deployment manifest
    ├── namespace.yaml          # (Optional) Namespace manifest
    └── service.yaml            # Kubernetes Service (ClusterIP) manifest
```
## 🚀  Objective
Deploy a custom NGINX Docker container that serves a static "Hello, World" HTML page on a local Kubernetes cluster using Minikube.

## 🧱 Prerequisites
Docker

kubectl

Minikube


## 🛠️ Setup Instructions
1. Start Minikube
```sh
minikube start
```
2. Build Docker Image
```
docker build -t hello-world-nginx .
```
3. Apply Kubernetes Manifests
```
kubectl apply -f k8s/
```
If you're using a custom namespace:
```
kubectl apply -f k8s/namespace.yaml
```
4. Port Forward to Access the App
Get the pod name:
```
kubectl get pods
```
Port forward to access NGINX:

```
kubectl port-forward svc/<svc-name> 8080:80
```
Then open in your browser:

```
http://localhost:8080
```
Expected Output:
```
Hello, World from Kubernetes!
```
## 🎥 Demo Video
A walkthrough video demonstrating the full setup is available in the demo/ directory:
📁 demo/debjyoti-demo.mp4
