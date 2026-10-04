
> 🚀 Production-grade Grocery Delivery App with End-to-End DevOps Automation

![DevOps](https://img.shields.io/badge/DevOps-Production-red?style=for-the-badge)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker)
![Kubernetes](https://img.shields.io/badge/Kubernetes-EKS-326CE5?style=for-the-badge&logo=kubernetes)
![Jenkins](https://img.shields.io/badge/Jenkins-CI/CD-D24939?style=for-the-badge&logo=jenkins)
![Terraform](https://img.shields.io/badge/Terraform-IaC-7B42BC?style=for-the-badge&logo=terraform)

---

📖 Overview

*FreshMart* is a scalable MERN Stack e-commerce platform automated with modern DevOps practices. This repo contains complete code for *Local Dev (Docker Compose)* to *Production (EKS)* with Monitoring & Security.

✨ Features
- 🛍️ *E-Commerce:* Product, Cart, Order Management
- 🔐 *Auth:* JWT + RBAC (Admin/Customer)
- 📦 *Scalable:* Kubernetes HPA (2-10 pods)
- 📊 *Observability:* Metrics + Logs + Dashboards

---

🏗️ Architecture - DevOps Flow Chart

```mermaid
graph TD
    A[👨‍💻 Developer<br/>Push Code] --> B[🌿 GitHub<br/>Repo]
    B --> C{🔄 CI/CD Trigger}
    C --> D[🤖 Jenkins<br/>Pipeline]
    
    D --> E[📦 Docker Build<br/>Backend, Frontend, Admin]
    E --> F[🔍 Trivy Scan<br/>Security Check]
    F --> G[📝 SonarQube<br/>Code Quality]
    
    G --> H[🐳 DockerHub<br/>Registry]
    H --> I[🚀 ArgoCD<br/>GitOps]
    
    I --> J[☸️ Kubernetes<br/>EKS Cluster]
    J --> K1[🟢 Backend Pods x2]
    J --> K2[🔵 Frontend Pods x2]
    J --> K3[🟣 Admin Pods x1]
    J --> K4[🍃 MongoDB]
    
    K1 --> L[🌐 Ingress NGINX<br/>Load Balancer]
    K2 --> L
    K3 --> L
    
    L --> M[👥 Users]
    
    J --> N[📈 Prometheus<br/>Metrics Collection]
    N --> O[📊 Grafana<br/>Dashboard]
    
    J --> P[📜 Loki<br/>Log Aggregation]
    P --> O

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style M fill:#bbf,stroke:#333,stroke-width:2px
    style O fill:#ffcc00,stroke:#333,stroke-width:2px
    style J fill:#326CE5,color:#fff
---

🛠️ Tech Stack - Present Market 2026
Layer	Icon	Tool	Purpose
*Source*	🌿	*GitHub*	Code Management
*Container*	🐳	*Docker + Compose*	App Containerization
*Orchestration*	☸️	*K8s (EKS) + Helm*	Production Deploy
*IaC*	🌍	*Terraform*	Infra as Code
*CI*	🤖	*Jenkins*	Build & Test
*CD*	🚀	*ArgoCD*	GitOps Deploy
*Monitoring*	📈	*Prometheus*	Metrics
*Visualization*	📊	*Grafana*	Dashboards
*Logs*	📜	*Loki*	Centralized Logs
*Security*	🔍	*Trivy + SonarQube*	Scan & Quality
*Scaling*	📏	*HPA*	Auto Scaling
---

📁 Project Structure
FreshMart_App/
├── 🟢 backend/              # Node.js + Express API
│   └── Dockerfile
├── 🔵 frontend/             # React User App
│   └── Dockerfile
├── 🟣 admin/                # React Admin Panel
│   └── Dockerfile
├── ☸️ k8s/                   # Kubernetes Manifests
│   ├── 01-namespace.yaml
│   ├── 02-mongodb.yaml
│   ├── 03-backend.yaml
│   ├── 04-frontend.yaml
│   ├── 05-ingress.yaml
│   └── 06-hpa.yaml
├── 📈 monitoring/
│   ├── prometheus.yml
│   └── grafana/dashboard.json
├── 🌍 terraform/
│   └── main.tf (EKS)
├── 🤖 Jenkinsfile
├── 🐳 docker-compose.yml
└── 📖 README.md
---

⚡ Quick Start

🔹 Local Dev (2 min)
git clone https://github.com/HexagonDigitalServices/FreshMart_App.git
cd FreshMart_App
docker-compose up --build

🌐 Access:
Frontend   -> http://localhost:3000
Admin      -> http://localhost:3001
Backend    -> http://localhost:5000
Prometheus -> http://localhost:9090
Grafana    -> http://localhost:3002 (admin/admin)
🔹 Production (EKS)
1. Infra Create
cd terraform && terraform init && terraform apply

2. Deploy App
kubectl apply -f k8s/

3. Check Status
kubectl get pods -n freshmart -w
---

🔄 CI/CD Pipeline Flow
👨‍💻 Git Push
  ↓
🤖 Jenkins Pipeline Started
  ↓
📦 Step 1: Build Docker Images
  ↓
🔍 Step 2: Trivy Vulnerability Scan
  ↓
📝 Step 3: SonarQube Code Analysis
  ↓
🐳 Step 4: Push to DockerHub
  ↓
🚀 Step 5: ArgoCD Sync to K8s
  ↓
✅ Step 6: Health Check & Slack Notify
  ↓
📊 Monitored in Grafana
---

📊 Monitoring Dashboard

Grafana Dashboards Included:
- 🖥️ Node Exporter (ID: 1860)
- ☸️ Kubernetes Cluster
- 🟢 FreshMart API - Request Rate, Latency, Error Rate
- 📦 Pod CPU/RAM Usage

Import: monitoring/grafana/dashboard.json

---

🔐 Security

- ✅ No Hardcoded Secrets (Using Vault)
- ✅ Trivy Image Scan in Pipeline
- ✅ SonarQube Quality Gate

---

👨‍💻 Author

Hexagon Digital Services
🌐 Portfolio: [hexagondigitalservices.github.io]
📧 Contact: hexagon@example.com

---

⭐ Support

If you like this project, give a ⭐ on GitHub!

> Built with ❤️ for Production

---
