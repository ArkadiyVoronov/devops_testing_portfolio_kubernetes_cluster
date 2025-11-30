# DevOps Testing Portfolio: Kubernetes Cluster

This project demonstrates how to provision and manage a Kubernetes cluster entirely through **GitHub Actions**, using **Infrastructure as Code (IaC)** principles.

## 🎯 Goal
Automate the deployment of a functional Kubernetes cluster (e.g., on AWS, GCP, or a local VM setup) triggered by Git pushes or manual workflows — ideal for testing, demos, or portfolio展示.

## 🔧 Technologies Used
- **GitHub Actions** — CI/CD orchestration
- **Terraform** or **CloudFormation** — Infrastructure provisioning
- **Kubeadm / K3s / Kind / EKS / GKE** — Kubernetes deployment (configurable)
- **Ansible** (optional) — Configuration and post-setup tasks
- **Docker** — Container runtime

## 🚀 How It Works
1. Push code to the repository (or trigger manually).
2. GitHub Actions workflow:
   - Provisions cloud resources (VMs, VPC, etc.).
   - Installs and configures Kubernetes.
   - Optionally deploys a test app or runs conformance checks.
3. Cluster details (kubeconfig, endpoints) are stored as workflow artifacts or sent securely via encrypted secrets.

> 💡 Designed for learning, testing, and showcasing DevOps automation skills — **not for production use** without hardening.



## ▶️ Getting Started
1. Fork this repository.
2. Set required secrets in **Settings → Secrets and variables → Actions** (e.g., `AWS_ACCESS_KEY_ID`, `SSH_PRIVATE_KEY`).
3. Push a change — or run the workflow manually from the **Actions** tab.

> 🔐 **Security note**: Always restrict secrets and never expose kubeconfig publicly.

---

## ▶️ Getting Started
1. Fork this repository.
2. Set required secrets in **Settings → Secrets and variables → Actions** (e.g., `AWS_ACCESS_KEY_ID`, `SSH_PRIVATE_KEY`).
3. Push a change — or run the workflow manually from the **Actions** tab.

> 🔐 **Security note**: Always restrict secrets and never expose kubeconfig publicly.

---
