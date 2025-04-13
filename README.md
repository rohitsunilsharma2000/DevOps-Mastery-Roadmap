
---

## **DevOps Mastery Roadmap**

### **Duration**: ~4-5 Months  
### **Goal**: Master AWS, Kubernetes, Terraform, GitOps, CI/CD, and Observability

---

## **Phase 1: Foundations (2–3 weeks)**

### Topics:
- Linux (bash, permissions, file system, SSH)
- Networking (IP, DNS, HTTP, ports, OSI model)

### Resources:
- [Linux Journey](https://linuxjourney.com/)
- [Networking Fundamentals – Roadmap.sh](https://roadmap.sh/devops)

---

## **Phase 2: AWS Core Services (4 weeks)**

### Topics:
- **EC2**: Key pairs, volumes, AMIs
- **IAM**: Policies, roles, groups
- **VPC**: Subnets, routing, NAT, IGW
- **CloudWatch**: Logs, metrics, alarms
- **Load Balancers**: ALB, NLB

### Tools:
- AWS Console, AWS CLI, Terraform (basic)

### Resources:
- [AWS Official Docs](https://docs.aws.amazon.com/)
- [Free AWS Training](https://explore.skillbuilder.aws/)

---

## **Phase 3: Kubernetes Mastery (6–8 weeks)**

### Topics:
- Kubernetes fundamentals (`kubectl`, pods, deployments, services)
- Helm
- EKS cluster setup (using `eksctl` or Terraform)
- **Karpenter** for autoscaling
- Namespaces, Ingress, RBAC
- Bonus: **Fargate**, **KEDA**, **Cluster Autoscaler**

### Resources:
- [Kubernetes Docs](https://kubernetes.io/docs/)
- [CKA Official Curriculum](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/)
- [Karpenter on AWS](https://karpenter.sh/docs/)

---

## **Phase 4: Infrastructure as Code (4 weeks)**

### Topics:
- Terraform basics: resources, variables, modules
- State management (remote backend: S3 + DynamoDB)
- Provisioning: EC2, IAM, VPC, EKS
- GitOps: **ArgoCD**, **FluxCD**

### Resources:
- [Terraform Docs](https://developer.hashicorp.com/terraform)
- [ArgoCD Docs](https://argo-cd.readthedocs.io/)
- [FluxCD](https://fluxcd.io/)

---

## **Phase 5: CI/CD Pipelines (3–4 weeks)**

### Tools:
- GitHub Actions
- Jenkins Pipelines
- AWS CodePipeline + CodeBuild

### Topics:
- Build, Test, Deploy pipelines
- Dockerized CI/CD agents
- Deploying to EKS using CI/CD

### Resources:
- [Jenkins Docs](https://www.jenkins.io/doc/)
- [GitHub Actions](https://docs.github.com/en/actions)

---

## **Phase 6: Observability & Monitoring (3 weeks)**

### Tools:
- CloudWatch
- Prometheus + Grafana

### Topics:
- Logs, metrics, dashboards
- Helm install Prometheus stack
- Custom alerts, service monitoring

### Resources:
- [Prometheus Docs](https://prometheus.io/docs/)
- [Grafana Docs](https://grafana.com/docs/)

---

## **Certifications to Target**

| Certification | Recommended After |
|---------------|-------------------|
| AWS DevOps Pro | Phase 5 |
| Terraform Associate | Phase 4 |
| CKA / CKAD | Phase 3 |

---

## **Hands-on Projects (Ongoing)**

1. Deploy a full-stack app on EKS using Terraform
2. CI/CD pipeline with GitHub Actions or Jenkins + ArgoCD
3. Setup Karpenter with spot instances
4. Monitor app with Prometheus + Grafana

---

