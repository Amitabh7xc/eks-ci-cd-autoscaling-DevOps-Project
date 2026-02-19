# Cloud-Native E-Commerce Platform on AWS EKS
Production-Style Infrastructure • CI Automation • Kubernetes Autoscaling

A cloud-native DevOps implementation on Amazon EKS that demonstrates infrastructure automation, CI/CD integration, autoscaling, and observability in a production-inspired architecture.

This project focuses on building a resilient, reproducible, and observable Kubernetes platform — not just deploying containers.

## 🏗 Architecture Overview

This repository provisions AWS infrastructure using Terraform and deploys a containerized e-commerce application to EKS through a Jenkins-driven CI pipeline.

The Platform Includes

✅ Automated AWS infrastructure provisioning

✅ Containerized frontend & backend services

✅ CI-driven Kubernetes deployments

✅ Horizontal Pod Autoscaling (HPA)

✅ Full monitoring stack (Prometheus + Grafana)

The objective: reliability, repeatability, and operational visibility.

## 🛠 Tech Stack
☁ Cloud & Infrastructure

AWS (VPC, Subnets, NAT Gateway, IAM, EC2, EKS)

Terraform (Modular Infrastructure as Code)

### 📦 Containers & Orchestration

Docker

Kubernetes (EKS)

Horizontal Pod Autoscaler (HPA)

### 🔁 CI Pipeline

Jenkins

Docker Hub

### 📊 Observability

Prometheus

Grafana

Helm

### ⚙ Automation

Bash

kubectl

AWS CLI

### 🚀 Core Capabilities
### 1️⃣ Infrastructure as Code

Modular Terraform setup for:

VPC & networking

IAM roles & policies

EKS cluster provisioning

Jenkins EC2 deployment

Designed for reproducible, environment-ready infrastructure.

### 2️⃣ CI → Kubernetes Integration

The Jenkins pipeline:

Pulls source code

Builds Docker images (frontend & backend)

Pushes images to Docker Hub

Deploys directly to EKS using kubectl

Simulates real-world CI-to-cluster workflows.

### 3️⃣ Kubernetes Workload Design

Independent frontend & backend deployments

Namespace isolation

Service exposure configuration

Resource definitions aligned with scaling policies

### 4️⃣ Intelligent Autoscaling

HPA configured per workload

CPU-based scaling strategy

Automatic replica adjustments under load

### 5️⃣ Observability Stack

Prometheus deployed via Helm

Metrics collection using ServiceMonitor

Grafana dashboards for:

Pod health

Resource utilization

Scaling behavior

Application monitoring

Observability was treated as a core design principle — not an afterthought.

### 🔄 Deployment Flow
Step 1: Infrastructure Provisioning

Terraform provisions:

Networking layer

IAM configuration

EKS cluster

Jenkins EC2 instance

Bootstrap scripts configure required tooling (Docker, Jenkins, kubectl, AWS CLI).

Step 2: Continuous Integration

Jenkins pipeline automates:

Image builds

Registry push

Kubernetes manifest deployment

No manual kubectl operations required post-setup.

Step 3: Runtime & Scaling

Kubernetes manages services & deployments

HPA dynamically adjusts replicas

Prometheus collects metrics

Grafana visualizes system health

### 🧠 Engineering Challenges & Lessons
Terraform Execution & Dependencies

Refactored modules

Defined explicit dependencies

Used targeted applies during debugging

EKS IAM & Authentication

Corrected aws-auth role mappings

Built validation scripts for cluster access

Jenkins + Docker Permissions

Fixed EC2 user group permissions

Verified Docker daemon accessibility

Monitoring Configuration Issues

Corrected ServiceMonitor selectors

Fixed namespace & RBAC misconfigurations

Terraform State Management

Learned why state files should not be version-controlled

Planned migration to S3 + DynamoDB remote backend

## 📈 Key Takeaways

Writing resilient Terraform configurations

Deep IAM understanding within EKS

Building CI pipelines that interact directly with Kubernetes

Debugging multi-layer DevOps failures

Designing autoscaling strategies based on real metrics

Treating observability as a system requirement

## 🔭 Roadmap

Planned enhancements:

GitHub Actions-based CI

ArgoCD (GitOps deployment)

Helm-based application packaging

AWS Secrets Manager / Vault integration

Remote Terraform state backend

Multi-environment support (dev/stage/prod)

Security hardening

## ▶ Getting Started

Provision infrastructure with Terraform

Access Jenkins on the EC2 instance

Trigger the pipeline

Validate deployed services

Monitor scaling & metrics via Grafana

## 🎯 Project Philosophy

This project represents a shift from tool usage to platform engineering mindset:

Designing reproducible infrastructure

Building resilient CI/CD workflows

Observing real system behavior

Debugging systematically

Improving architecture iteratively

It is not just a Kubernetes demo — it is a cloud-native systems implementation.
