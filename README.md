# AWS EKS Production Platform

![AWS](https://img.shields.io/badge/AWS-EKS-orange)
![Terraform](https://img.shields.io/badge/Terraform-IaC-purple)
![Docker](https://img.shields.io/badge/Docker-Containers-blue)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-blue)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI/CD-green)
![Amazon ECR](https://img.shields.io/badge/Amazon-ECR-yellow)
![Amazon ALB](https://img.shields.io/badge/AWS-ALB-red)

## Overview

A production-style Kubernetes platform built on Amazon EKS using Terraform, Docker, Amazon ECR, GitHub Actions, AWS Load Balancer Controller, and Application Load Balancers (ALB).

This project demonstrates modern DevOps practices including Infrastructure as Code (IaC), containerization, Kubernetes orchestration, CI/CD automation, and cloud-native application deployment on AWS.

---

## Architecture

![Architecture Diagram](architecture/architecture-diagram.png)




---
### Request Flow

1. Developer pushes code to GitHub
2. GitHub Actions builds Docker image
3. Image is pushed to Amazon ECR
4. GitHub Actions updates Amazon EKS
5. Pods pull image from ECR
6. Ingress routes traffic
7. AWS Load Balancer Controller manages ALB
8. Users access application through ALB
   
---
```text
GitHub
   │
   ▼
GitHub Actions
   │
   ▼
Amazon ECR
   │
   ▼
Amazon EKS
   │
   ▼
AWS Load Balancer Controller
   │
   ▼
Application Load Balancer (ALB)
   │
   ▼
Kubernetes Service
   │
   ▼
Pods
```

---

## Technologies Used

### Cloud

* Amazon Web Services (AWS)
* Amazon EKS
* Amazon ECR
* IAM
* VPC
* Application Load Balancer (ALB)

### Infrastructure as Code

* Terraform

### Containerization

* Docker

### Kubernetes

* Deployments
* Services
* Ingress
* AWS Load Balancer Controller
* IRSA (IAM Roles for Service Accounts)

### CI/CD

* GitHub Actions

---

## Features

### Infrastructure Provisioning

* Custom VPC
* Public Subnets
* Private Subnets
* Internet Gateway
* NAT Gateway
* Route Tables
* IAM Roles and Policies

### Kubernetes Platform

* Amazon EKS Cluster
* Managed Node Groups
* Namespace Management
* Deployments
* Services
* Ingress Resources

### Container Registry

* Amazon ECR Integration
* Automated Image Storage

### Continuous Integration / Continuous Deployment

* GitHub Actions Pipeline
* Automated Docker Build
* Automated ECR Push
* Automated EKS Deployment

---

## Repository Structure

```text
aws-eks-production-platform/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── app/
│   ├── Dockerfile
│   └── index.html
├── kubernetes/
│   ├── deployment.yaml
│   ├── ingress.yaml
│   ├── namespaces.yaml
│   └── service.yaml
├── terraform/
│   ├── eks.tf
│   ├── iam.tf
│   ├── node-groups.tf
│   ├── outputs.tf
│   ├── providers.tf
│   ├── variables.tf
│   ├── versions.tf
│   └── vpc.tf
└── README.md
```

---

## CI/CD Workflow

The deployment pipeline automatically executes whenever code is pushed to the master branch.

### Workflow Steps

1. Checkout source code
2. Configure AWS credentials
3. Authenticate with Amazon ECR
4. Build Docker image
5. Push image to Amazon ECR
6. Update Kubernetes deployment
7. Roll out application to Amazon EKS

---

## Infrastructure Provisioning

### Initialize Terraform

```bash
terraform init
```

### Validate Configuration

```bash
terraform validate
```

### Deploy Infrastructure

```bash
terraform apply
```

### Destroy Infrastructure

```bash
terraform destroy
```

---

## Kubernetes Deployment

### Deploy Application

```bash
kubectl apply -f kubernetes/
```

### Verify Pods

```bash
kubectl get pods -n production
```

### Verify Ingress

```bash
kubectl get ingress -n production
```

---

## Project Achievements

* Built AWS infrastructure using Terraform
* Provisioned Amazon EKS cluster
* Implemented AWS Load Balancer Controller
* Configured ALB-based Ingress
* Containerized application using Docker
* Stored images in Amazon ECR
* Automated deployment using GitHub Actions
* Implemented production-style Kubernetes architecture

---

## Future Enhancements

* Prometheus Monitoring
* Grafana Dashboards
* Loki Logging
* ArgoCD GitOps
* Route53 Integration
* SSL/TLS with ACM
* Helm Chart Packaging
* Blue/Green Deployments
* Canary Releases

---

## Project Screenshots

Terraform Apply Success
kubectl get nodes
GitHub Actions Successful Run
ECR Repository
ALB Ingress Output
Final Application Page
EKS Cluster in AWS Console

## Project Screenshots

### Terraform Infrastructure Outputs

The Terraform deployment successfully provisioned the AWS infrastructure, including the VPC, subnets, IAM roles, NAT Gateway, and EKS cluster.

![Terraform Outputs](screenshots/terraform-output.png)

---

### EKS Worker Nodes

Both managed worker nodes successfully joined the EKS cluster and are in the Ready state.

![EKS Worker Nodes](screenshots/eks-worker-nodes.png)

---

### AWS Application Load Balancer (ALB) Ingress

The AWS Load Balancer Controller automatically provisioned an Application Load Balancer and associated it with the Kubernetes Ingress resource.

![ALB Ingress](screenshots/alb-ingress.png)

---

### GitHub Actions CI/CD Pipeline

Successful GitHub Actions workflow execution showing automated build and deployment to Amazon EKS.

![GitHub Actions](screenshots/github-actions-success.png)

---

### Amazon ECR Repository

Container images are stored and versioned in Amazon Elastic Container Registry (ECR).

![Amazon ECR](screenshots/ecr-repository.png)

---

### Amazon EKS Cluster

Amazon EKS cluster running in Active state with managed worker nodes.

![Amazon EKS Cluster](screenshots/eks-cluster.png)

---

### Application Running Through AWS ALB

The application is accessible through the AWS Application Load Balancer provisioned by the AWS Load Balancer Controller.

![Application Running](screenshots/application-running-through-alb.png)

---

## Author

### Babatunde Ayo

DevOps Engineer | AWS Cloud Engineer | Software Developer

- GitHub: [@digimind34](https://github.com/digimind34)
- Portfolio: [DigimindIT](https://digimindit.com)
- LinkedIn: Add your LinkedIn profile URL here
```
