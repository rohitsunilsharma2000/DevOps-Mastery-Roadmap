## 📌 Real-World Projects & CKA Prep – 10 Hands-On Prompts (Beginner to Super Advanced)**

### 📝 Optional Subtitle:
> Deploy fullstack apps, autoscale with KEDA and Karpenter, automate EKS infra with Terraform, implement CI/CD with GitHub Actions + Helm, and prepare for real CKA-style challenges.
---

### ✅ Prompt 1: **Basic EKS Cluster with Terraform**
**🧠 Level:** Beginner  
```
🔧 I’m a beginner learning infrastructure as code.  
🎯 I want to create a basic EKS cluster using Terraform.  
💻 Stack: AWS, Terraform, EKS  
📁 Structure:
eks-tf/
├── main.tf  
├── variables.tf  
├── outputs.tf  

🔣 Input: Region, cluster name  
📤 Output: EKS cluster with public access and 2 nodes  

🌍 Environment: AWS CLI, Terraform v1.3+  
📜 Constraints: Use managed node group  
🧾 Output: Terraform plan + kubectl config access  
🔧 Experience Level: Beginner  
🏢 Use Case: IaC setup for dev team  
💡 I want reusable Terraform code  
🚀 Deploy: Terraform  
🔐 Best Practices: Use remote backend for state  
📥 Logs: Terraform output logs  
🌐 Language: English
```

---

### ✅ Prompt 2: **Deploy Backend App on EKS with Karpenter Scaling**
**🧠 Level:** Intermediate  
```
🔧 I’m deploying a backend service on EKS.  
🎯 I want to autoscale backend pods using HPA, and nodes using Karpenter.  
💻 Stack: Node.js, EKS, Karpenter, HPA  
📁 Structure:
backend-autoscale/
├── app.js  
├── Dockerfile  
├── deployment.yaml  
├── hpa.yaml  
├── provisioner.yaml  

🔣 Input: CPU-based HPA  
📤 Output: Backend scales pods and nodes dynamically  

🌍 Environment: AWS EKS  
📜 Constraints: Karpenter IAM + metrics server  
🧾 Output: `kubectl get hpa` + new EC2 nodes  
🔧 Experience Level: Intermediate  
🏢 Use Case: Production-grade API  
💡 I want HPA + Karpenter setup  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Use taints, node selectors  
📥 Logs: `top pods`, Karpenter logs  
🌐 Language: English
```

---

### ✅ Prompt 3: **Ingress + TLS for a Fullstack App on EKS**
**🧠 Level:** Intermediate  
```
🔧 I’m deploying a fullstack SaaS app.  
🎯 I want to expose a React + Express app via NGINX Ingress with TLS using cert-manager.  
💻 Stack: React, Express, Ingress, cert-manager, AWS EKS  
📁 Structure:
fullstack-tls/
├── backend/  
├── frontend/  
├── ingress.yaml  
├── certificate.yaml  

🔣 Input: HTTPS on `app.mydomain.com`  
📤 Output: Fullstack app secured with TLS  

🌍 Environment: AWS EKS with cert-manager  
📜 Constraints: Requires working DNS and issuer  
🧾 Output: Public HTTPS URL + cert status  
🔧 Experience Level: Intermediate  
🏢 Use Case: Multi-user web portal  
💡 I want Ingress + cert-manager + fullstack chart  
🚀 Deploy: Helm  
🔐 Best Practices: Use Let's Encrypt staging for testing  
📥 Logs: cert-manager logs  
🌐 Language: English
```

---

### ✅ Prompt 4: **CI/CD Pipeline with GitHub Actions + Helm to EKS**
**🧠 Level:** Intermediate  
```
🔧 I want to automate deployments to EKS.  
🎯 I want to build a CI/CD pipeline using GitHub Actions that builds and deploys a Dockerized app to EKS using Helm.  
💻 Stack: GitHub Actions, Docker, Helm, EKS  
📁 Structure:
ci-cd-eks/
├── .github/workflows/deploy.yaml  
├── Chart.yaml  
├── Dockerfile  
├── values.yaml  

🔣 Input: Git push  
📤 Output: App deployed via Helm to EKS  

🌍 Environment: GitHub + EKS access token  
📜 Constraints: Auth via OIDC or AWS credentials  
🧾 Output: Actions job status + Helm release  
🔧 Experience Level: Intermediate  
🏢 Use Case: Dev → Staging automation  
💡 I want full CI/CD YAML  
🚀 Deploy: GitHub Actions  
🔐 Best Practices: Use secrets, not hardcoded keys  
📥 Logs: GitHub build logs + Helm diff  
🌐 Language: English
```

---

### ✅ Prompt 5: **Custom HPA Using Prometheus Metrics (Request Rate)**
**🧠 Level:** Hard  
```
🔧 I want autoscaling based on custom metrics.  
🎯 I want to scale a backend API based on HTTP request rate using Prometheus + Adapter.  
💻 Stack: Node.js, Prometheus, HPA, EKS  
📁 Structure:
hpa-prometheus/
├── deployment.yaml  
├── prometheus-rule.yaml  
├── hpa.yaml  

🔣 Input: `http_requests_total` metric  
📤 Output: More pods when QPS > 100  

🌍 Environment: EKS + kube-prometheus-stack  
📜 Constraints: MetricAdapter must be configured  
🧾 Output: HPA scales on QPS  
🔧 Experience Level: Hard  
🏢 Use Case: High-traffic APIs  
💡 I want HPA with external metrics  
🚀 Deploy: Helm  
🔐 Best Practices: Use safe thresholds  
📥 Logs: Prometheus adapter logs  
🌐 Language: English
```

---

### ✅ Prompt 6: **SQS-Driven Worker Autoscaling with KEDA**
**🧠 Level:** Hard  
```
🔧 I want to scale consumers on-demand.  
🎯 I want to configure KEDA to scale a consumer pod when AWS SQS message count increases.  
💻 Stack: AWS SQS, EKS, KEDA, Node.js  
📁 Structure:
keda-sqs-scale/
├── scaledobject.yaml  
├── deployment.yaml  
├── sqs-listener.js  
├── serviceaccount.yaml  

🔣 Input: 100+ SQS messages  
📤 Output: Pods scale up to consume  

🌍 Environment: AWS EKS with IRSA  
📜 Constraints: SQS + IAM setup  
🧾 Output: Scaling events from KEDA  
🔧 Experience Level: Hard  
🏢 Use Case: Event-driven background job  
💡 I want KEDA + IRSA example  
🚀 Deploy: Helm  
🔐 Best Practices: Rate-limit concurrency  
📥 Logs: SQS poller logs  
🌐 Language: English
```

---

### ✅ Prompt 7: **GitHub PR-Based Preview Environments on EKS**
**🧠 Level:** Super Advanced  
```
🔧 I want on-demand staging environments.  
🎯 I want to create ephemeral EKS namespaces via GitHub Actions on each pull request.  
💻 Stack: GitHub Actions, Helm, EKS, React, Node.js  
📁 Structure:
preview-environments/
├── .github/workflows/pr-env.yaml  
├── helm/  
│   ├── frontend/  
│   └── backend/  

🔣 Input: GitHub pull request  
📤 Output: Unique preview environment with PR ID  

🌍 Environment: EKS + dynamic namespace  
📜 Constraints: Namespace auto-cleanup  
🧾 Output: Preview URL in PR comments  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Review feature branches  
💡 I want GitHub Actions + Helm automation  
🚀 Deploy: GitHub Actions  
🔐 Best Practices: Enforce cleanup on merge  
📥 Logs: GitHub workflow logs  
🌐 Language: English
```

---

### ✅ Prompt 8: **Production-Grade EKS Setup with Terraform + Karpenter + TLS**
**🧠 Level:** Super Advanced  
```
🔧 I want a fully automated production EKS setup.  
🎯 I want to provision EKS using Terraform, autoscale with Karpenter, and expose apps via TLS ingress.  
💻 Stack: Terraform, EKS, Karpenter, cert-manager  
📁 Structure:
prod-eks-terraform/
├── terraform/  
├── karpenter/  
├── ingress.yaml  
├── certificate.yaml  

🔣 Input: DNS + cluster config  
📤 Output: EKS + Ingress + autoscaling + TLS  

🌍 Environment: AWS  
📜 Constraints: Requires VPC, domain, ACM  
🧾 Output: Full production-ready deployment  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Scalable SaaS foundation  
💡 I want end-to-end automation  
🚀 Deploy: Terraform + Helm  
🔐 Best Practices: Use OIDC + IRSA + sealed secrets  
📥 Logs: Karpenter + cert-manager logs  
🌐 Language: English
```

---

### ✅ Prompt 9: **Real-Time WebSocket Chat App with KEDA and Scaling**
**🧠 Level:** Super Advanced  
```
🔧 I want to build a real-time chat backend.  
🎯 I want to scale WebSocket servers using KEDA based on Redis PubSub queue length.  
💻 Stack: Node.js, Redis, WebSocket, KEDA, EKS  
📁 Structure:
realtime-chat-keda/
├── ws-server.js  
├── deployment.yaml  
├── scaledobject.yaml  

🔣 Input: Redis channel message count  
📤 Output: WebSocket pods scale dynamically  

🌍 Environment: AWS EKS  
📜 Constraints: Redis metrics exported  
🧾 Output: Live chat auto-scales with usage  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Slack-like chat app  
💡 I want chat autoscaler setup  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Graceful shutdown  
📥 Logs: Redis + KEDA + pod logs  
🌐 Language: English
```

---

### ✅ Prompt 10: **CKA Prep Lab – Troubleshoot Broken Ingress + HPA**
**🧠 Level:** Super Advanced  
```
🔧 I’m preparing for CKA certification.  
🎯 I want to troubleshoot and fix a broken Ingress and HPA in a deployed app.  
💻 Stack: Kubernetes, Ingress, HPA, Prometheus  
📁 Structure:
cka-practice-lab/
├── broken-deployment.yaml  
├── broken-hpa.yaml  
├── broken-ingress.yaml  

🔣 Input: Broken config files  
📤 Output: Fixed routing, HPA starts working  

🌍 Environment: Minikube or EKS  
📜 Constraints: No Helm, CLI-only fix  
🧾 Output: Curl works, HPA shows correct scale  
🔧 Experience Level: Super Advanced  
🏢 Use Case: CKA hands-on simulation  
💡 I want fix-ready YAMLs and debugging steps  
🚀 Deploy: kubectl  
🔐 Best Practices: Check probes, RBAC, metric sources  
📥 Logs: `describe` + `logs` + `top` outputs  
🌐 Language: English
```

---
