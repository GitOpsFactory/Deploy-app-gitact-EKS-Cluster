# 🚀 CI/CD Pipeline: GitHub Actions → Amazon ECR → Amazon EKS

## 📌 Project Overview

This project demonstrates an end-to-end CI/CD pipeline that automates the deployment of a containerized application to Amazon EKS using GitHub Actions.

The pipeline securely authenticates with AWS using GitHub OpenID Connect (OIDC), builds a Docker image, pushes it to Amazon Elastic Container Registry (ECR), and performs a rolling deployment to an Amazon EKS cluster. The application is exposed through an AWS Application Load Balancer (ALB) provisioned automatically by the AWS Load Balancer Controller.

---

## 🏗️ Architecture

```
Developer
    │
    │ Git Push
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Authenticate using GitHub OIDC
    ├── Assume IAM Role
    ├── Build Docker Image
    ├── Push Image to Amazon ECR
    ├── Update kubeconfig
    └── Deploy to Amazon EKS
            │
            ▼
      Kubernetes Deployment
            │
            ▼
        Rolling Update
            │
            ▼
      AWS Load Balancer Controller
            │
            ▼
Application Load Balancer (ALB)
            │
            ▼
          End Users
```

---

## 🚀 Features

- Automated CI/CD using GitHub Actions
- Secure authentication with AWS using GitHub OIDC
- Docker image build and push to Amazon ECR
- Automated deployment to Amazon EKS
- Kubernetes Rolling Updates with zero/minimal downtime
- Application exposed through AWS Application Load Balancer
- Infrastructure follows AWS security best practices

---

## 🛠️ Technologies Used

- Amazon EKS
- Amazon ECR
- AWS IAM
- GitHub Actions
- GitHub OIDC
- Docker
- Kubernetes
- AWS Load Balancer Controller
- Application Load Balancer (ALB)
- AWS CLI
- kubectl

---

## 📂 Workflow

1. Developer pushes code to the `main` branch.
2. GitHub Actions workflow is triggered.
3. GitHub authenticates to AWS using OIDC.
4. Docker image is built.
5. Image is pushed to Amazon ECR.
6. kubeconfig is updated for the EKS cluster.
7. Kubernetes Deployment is updated with the new image.
8. Rolling update deploys new Pods.
9. Application remains accessible through the AWS ALB.

---

## 🔐 Security

- GitHub OIDC authentication (no long-lived AWS access keys)
- IAM Role with least-privilege permissions
- Amazon EKS Access Entries for cluster authorization
- AWS Security Groups for network protection
- Kubernetes RBAC support

---

## 📖 Learning Outcomes

- Deploy applications to Amazon EKS
- Configure GitHub Actions CI/CD pipelines
- Push Docker images to Amazon ECR
- Implement GitHub OIDC authentication
- Perform rolling deployments on Kubernetes
- Configure AWS Load Balancer Controller
- Understand EKS networking and traffic flow

---

## 📸 Result

The application is automatically deployed to Amazon EKS after every successful push to the `main` branch. Kubernetes performs a rolling update, and the application is served through an AWS Application Load Balancer without manual intervention.
