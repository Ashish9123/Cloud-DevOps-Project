# 🚀 Cloud DevOps Project

<div align="center">

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white)

**Complete End-to-End DevOps Pipeline Implementation**

[Features](#-features) • [Architecture](#-architecture) • [Quick Start](#-quick-start) • [Documentation](#-documentation)

</div>

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Technologies Used](#️-technologies-used)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Quick Start](#-quick-start)
- [Detailed Setup Guide](#-detailed-setup-guide)
- [CI/CD Pipeline](#-cicd-pipeline)
- [Monitoring & Access](#-monitoring--access)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [Author](#-author)

---

## 🎯 Project Overview

This project demonstrates a **complete production-ready DevOps pipeline** implementation using industry-standard tools and best practices. It covers the entire software delivery lifecycle from infrastructure provisioning to continuous deployment.

### Key Highlights

✅ **Infrastructure as Code** - Terraform modules for AWS resources  
✅ **Configuration Management** - Ansible playbooks with dynamic inventory  
✅ **Containerization** - Docker multi-stage builds  
✅ **Orchestration** - Kubernetes (EKS) with namespace isolation  
✅ **CI/CD Pipeline** - Jenkins with shared libraries  
✅ **GitOps** - ArgoCD for declarative deployments  
✅ **Security** - Trivy image scanning, Security Groups  
✅ **Monitoring** - CloudWatch integration

---

## ✨ Features

### 🏗️ Infrastructure Provisioning
- **Terraform Modules**: Modular infrastructure with Network and Server modules
- **AWS Resources**: VPC, Subnets, IGW, Security Groups, EC2, EKS
- **S3 Backend**: Remote state management with locking
- **CloudWatch**: EC2 monitoring and logging

### 🔧 Configuration Management
- **Ansible Roles**: Java, Docker, Git, Jenkins
- **Dynamic Inventory**: AWS EC2 plugin for automatic discovery
- **Idempotent**: Safely re-runnable playbooks

### 🐳 Containerization
- **Multi-stage Dockerfile**: Optimized image size
- **Flask Application**: Python-based web application
- **Health Checks**: Built-in health endpoints
- **DockerHub**: Automated image publishing

### ☸️ Kubernetes Orchestration
- **EKS Cluster**: Managed Kubernetes on AWS
- **Namespace Isolation**: `ivolve` namespace for application
- **LoadBalancer Service**: Automatic AWS ELB provisioning
- **Horizontal Scaling**: Multiple pod replicas

### 🔄 CI/CD Pipeline
- **Jenkins**: Automated build and deployment
- **Shared Library**: Reusable pipeline functions
- **Trivy Scanning**: Container vulnerability detection
- **GitOps**: Git as single source of truth

### 📦 Continuous Deployment
- **ArgoCD**: Automated sync from Git
- **Self-Healing**: Automatic drift correction
- **Rollback**: Easy version management

---

## 🏛️ Architecture
```
┌─────────────────────────────────────────────────────────────────┐
│                          DEVELOPER                              │
│                              │                                   │
│                              ▼                                   │
│                    ┌──────────────────┐                         │
│                    │   GitHub Repo    │                         │
│                    └────────┬─────────┘                         │
│                             │                                    │
│            ┌────────────────┴────────────────┐                 │
│            ▼                                  ▼                  │
│   ┌─────────────────┐              ┌──────────────────┐        │
│   │  Jenkins CI     │              │   ArgoCD         │        │
│   │  - Build        │              │   - Sync         │        │
│   │  - Test         │              │   - Deploy       │        │
│   │  - Scan (Trivy) │              │   - Monitor      │        │
│   │  - Push to Hub  │              └─────────┬────────┘        │
│   └────────┬────────┘                        │                 │
│            │                                  │                  │
│            ▼                                  ▼                  │
│   ┌─────────────────┐              ┌──────────────────┐        │
│   │   DockerHub     │──────────────▶│  EKS Cluster    │        │
│   │   Image Registry│              │  - Namespace     │        │
│   └─────────────────┘              │  - Deployment    │        │
│                                     │  - Service (LB)  │        │
│                                     └─────────┬────────┘        │
│                                               │                  │
│                                               ▼                  │
│                                     ┌──────────────────┐        │
│                                     │  Load Balancer   │        │
│                                     │  (AWS ELB)       │        │
│                                     └─────────┬────────┘        │
│                                               │                  │
│                                               ▼                  │
│                                     ┌──────────────────┐        │
│                                     │   END USERS      │        │
│                                     └──────────────────┘        │
└─────────────────────────────────────────────────────────────────┘

Infrastructure Layer (Terraform):
┌──────────────────────────────────────────────────────────────┐
│  VPC  │  Subnets  │  IGW  │  Security Groups  │  EC2  │  EKS │
└──────────────────────────────────────────────────────────────┘

Configuration Layer (Ansible):
┌──────────────────────────────────────────────────────────────┐
│  Java  │  Docker  │  Git  │  Jenkins  │  Monitoring         │
└──────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Technologies Used

### Cloud & Infrastructure
- **AWS**: EKS, EC2, VPC, ELB, CloudWatch
- **Terraform**: v1.5+ (Infrastructure as Code)
- **S3**: Remote state backend

### Configuration & Orchestration
- **Ansible**: 2.9+ (Configuration Management)
- **Kubernetes**: 1.28+ (Container Orchestration)
- **Docker**: 24+ (Containerization)

### CI/CD & GitOps
- **Jenkins**: 2.4+ (Continuous Integration)
- **ArgoCD**: 2.9+ (Continuous Deployment)
- **Git**: Version Control

### Security & Monitoring
- **Trivy**: Container vulnerability scanning
- **AWS CloudWatch**: Metrics and logging
- **Security Groups**: Network security

### Application
- **Python**: 3.9+
- **Flask**: Web framework
- **Gunicorn**: WSGI server

---

## 📁 Project Structure
```
Cloud-DevOps-Project/
│
├── README.md                          # Main project documentation
├── .gitignore                         # Git ignore rules
│
├── docker/                            # Application & Containerization
│   ├── Dockerfile                     # Multi-stage Docker build
│   ├── app.py                         # Flask application
│   ├── requirements.txt               # Python dependencies
│   └── README.md                      # Docker documentation
│
├── kubernetes/                        # K8s Manifests
│   ├── deployment.yaml                # Application deployment
│   ├── service.yaml                   # LoadBalancer service
│   └── README.md                      # Kubernetes setup guide
│
├── terraform/                         # Infrastructure as Code
│   ├── main.tf                        # Main Terraform configuration
│   ├── variables.tf                   # Input variables
│   ├── outputs.tf                     # Output values
│   ├── backend.tf                     # S3 backend configuration
│   ├── modules/                       # Terraform modules
│   │   ├── network/                   # VPC, Subnets, IGW
│   │   └── server/                    # EC2, Security Groups
│   └── README.md                      # Terraform documentation
│
├── ansible/                           # Configuration Management
│   ├── site.yaml                      # Main playbook
│   ├── dynamic_inventory.aws_ec2.yaml # AWS dynamic inventory
│   ├── roles/                         # Ansible roles
│   │   ├── java/                      # Java installation
│   │   ├── docker/                    # Docker setup
│   │   ├── git/                       # Git installation
│   │   └── jenkins/                   # Jenkins configuration
│   └── README.md                      # Ansible documentation
│
├── jenkins/                           # CI/CD Pipeline
│   ├── Jenkinsfile                    # Pipeline definition
│   ├── shared-library/                # Reusable functions
│   │   └── vars/
│   │       ├── buildImage.groovy
│   │       ├── pushImage.groovy
│   │       └── scanImage.groovy
│   └── README.md                      # Jenkins setup guide
│
└── argocd/                            # GitOps Configuration
    ├── application.yaml               # ArgoCD Application manifest
    └── README.md                      # ArgoCD documentation
```

---

## 📦 Prerequisites

Before starting, ensure you have the following installed:

### Required Tools
```bash
# AWS CLI
aws --version  # >= 2.0

# Terraform
terraform --version  # >= 1.5

# Ansible
ansible --version  # >= 2.9

# kubectl
kubectl version --client  # >= 1.28

# Docker
docker --version  # >= 24.0

# eksctl (for EKS)
eksctl version  # >= 0.150
```

### AWS Configuration
```bash
# Configure AWS credentials
aws configure

# Verify access
aws sts get-caller-identity
```

### SSH Key
```bash
# Generate SSH key for EC2 access
ssh-keygen -t rsa -b 4096 -f ~/.ssh/omar-key
```

---

## 🚀 Quick Start

### 1. Clone Repository
```bash
git clone https://github.com/Ashish9123/Cloud-DevOps-Project.git
cd Cloud-DevOps-Project
```

### 2. Provision Infrastructure
```bash
cd terraform/
terraform init
terraform plan
terraform apply -auto-approve
```

### 3. Configure Servers
```bash
cd ../ansible/
ansible-playbook site.yaml -i dynamic_inventory.aws_ec2.yaml
```

### 4. Build & Deploy Application
```bash
# Build Docker image
cd ../docker/
docker build -t ashishcb/cloud-devops-app:latest .

# Deploy to Kubernetes
cd ../kubernetes/
kubectl apply -f .
```

### 5. Access Application
```bash
# Get LoadBalancer URL
kubectl get svc app-service -n ivolve

# Open in browser
curl http://<LOAD_BALANCER_URL>
```

---

## 📚 Detailed Setup Guide

### Phase 1: Infrastructure Provisioning

#### Terraform Setup
```bash
cd terraform/

# Initialize Terraform
terraform init

# Plan infrastructure changes
terraform plan -var-file="dev.tfvars"

# Apply infrastructure
terraform apply -var-file="dev.tfvars" -auto-approve

# Output values
terraform output
```

**Resources Created:**
- ✅ VPC with public subnets
- ✅ Internet Gateway
- ✅ Security Groups (Jenkins: 8080, SSH: 22)
- ✅ EC2 instance for Jenkins
- ✅ EKS Cluster with managed node group
- ✅ CloudWatch monitoring

#### Verify Infrastructure
```bash
# Check EC2 instance
aws ec2 describe-instances --filters "Name=tag:Project,Values=cloud-devops-project"

# Check EKS cluster
aws eks describe-cluster --name cloud-devops-eks --region us-east-1
```

---

### Phase 2: Configuration Management

#### Ansible Playbook Execution
```bash
cd ansible/

# Test connectivity
ansible all -i dynamic_inventory.aws_ec2.yaml -m ping

# Run playbook
ansible-playbook site.yaml -i dynamic_inventory.aws_ec2.yaml \
  -u ec2-user --private-key ~/.ssh/ashish-key.pem

# Verify installations
ansible all -i dynamic_inventory.aws_ec2.yaml \
  -a "java -version" -u ec2-user --private-key ~/.ssh/ashish-key.pem
```

**Services Configured:**
- ✅ Java 17 (Amazon Corretto)
- ✅ Docker Engine
- ✅ Git
- ✅ Jenkins (http://EC2_IP:8080)

#### Access Jenkins
```bash
# Get Jenkins initial password
ssh -i ~/.ssh/ashish-key.pem ec2-user@<EC2_PUBLIC_IP>
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

### Phase 3: Containerization

#### Build Docker Image
```bash
cd docker/

# Build image
docker build -t ashishcb/cloud-devops-app:latest .

# Test locally
docker run -p 5000:5000 ashishcb/cloud-devops-app:latest

# Test endpoints
curl http://localhost:5000
curl http://localhost:5000/health

# Push to DockerHub
docker login
docker push ashishcb/cloud-devops-app:latest
```

---

### Phase 4: Kubernetes Deployment

#### Setup EKS Cluster
```bash
# Update kubeconfig
aws eks update-kubeconfig --region us-east-1 --name cloud-devops-eks

# Verify cluster access
kubectl get nodes

# Create namespace
kubectl create namespace ivolve
```

#### Deploy Application
```bash
cd kubernetes/

# Apply manifests
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# Watch deployment
kubectl get pods -n ivolve -w

# Get service details
kubectl get svc app-service -n ivolve
```

#### Verify Deployment
```bash
# Check pods
kubectl get pods -n ivolve

# Check logs
kubectl logs -f deployment/app-deployment -n ivolve

# Get LoadBalancer URL
kubectl get svc app-service -n ivolve -o jsonpath='{.status.loadBalancer.ingress[0].hostname}'

# Test application
curl http://<LOAD_BALANCER_URL>
curl http://<LOAD_BALANCER_URL>/health
```

---

### Phase 5: CI/CD Pipeline

#### Jenkins Setup
```bash
# Access Jenkins UI
http://<EC2_PUBLIC_IP>:8080

# Initial setup:
1. Enter initial admin password
2. Install suggested plugins
3. Create admin user
4. Configure Jenkins URL
```

#### Configure Pipeline
```bash
# In Jenkins UI:
1. New Item → Pipeline
2. Pipeline from SCM → Git
3. Repository URL: https://github.com/Ashish9123/Cloud-DevOps-Project.git
4. Script Path: jenkins/Jenkinsfile
5. Save & Build
```

#### Pipeline Stages
1. **Checkout**: Clone repository
2. **Build**: Build Docker image
3. **Scan**: Trivy vulnerability scan
4. **Push**: Push to DockerHub
5. **Deploy**: Update Kubernetes

---

### Phase 6: GitOps with ArgoCD

#### Install ArgoCD
```bash
# Create namespace
kubectl create namespace argocd

# Install ArgoCD
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Wait for pods
kubectl wait --for=condition=Ready pods --all -n argocd --timeout=300s
```

#### Access ArgoCD UI
```bash
# Get admin password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

# Port forward
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Open browser
https://localhost:8080
# Username: admin
# Password: (from above)
```

#### Deploy Application via ArgoCD
```bash
# Apply ArgoCD Application
kubectl apply -f argocd/application.yaml

# Check sync status
kubectl get application -n argocd

# Watch sync
kubectl get application cloud-devops-app -n argocd -w
```

---

## 🔄 CI/CD Pipeline

### Pipeline Flow
```
┌──────────────┐
│ Git Push     │
└──────┬───────┘
       │
       ▼
┌──────────────────────┐
│ Jenkins Trigger      │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ 1. Build Image       │
│    docker build      │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ 2. Scan Image        │
│    trivy scan        │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ 3. Push to DockerHub │
│    docker push       │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ 4. Update Manifests  │
│    Update image tag  │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ 5. ArgoCD Sync       │
│    Auto deploy       │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Application Running  │
└──────────────────────┘
```

### Jenkinsfile Overview
```groovy
pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                buildImage('Ashish9123/cloud-devops-app', 'latest')
            }
        }
        
        stage('Scan') {
            steps {
                scanImage('ashishcb/cloud-devops-app:latest')
            }
        }
        
        stage('Push') {
            steps {
                pushImage('ashishcb/cloud-devops-app', 'latest')
            }
        }
        
        stage('Deploy') {
            steps {
                updateManifests('kubernetes/deployment.yaml')
            }
        }
    }
}
```

---

## 📊 Monitoring & Access

### Application Endpoints

| Endpoint | URL | Purpose |
|----------|-----|---------|
| Main App | `http://<LB_URL>` | Application home |
| Health Check | `http://<LB_URL>/health` | Health status |
| Jenkins | `http://<EC2_IP>:8080` | CI/CD pipeline |
| ArgoCD | `https://localhost:8080` | GitOps dashboard |

### Monitoring Commands
```bash
# Check cluster health
kubectl get nodes
kubectl top nodes

# Check application pods
kubectl get pods -n ivolve
kubectl describe pod <POD_NAME> -n ivolve
kubectl logs -f <POD_NAME> -n ivolve

# Check services
kubectl get svc -n ivolve
kubectl describe svc app-service -n ivolve

# Check ArgoCD sync status
kubectl get application -n argocd
argocd app list

# View CloudWatch logs
aws logs tail /aws/eks/cloud-devops-eks/cluster --follow
```

### AWS Console Monitoring

1. **EC2 Dashboard**: Check instance health
2. **EKS Dashboard**: View cluster status
3. **CloudWatch**: Monitor metrics and logs
4. **VPC Dashboard**: Network configuration

---

## 🔧 Troubleshooting

### Common Issues

#### 1. Pods Stuck in Pending
```bash
# Check node resources
kubectl describe nodes

# Check pod events
kubectl describe pod <POD_NAME> -n ivolve

# Solution: Scale down or add nodes
kubectl scale deployment app-deployment -n ivolve --replicas=1
```

#### 2. Jenkins Connection Issues
```bash
# Check security group
aws ec2 describe-security-groups --filters "Name=tag:Name,Values=*jenkins*"

# Verify Jenkins is running
ssh -i ~/.ssh/omar-key.pem ec2-user@<EC2_IP>
sudo systemctl status jenkins
```

#### 3. Docker Build Failures
```bash
# Check Dockerfile syntax
docker build --no-cache -t test .

# Check logs
docker logs <CONTAINER_ID>

# Rebuild
docker system prune -a
docker build -t ashishcb/cloud-devops-app:latest .
```

#### 4. ArgoCD Sync Issues
```bash
# Check application status
kubectl get application cloud-devops-app -n argocd -o yaml

# Force sync
argocd app sync cloud-devops-app

# Check ArgoCD logs
kubectl logs -n argocd deployment/argocd-server
```

### Useful Commands
```bash
# Reset Kubernetes deployment
kubectl delete deployment app-deployment -n ivolve
kubectl apply -f kubernetes/deployment.yaml

# Restart Jenkins
sudo systemctl restart jenkins

# Clean Docker
docker system prune -a

# Terraform state issues
terraform state list
terraform state rm <RESOURCE>
```

---

## 🧹 Cleanup

### Remove All Resources
```bash
# Delete Kubernetes resources
kubectl delete namespace ivolve
kubectl delete namespace argocd

# Delete EKS cluster
eksctl delete cluster --name cloud-devops-eks --region us-east-1

# Destroy Terraform infrastructure
cd terraform/
terraform destroy -var-file="dev.tfvars" -auto-approve

# Clean Docker
docker system prune -a -f

# Remove kubeconfig
kubectl config delete-context <CONTEXT_NAME>
```

### Cost Optimization

- Stop EC2 instances when not in use
- Delete unused EBS volumes
- Remove old Docker images from DockerHub
- Delete CloudWatch log groups if not needed

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 👤 Author

**Omar Ghaly** - Cloud & DevOps Engineer

### Connect with Me

- 🐙 **GitHub**: [@Ashish kumar](https://github.com/Ashish9123)
- 💼 **LinkedIn**: [Ashish kumar](https://linkedin.com/in/ashishkkumar91/)
- 📧 **Email**: ashishcb035@gmail.com

---

### About This Project

I'm passionate about building scalable, automated infrastructure and implementing DevOps best practices. This project demonstrates my expertise in:

- ☁️ Cloud Architecture (AWS)
- 🏗️ Infrastructure as Code (Terraform)
- 🔧 Configuration Management (Ansible)
- 🐳 Containerization (Docker)
- ☸️ Container Orchestration (Kubernetes)
- 🔄 CI/CD Pipeline Design (Jenkins)
- 📦 GitOps (ArgoCD)

**💡 Interested in collaboration or have questions about this project?**  
Feel free to reach out via any of the channels above!

---


---

<div align="center">

**⭐ If you find this project helpful, please consider giving it a star!**

Made with ❤️ by [Ashish kumar](https://github.com/Ashish9123)

</div>
