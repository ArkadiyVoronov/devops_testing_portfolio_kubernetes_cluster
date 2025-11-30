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

## 🚀 What This Project Demonstrates

This repository automates the **provisioning of a single-node Kubernetes cluster (K3s)** directly inside a GitHub Actions runner.

- ✅ Fully automated via GitHub Actions
- ✅ Installs K3s and configures `kubectl`
- ✅ Runs a **1-minute health-check loop** to simulate monitoring
- ✅ Exposes cluster state via workflow logs and artifacts
- ⚠️ **For demo/learning only** — cluster is destroyed after workflow ends

Ideal for showcasing **infrastructure automation**, **Kubernetes basics**, and **observability patterns** in CI/CD pipelines.

## 🚀 Kubernetes Deployment & Monitoring Demo

This repository demonstrates a fully automated **single-node Kubernetes (K3s) cluster deployment** inside a GitHub Actions runner, followed by a **1-minute synthetic health check loop**.

### ✨ Features
- ✅ Installs K3s and configures `kubectl` in under 20 seconds
- ✅ Deploys a test `nginx` application
- ✅ Runs **6 health checks over 1 minute** (every 10s):
  - Node and pod status via `kubectl`
  - HTTP connectivity test via `curl` to the nginx service
- ✅ **Sends deployment status to Telegram** (success/failure)
- ✅ Exports encrypted `kubeconfig` as a workflow artifact (for audit/demo)

> ⚠️ **Note**: The cluster runs inside the ephemeral GitHub Actions runner and is **destroyed after the workflow ends**. This is intended for **demonstration, testing, and DevOps portfolio purposes only** — not for production workloads.

### 🔔 Telegram Notifications
Upon completion, the workflow sends a message to your Telegram channel or chat with:
- Workflow status (✅ Success / ❌ Failure)
- Commit hash and branch
- Duration and link to the run

To enable this, add your Telegram bot token and chat ID as secrets (see [Setup](#setup)).

### 📂 Artifacts
After each run, you can download:
- `local-kubeconfig.gpg` — encrypted Kubernetes config (decrypt with your passphrase)
