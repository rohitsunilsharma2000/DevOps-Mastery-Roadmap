
---

# **Phase 4: Infrastructure as Code (4 Weeks)**

## **Week 1: Terraform Fundamentals**

### Topics:
- What is Infrastructure as Code (IaC)?
- Installing Terraform CLI
- Understanding providers (e.g., AWS)
- Resources, variables, and outputs
- Writing your first `.tf` file to:
  - Provision an EC2 instance
  - Create an S3 bucket

### Hands-On Tasks:
- Install Terraform and configure AWS credentials
- Create a `main.tf` that provisions:
  - An EC2 instance
  - An S3 bucket
  - Use `terraform apply`, `destroy`, and `plan`
- Learn input variables & output values (`variables.tf`, `outputs.tf`)

### Resources:
- [Terraform Getting Started Guide](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
- [Terraform AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)

---

## **Week 2: Modules & State Management**

### Topics:
- Organizing code into modules (reusable pieces)
- Calling modules in `main.tf`
- Terraform backends and state
- Remote state in S3 with state locking via DynamoDB

### Hands-On Tasks:
- Refactor existing code into modules (VPC, EC2, S3)
- Set up an S3 bucket and DynamoDB table
- Configure backend in Terraform using:
  ```hcl
  terraform {
    backend "s3" {
      bucket         = "your-terraform-state"
      key            = "dev/terraform.tfstate"
      region         = "us-east-1"
      dynamodb_table = "terraform-lock"
    }
  }
  ```

### Resources:
- [Terraform Modules](https://developer.hashicorp.com/terraform/language/modules)
- [Remote State Management](https://developer.hashicorp.com/terraform/tutorials/state/state-remote)

---

## **Week 3: Provisioning Real Infra (VPC, IAM, EKS)**

### Topics:
- Provisioning a full VPC: subnets, route tables, gateways
- Creating IAM roles and policies
- Creating EKS cluster using Terraform

### Hands-On Tasks:
- Use Terraform to:
  - Create a full VPC (public/private subnets, NAT, IGW)
  - Create IAM roles and attach policies
  - Provision an EKS cluster
- Install `kubectl` and `aws-iam-authenticator`
- Connect to EKS via kubeconfig

### Resources:
- [Terraform VPC Module](https://registry.terraform.io/modules/terraform-aws-modules/vpc/aws/latest)
- [Terraform EKS Module](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest)
- [AWS IAM Terraform Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role)

---

## **Week 4: GitOps with ArgoCD / FluxCD**

### Topics:
- What is GitOps?
- ArgoCD vs FluxCD: Concepts & architecture
- Installing ArgoCD in your EKS cluster using Helm
- Syncing an app from GitHub to Kubernetes
- Managing Helm charts declaratively

### Hands-On Tasks:
- Deploy ArgoCD to EKS using Helm:
  ```bash
  helm repo add argo https://argoproj.github.io/argo-helm
  helm install argo-cd argo/argo-cd -n argocd --create-namespace
  ```
- Configure Git repo as a source in ArgoCD
- Use `Application` YAML to deploy a sample app (e.g., nginx)
- Try the same using FluxCD (optional)

### Resources:
- [ArgoCD Quick Start](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [FluxCD Docs](https://fluxcd.io/docs/)
- [Helm Charts](https://artifacthub.io/)

---

