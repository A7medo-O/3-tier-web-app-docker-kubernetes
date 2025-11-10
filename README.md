# 🚀 Three-Tier Web Application Deployment (Docker & Kubernetes)

This project demonstrates the deployment of a **three-tier web application** consisting of a **frontend**, **backend**, and **database layer** using **Docker containers** and **Kubernetes orchestration**.

---

## 🧠 Overview

The project aims to show how modern DevOps practices can be applied to containerize and deploy a multi-layer application with scalability, automation, and maintainability in mind.

**Architecture Layers:**
- **Frontend:** Handles user interface and requests routing.
- **Backend:** A Go application providing REST API services.
- **Database:** Stores application data with persistent storage (PVC/PV).

---

## ⚙️ Technologies Used
- **Docker** – Containerization of the application components.  
- **Kubernetes** – Deployment, scaling, and service management.  
- **OpenShift (Optional)** – For enterprise-grade orchestration.  
- **Git & GitHub** – Version control and project management.  
- **Linux** – Environment for build and deployment scripts.  
- **CI/CD Ready** – Compatible with Jenkins, ArgoCD, and Terraform.

---

## 📂 Project Structure

├── backend/ # Go backend source code (main.go, Dockerfile)
│ ├── go.mod
│ ├── go.sum
│ └── main.go
│
└── k8s/ # Kubernetes manifests
├── backend-deployment.yaml
├── backend-secret.yaml
├── database-deployment.yaml
├── db-data-pv.yaml
├── db-data-pvc.yaml
├── db-secret.yaml
├── proxy-deployment.yaml
├── nginx-config.yaml
├── tls.crt
└── tls.key

## 🚀 How to Deploy

 1️⃣ Build and Tag the Backend Image

cd backend
docker build -t your-username/backend:latest .

2️⃣ Start Minikube or Connect to a Cluster

minikube start

3️⃣ Apply Kubernetes Manifests

kubectl apply -f k8s/
kubectl get pods,svc

4️⃣ Check Logs and Access

kubectl logs -l app=backend
minikube service proxy-service

🧩 Features

    Three-layer architecture (frontend / backend / database)

    Containerized and orchestrated using Docker & Kubernetes

    Declarative infrastructure (YAML manifests)

    Scalable, modular, and CI/CD ready

    Uses Kubernetes Secrets and TLS for secure communication

🔐 Security Notes

    ⚠️ Do not commit private keys or secret files to the repository.
    Sensitive files such as tls.key, backend-secret.yaml, and db-secret.yaml should be added to .gitignore and managed securely via Kubernetes Secrets or GitHub Secrets

💻Author

Ahmed Khaled Aboubakr
