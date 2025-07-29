🧱 Microservices Kubernetes Deployment (Node.js + Minikube)
This project sets up and deploys four containerized Node.js microservices using Kubernetes on Minikube:
User Service – Port 3000
Product Service – Port 3001
Order Service – Port 3002
Gateway Service – Port 3003

🗂️ Directory Structure
Minikube-Microservices/
├── user-deployment.yaml
├── product-deployment.yaml
├── order-deployment.yaml
├── gateway-deployment.yaml
├── user-service.yaml
├── product-service.yaml
├── order-service.yaml
├── gateway-service.yaml

🚀 1. Minikube Setup & Initialization
✅ Prerequisites
Minikube
kubectl
Docker (for local builds)

🔧 Start Minikube
minikube start --memory=4096 --cpus=2

Ensure Minikube is running: minikube status

📦 2. Kubernetes Deployment
Apply all deployment and service YAML files:

kubectl apply -f deploment.yaml
kubectl apply -f service.yaml

Repeat same for all four srevices

🧪 3. Verifying the Deployment
Check if Pods are Running
kubectl get pods
<img width="852" height="174" alt="image" src="https://github.com/user-attachments/assets/922f319d-b303-49d7-80e7-4c17f1267f7d" />

Check if Services are Running
kubectl get svc
<img width="884" height="121" alt="image" src="https://github.com/user-attachments/assets/21bbd41a-63ec-494e-b0e5-593ff3caa2fb" />

Port Forwarding (for local access)
kubectl port-forward service/user-service 3000:3000
kubectl port-forward service/product-service 3001:3001
kubectl port-forward service/order-service 3002:3002
kubectl port-forward service/gateway-service 3003:3003

Tested each service locally using browser:
curl http://localhost:3003    # Gateway
curl http://localhost:3000    # User
