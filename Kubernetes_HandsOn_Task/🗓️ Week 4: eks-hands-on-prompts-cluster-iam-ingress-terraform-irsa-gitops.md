

### 🧭 Kubernetes Week 4: AWS EKS (Elastic Kubernetes Service) – 20 Hands-On Prompts (Beginner to Super Hard)

---

### 📝  Subtitle:
> A curated collection of AWS EKS hands-on labs with real-world backend, frontend, and fullstack scenarios—covering everything from `eksctl`, IAM integration, Terraform, IRSA, ArgoCD GitOps, OIDC, service mesh, Karpenter, and more—tailored for DevOps engineers from beginner to expert.

---

### ✅ Prompt 1: **Create an EKS Cluster Using `eksctl`**  
**🧠 Level:** Beginner  
```
🔧 I am a DevOps beginner exploring AWS EKS.  
🎯 I want to create an EKS cluster using eksctl and verify connectivity with kubectl.  
💻 Tech Stack: AWS CLI, eksctl, kubectl, Kubernetes  
📁 Structure:
eks-basics/
├── eksctl-config.yaml  

🔣 Input: Cluster name, region  
📤 Output: Working EKS cluster with valid kubeconfig  

🌍 Environment: AWS (us-east-1), macOS  
📜 Constraints: Public access, 2 nodes  
🧾 Output: CLI steps + YAML + kubectl output  
🔧 Experience Level: Beginner  
🏢 Use Case: Playground or dev cluster  
💡 I want CLI setup steps and best practices  
🚀 Deploy: eksctl  
🔐 Best Practices: Tag EKS for IAM access later  
📥 Logs: `kubectl get nodes` must return worker nodes  
🌐 Language: English
```

---

### ✅ Prompt 2: **Deploy NGINX on EKS**  
**🧠 Level:** Beginner  
```
🔧 I am learning how to deploy apps to EKS.  
🎯 I want to deploy a sample NGINX deployment and expose it using LoadBalancer.  
💻 Tech Stack: Kubernetes, AWS EKS, NGINX  
📁 Structure:
nginx-on-eks/
├── deployment.yaml  
├── service.yaml  

🔣 Input: Pod with image `nginx`, Service type: LoadBalancer  
📤 Output: Public IP exposes default NGINX page  

🌍 Environment: AWS EKS  
📜 Constraints: IAM role with EBS access not required  
🧾 Output: YAML + curl test output  
🔧 Experience Level: Beginner  
🏢 Use Case: Basic HTTP app deployment  
💡 I want best practices for exposing services  
🚀 Deploy: AWS EKS  
🔐 Best Practices: Use `externalTrafficPolicy: Local` for real IP  
📥 Logs: `kubectl get svc`, `kubectl describe`  
🌐 Language: English
```

---

### ✅ Prompt 3: **Configure kubeconfig to Access EKS**  
**🧠 Level:** Beginner  
```
🔧 I am managing access to an EKS cluster.  
🎯 I want to update kubeconfig to point to an existing EKS cluster.  
💻 Stack: AWS CLI, kubectl, EKS  
📁 Structure:
aws-config-access/
├── access-commands.md  

🔣 Input: Cluster name, AWS profile  
📤 Output: `kubectl get pods` works after config  

🌍 Environment: AWS CLI v2, macOS  
📜 Constraints: AWS credentials must be configured  
🧾 Output: CLI output from `aws eks update-kubeconfig`  
🔧 Experience Level: Beginner  
🏢 Use Case: Accessing shared dev cluster  
💡 I want command + IAM auth explanation  
🚀 Deploy: N/A – Auth config only  
🔐 Best Practices: Use named profiles for isolation  
📥 Logs: Common error `error: You must be logged in to the server`  
🌐 Language: English
```

---

### ✅ Prompt 4: **Deploy Express.js Backend on EKS with LoadBalancer**  
**🧠 Level:** Intermediate  
```
🔧 I am a backend developer.  
🎯 I want to deploy a simple Express.js API on EKS and expose it over the internet.  
💻 Tech Stack: Node.js, Express, AWS EKS, LoadBalancer  
📁 Structure:
express-on-eks/
├── Dockerfile  
├── app.js  
├── k8s/deployment.yaml  
├── k8s/service.yaml  

🔣 Input: `/hello` API endpoint  
📤 Output: Accessible via public DNS on port 80  

🌍 Environment: AWS EKS, Docker Hub  
📜 Constraints: EBS not required  
🧾 Output: Service IP + curl test  
🔧 Experience Level: Intermediate  
🏢 Use Case: Microservice demo  
💡 I want Helm + manifest hybrid deployment  
🚀 Deploy: kubectl  
🔐 Best Practices: Use liveness/readiness probes  
📥 Logs: `kubectl logs` for API validation  
🌐 Language: English
```

---

### ✅ Prompt 5: **Attach IAM Policy to EKS Node Group for EBS**  
**🧠 Level:** Intermediate  
```
🔧 I am enabling EBS access in a stateful app.  
🎯 I want to attach an IAM policy to the EKS node group to allow dynamic EBS provisioning.  
💻 Tech Stack: AWS IAM, EKS, Kubernetes StorageClass  
📁 Structure:
iam-ebs-eks/
├── policy.json  
├── nodegroup-update.md  

🔣 Input: IAM policy ARN  
📤 Output: Nodes can create EBS volumes using PVC  

🌍 Environment: AWS  
📜 Constraints: Policy must include `ec2:CreateVolume`  
🧾 Output: Verified with dynamic PVC creation  
🔧 Experience Level: Intermediate  
🏢 Use Case: Stateful workload (MongoDB)  
💡 I want CLI + IAM JSON sample  
🚀 Deploy: AWS CLI  
🔐 Best Practices: Least privilege IAM  
📥 Logs: PVC stuck in Pending → check IAM  
🌐 Language: English
```

---

### ✅ Prompt 6: **Create EKS Cluster Using Terraform**  
**🧠 Level:** Intermediate  
```
🔧 I’m a DevOps engineer automating infra.  
🎯 I want to create an EKS cluster using Terraform and verify node access.  
💻 Stack: Terraform, AWS EKS, IAM  
📁 Structure:
eks-tf-cluster/
├── main.tf  
├── outputs.tf  
├── variables.tf  

🔣 Input: Region, VPC ID, node group details  
📤 Output: EKS created and nodes accessible  

🌍 Environment: AWS, Terraform CLI  
📜 Constraints: Must use Terraform 1.0+  
🧾 Output: Terraform plan/apply logs  
🔧 Experience Level: Intermediate  
🏢 Use Case: IaC pipeline  
💡 I want modular TF example  
🚀 Deploy: Terraform  
🔐 Best Practices: Use separate state backend  
📥 Logs: Output from `kubectl get nodes`  
🌐 Language: English
```

---

### ✅ Prompt 7: **Deploy Fullstack App with EFS Persistent Storage**  
**🧠 Level:** Hard  
```
🔧 I’m a fullstack engineer deploying a React + Node.js app.  
🎯 I want to store uploaded files on EFS using a CSI driver in EKS.  
💻 Stack: React, Node.js, AWS EFS, EKS  
📁 Structure:
fullstack-efs/
├── backend/
├── frontend/
├── efs-sc.yaml  
├── pv.yaml  
├── pvc.yaml  

🔣 Input: Uploads to `/uploads`  
📤 Output: Files persist across pod restarts  

🌍 Environment: EKS with EFS CSI  
📜 Constraints: IAM role must have EFS access  
🧾 Output: UI upload → persistent file visible  
🔧 Experience Level: Hard  
🏢 Use Case: File management system  
💡 I want sample app with working mount  
🚀 Deploy: Terraform + kubectl  
🔐 Best Practices: Mount readWriteMany volumes properly  
📥 Logs: `describe pvc` if stuck  
🌐 Language: English
```

---

### ✅ Prompt 8: **Auto-Scaling Backend API on EKS Using HPA**  
**🧠 Level:** Hard  
```
🔧 I’m a backend developer with growing traffic.  
🎯 I want to use HPA to scale my Express.js API based on CPU usage.  
💻 Stack: Node.js, EKS, Metrics Server, HPA  
📁 Structure:
hpa-express/
├── deployment.yaml  
├── hpa.yaml  

🔣 Input: Load test  
📤 Output: Pods scale up and down  

🌍 Environment: EKS with Metrics Server  
📜 Constraints: CPU threshold 50%, min=2, max=5 pods  
🧾 Output: HPA status and scaling logs  
🔧 Experience Level: Hard  
🏢 Use Case: E-commerce API  
💡 I want full config + monitoring commands  
🚀 Deploy: kubectl  
🔐 Best Practices: Use `resources.requests/limits`  
📥 Logs: `kubectl describe hpa`  
🌐 Language: English
```

---

### ✅ Prompt 9: **EKS with Ingress Controller + TLS**  
**🧠 Level:** Super Advanced  
```
🔧 I’m deploying a production-ready app on EKS.  
🎯 I want to use AWS ALB Ingress Controller to expose my app via HTTPS.  
💻 Stack: AWS EKS, Ingress, ACM, Cert-Manager  
📁 Structure:
tls-ingress-app/
├── ingress.yaml  
├── service.yaml  
├── cert.yaml  

🔣 Input: Domain with SSL cert  
📤 Output: HTTPS web app with ALB  

🌍 Environment: AWS EKS, Route53, ACM  
📜 Constraints: Must have DNS validation  
🧾 Output: `curl https://app.mydomain.com`  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Secure production access  
💡 I want TLS Ingress + cert-manager combo  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Use external-dns  
📥 Logs: ALB logs, cert status  
🌐 Language: English
```

---

### ✅ Prompt 10: **OIDC Authentication for EKS Dashboard Access**  
**🧠 Level:** Super Advanced  
```
🔧 I’m enabling secure dashboard access.  
🎯 I want to integrate OIDC for EKS cluster access via AWS IAM Roles for Service Accounts.  
💻 Stack: EKS, IAM, OIDC, Kubernetes Dashboard  
📁 Structure:
oidc-auth/
├── oidc-role.yaml  
├── sa.yaml  
├── dashboard-deployment.yaml  

🔣 Input: IAM Role ARN, OIDC provider  
📤 Output: Dashboard accessible with federated auth  

🌍 Environment: AWS, EKS  
📜 Constraints: OIDC must be enabled on cluster  
🧾 Output: Login via signed token  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Secure multi-user dashboard  
💡 I want IAM + RBAC + SA setup  
🚀 Deploy: AWS CLI + kubectl  
🔐 Best Practices: Never bind admin to default SA  
📥 Logs: OIDC errors from `describe sa`  
🌐 Language: English
```


---
## 🔥 10 Super Hard AWS EKS Prompts

---

### ✅ Prompt SH1: **GitOps with ArgoCD + EKS Helm Deployment**  
**🧠 Level:** Super Hard  
```
🔧 I’m a DevOps engineer implementing GitOps.  
🎯 I want to deploy a fullstack app on AWS EKS using ArgoCD and Helm charts from a GitHub repo.  
💻 Stack: AWS EKS, ArgoCD, Helm, GitHub, Node.js, React  
📁 Structure:
eks-argocd-fullstack/
├── charts/
│   ├── frontend/
│   └── backend/
├── argocd-app.yaml  

🔣 Input: Git repo URL with Helm charts  
📤 Output: ArgoCD auto-syncs fullstack app on EKS  

🌍 Environment: AWS EKS, ArgoCD installed in `argocd` namespace  
📜 Constraints: Helm 3, public GitHub repo  
🧾 Output: ArgoCD UI reflects sync, app accessible via Ingress  
🔧 Experience Level: Super Hard  
🏢 Use Case: GitOps CI/CD for modern microservices  
💡 I want ArgoCD + Helm end-to-end GitOps setup  
🚀 Deploy: ArgoCD with Helm chart  
🔐 Best Practices: Use `syncPolicy: automated`, signed commits  
📥 Logs: ArgoCD sync status + Helm release history  
🌐 Language: English
```

---

### ✅ Prompt SH2: **Private ECR Image with IRSA-Based Pull in EKS**  
**🧠 Level:** Super Hard  
```
🔧 I’m deploying secure images to EKS.  
🎯 I want to pull images from a private ECR using IAM Roles for Service Accounts (IRSA).  
💻 Stack: AWS EKS, ECR, IAM, IRSA, Node.js  
📁 Structure:
ecr-irsa/
├── deployment.yaml  
├── serviceaccount.yaml  
├── iam-policy.json  

🔣 Input: Docker image from ECR  
📤 Output: Pod authenticates using IRSA to pull image  

🌍 Environment: AWS EKS, ECR  
📜 Constraints: Do not use static imagePullSecrets  
🧾 Output: Successful pod pull and start  
🔧 Experience Level: Super Hard  
🏢 Use Case: Secure container delivery  
💡 I want IRSA-based ECR access Helm-ready  
🚀 Deploy: AWS CLI + kubectl  
🔐 Best Practices: Least privilege IAM policy  
📥 Logs: `kubectl describe pod` → no `ImagePullBackOff`  
🌐 Language: English
```

---

### ✅ Prompt SH3: **Multi-AZ EKS with Cross-Zone Load Balancer**  
**🧠 Level:** Super Hard  
```
🔧 I am setting up a fault-tolerant cluster.  
🎯 I want to create a highly available multi-AZ EKS cluster and deploy a service with cross-zone ALB.  
💻 Stack: EKS, ALB Ingress Controller, AWS  
📁 Structure:
eks-multiaz/
├── eksctl-config.yaml  
├── deployment.yaml  
├── ingress.yaml  

🔣 Input: 3 AZs, one service, ALB across all zones  
📤 Output: App load-balanced across zones  

🌍 Environment: AWS us-east-1 with 3 AZs  
📜 Constraints: Use managed node groups, cross-zone LB  
🧾 Output: ALB DNS distributes traffic evenly  
🔧 Experience Level: Super Hard  
🏢 Use Case: Production HA workload  
💡 I want eksctl + cross-zone service config  
🚀 Deploy: eksctl + Helm + AWS CLI  
🔐 Best Practices: Use subnet tagging, monitor ALB health  
📥 Logs: ALB logs + AZ distribution test  
🌐 Language: English
```

---

### ✅ Prompt SH4: **Cluster Autoscaler with Spot + On-Demand Mix**  
**🧠 Level:** Super Hard  
```
🔧 I want to optimize EKS cost.  
🎯 I want to configure EKS with a mix of Spot and On-Demand nodes and autoscaler to prioritize spot instances.  
💻 Stack: AWS EKS, Cluster Autoscaler, EC2, Node Groups  
📁 Structure:
spot-autoscaler/
├── cluster-autoscaler.yaml  
├── nodegroups.yaml  

🔣 Input: 1 On-Demand, 2 Spot node groups  
📤 Output: Scale-up prioritizes Spot nodes  

🌍 Environment: AWS EKS  
📜 Constraints: Spot interruption handling enabled  
🧾 Output: Pods scheduled to cheapest nodes  
🔧 Experience Level: Super Hard  
🏢 Use Case: Cost-optimized autoscaling  
💡 I want Cluster Autoscaler config with Spot fallback  
🚀 Deploy: eksctl + YAML  
🔐 Best Practices: Use different taints per node group  
📥 Logs: `kubectl logs cluster-autoscaler`  
🌐 Language: English
```

---

### ✅ Prompt SH5: **Service Mesh with Istio on EKS (mTLS + Traffic Shifting)**  
**🧠 Level:** Super Hard  
```
🔧 I want to implement secure microservice networking.  
🎯 I want to deploy Istio on EKS with mutual TLS enabled and traffic shifting for two versions of a service.  
💻 Stack: EKS, Istio, Bookinfo, Helm  
📁 Structure:
eks-istio/
├── istioctl.yaml  
├── virtualservice.yaml  
├── destinationrule.yaml  

🔣 Input: v1 gets 80%, v2 gets 20%  
📤 Output: Requests routed based on weights securely with mTLS  

🌍 Environment: AWS EKS, Istio injected  
📜 Constraints: Istio sidecar injection enabled  
🧾 Output: Verified with Kiali or curl  
🔧 Experience Level: Super Hard  
🏢 Use Case: Secure and observable service communication  
💡 I want working Istio demo on EKS  
🚀 Deploy: Istioctl + Helm  
🔐 Best Practices: Use strict mTLS + peer auth policies  
📥 Logs: `istio-proxy` logs + traffic metrics  
🌐 Language: English
```

---

### ✅ Prompt SH6: **Network Policies for Pod-Level Security**  
**🧠 Level:** Super Hard  
```
🔧 I am enhancing network isolation.  
🎯 I want to implement Kubernetes NetworkPolicies in EKS to restrict pod-to-pod communication.  
💻 Stack: AWS EKS, Calico (CNI), Kubernetes  
📁 Structure:
network-policy-secure/
├── networkpolicy.yaml  
├── test-app.yaml  

🔣 Input: Deny all ingress except from specific label  
📤 Output: Only allowed pods can connect  

🌍 Environment: EKS with Calico  
📜 Constraints: Default deny policy  
🧾 Output: Test with busybox → only one succeeds  
🔧 Experience Level: Super Hard  
🏢 Use Case: Microservice isolation  
💡 I want pod-label based policy example  
🚀 Deploy: kubectl apply  
🔐 Best Practices: Default deny ingress/egress  
📥 Logs: NetworkPolicy audit logs  
🌐 Language: English
```

---

### ✅ Prompt SH7: **Secure ExternalDNS Setup with IAM via IRSA**  
**🧠 Level:** Super Hard  
```
🔧 I want DNS automation in EKS.  
🎯 I want to set up ExternalDNS on EKS using IAM Roles for Service Accounts (IRSA).  
💻 Stack: AWS EKS, Route53, IAM, ExternalDNS  
📁 Structure:
externaldns-irsa/
├── deployment.yaml  
├── serviceaccount.yaml  
├── policy.json  

🔣 Input: Hosted zone ID, service annotations  
📤 Output: DNS records auto-managed by ExternalDNS  

🌍 Environment: EKS + Route53  
📜 Constraints: IAM role must include Route53 permissions  
🧾 Output: Route53 record appears after svc creation  
🔧 Experience Level: Super Hard  
🏢 Use Case: Dynamic DNS for k8s services  
💡 I want end-to-end IRSA config  
🚀 Deploy: Helm or manifests  
🔐 Best Practices: Use restricted wildcard domain  
📥 Logs: `external-dns` pod logs  
🌐 Language: English
```

---

### ✅ Prompt SH8: **Karpenter Auto-Scaling with EC2 Spot + EBS**  
**🧠 Level:** Super Hard  
```
🔧 I want dynamic pod-based scaling in EKS.  
🎯 I want to use Karpenter to autoscale based on pod specs, using EC2 Spot and attaching EBS volumes dynamically.  
💻 Stack: AWS EKS, Karpenter, EC2 Spot, EBS  
📁 Structure:
karpenter-eks/
├── karpenter.yaml  
├── provisioner.yaml  
├── storageclass.yaml  

🔣 Input: Pod with storage claim  
📤 Output: Karpenter creates EC2 + attaches EBS automatically  

🌍 Environment: AWS EKS  
📜 Constraints: Use IRSA, EBS CSI driver  
🧾 Output: Pod starts with dynamic volume + spot node  
🔧 Experience Level: Super Hard  
🏢 Use Case: Cost-optimized dynamic workloads  
💡 I want full Karpenter + CSI config  
🚀 Deploy: Terraform or Helm  
🔐 Best Practices: EBS topology zone awareness  
📥 Logs: Karpenter controller logs  
🌐 Language: English
```

---

### ✅ Prompt SH9: **Cross-Account IAM Role Access for EKS App**  
**🧠 Level:** Super Hard  
```
🔧 I want my EKS app to access resources in another AWS account.  
🎯 I want to assume a role in Account B from a pod in Account A’s EKS cluster using IRSA.  
💻 Stack: EKS, IAM, STS, IRSA  
📁 Structure:
cross-account-irsa/
├── trust-policy.json  
├── serviceaccount.yaml  
├── deployment.yaml  

🔣 Input: Role ARN in Account B  
📤 Output: App in EKS (Account A) can assume role  

🌍 Environment: Two AWS accounts  
📜 Constraints: AssumeRole must be allowed by trust policy  
🧾 Output: STS token used successfully  
🔧 Experience Level: Super Hard  
🏢 Use Case: Multi-account AWS architecture  
💡 I want cross-account IRSA demo  
🚀 Deploy: kubectl + AWS CLI  
🔐 Best Practices: Use role sessions, rotate creds  
📥 Logs: AssumeRole STS response  
🌐 Language: English
```

---

### ✅ Prompt SH10: **Backup EKS Cluster Using Velero with S3**  
**🧠 Level:** Super Hard  
```
🔧 I want to set up disaster recovery for EKS.  
🎯 I want to back up and restore Kubernetes resources using Velero with AWS S3.  
💻 Stack: AWS EKS, Velero, S3, IAM  
📁 Structure:
eks-velero-backup/
├── backup.yaml  
├── restore.yaml  
├── velero-install.sh  

🔣 Input: Deployment and PVCs  
📤 Output: Backup stored in S3, restorable later  

🌍 Environment: AWS EKS, S3  
📜 Constraints: IAM for Velero with S3 access  
🧾 Output: CLI status from `velero backup get`  
🔧 Experience Level: Super Hard  
🏢 Use Case: EKS disaster recovery  
💡 I want backup + restore flow  
🚀 Deploy: Velero Helm chart  
🔐 Best Practices: Encrypt S3 bucket, use lifecycle rules  
📥 Logs: Velero pod logs + S3 confirmation  
🌐 Language: English
```

---

✅ Let me know if you’d like:
- A **markdown export** of all 20 (Beginner → Super Hard + SH1–SH10)?
- **Terraform modules**, **YAML templates**, or **Helm charts** for any of the prompts?
- Or ready-to-execute versions as GitHub folders?


