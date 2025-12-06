# AWS Enterprise EKS Platform (Infrastructure as Code)

This project demonstrates the provisioning of a **production-grade Kubernetes Cluster (EKS)** on AWS using **Terraform**. It establishes a secure VPC network foundation and deploys a managed Control Plane with self-healing Worker Nodes.

## 🚀 Project Architecture
* **Infrastructure as Code:** Terraform (State management, Modules).
* **Cloud Provider:** AWS (US-East-1 Region).
* **Orchestration:** Amazon EKS (Elastic Kubernetes Service) v1.30.
* **Networking:** Custom VPC with Public/Private subnets and NAT Gateways.
* **Compute:** Managed Node Groups using EC2 (t3.medium).

## 📸 Deployment Evidence

### 1. EKS Control Plane (Active)
*Successfully provisioned the Managed Control Plane using Terraform.*
![EKS Dashboard](images/eks-dashboard.png)

### 2. EC2 Worker Nodes
*Two worker nodes automatically provisioned and joined to the cluster.*
![Worker Nodes](images/worker-nodes.png)

### 3. CLI Verification
*Verifying node health and connectivity using `kubectl`.*
![Terminal Output](images/terminal-output.png)

## 🛠️ How to Deploy
1.  **Configure AWS Credentials:**
    ```bash
    aws configure
    ```
2.  **Initialize Terraform:**
    ```bash
    cd terraform
    terraform init
    ```
3.  **Apply Infrastructure:**
    ```bash
    terraform apply -auto-approve
    ```
4.  **Connect to Cluster:**
    ```bash
    aws eks update-kubeconfig --region us-east-1 --name jubeth-cluster
    ```

## ⚠️ Cost Management
This project uses real cloud resources. To avoid charges, destroy infrastructure immediately after use:
```bash
terraform destroy -auto-approve