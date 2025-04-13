
---

## 🧭 **Phase 3: Kubernetes Mastery (6–8 Weeks)**

### ✅ **Goal**: Deploy, scale, and manage applications in Kubernetes using EKS, Helm, and autoscalers like Karpenter/KEDA

---

## 🗓️ **Week 1: Kubernetes Basics – CLI & Core Concepts**

### 🔹 Topics:
- What is Kubernetes (K8s)? Core components
- Pods, ReplicaSets, Deployments
- Services (ClusterIP, NodePort, LoadBalancer)
- Labels, selectors, namespaces

### 🛠️ Hands-On:
- Install `minikube`, `kubectl`
- Create Pods & Deployments
- Expose services
- Use `kubectl get`, `describe`, `logs`, `exec`

### 📚 Resources:
- [Kubernetes Basics Tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

---

## 🗓️ **Week 2: Configs, Secrets, Volumes, RBAC**

### 🔹 Topics:
- ConfigMaps, Secrets
- Volumes: emptyDir, hostPath, PersistentVolumes
- RBAC: Roles, ClusterRoles, RoleBindings

### 🛠️ Hands-On:
- Mount ConfigMaps & Secrets into Pods
- Create persistent volume claims (PVC)
- Apply RBAC to restrict service accounts

### 📚 Resources:
- [ConfigMaps & Secrets](https://kubernetes.io/docs/concepts/configuration/)
- [RBAC Authorization](https://kubernetes.io/docs/reference/access-authn-authz/rbac/)

---

## 🗓️ **Week 3: Helm Package Manager & StatefulSets**

### 🔹 Topics:
- What is Helm? Helm Charts, Repos
- Installing and using Helm 3
- Deploying apps with Helm (e.g., nginx, prometheus)
- StatefulSets vs Deployments

### 🛠️ Hands-On:
- Install Helm: `brew install helm` or binary
- Deploy a sample chart: `helm install my-nginx bitnami/nginx`
- Write your own custom Helm chart
- Use values.yaml for overrides

### 📚 Resources:
- [Helm Docs](https://helm.sh/docs/)
- [Awesome Helm Charts](https://artifacthub.io)

---

## 🗓️ **Week 4: AWS EKS (Elastic Kubernetes Service)**

### 🔹 Topics:
- Creating EKS clusters using:
  - **eksctl**
  - or **Terraform**
- IAM integration
- Configuring `kubeconfig` and `aws-iam-authenticator`

### 🛠️ Hands-On:
- Install eksctl: `brew install eksctl`
- Create a cluster:
  ```bash
  eksctl create cluster --name my-cluster --region us-east-1
  ```
- Deploy a test app (e.g., nginx)
- Attach IAM policies to nodes for EBS access

### 📚 Resources:
- [EKS Getting Started](https://docs.aws.amazon.com/eks/latest/userguide/getting-started.html)
- [eksctl GitHub](https://github.com/weaveworks/eksctl)

---

## 🗓️ **Week 5: Scaling & Autoscaling – Karpenter, HPA, Cluster Autoscaler**

### 🔹 Topics:
- **Karpenter**: Auto provision & deprovision EC2 nodes
- **HPA**: Horizontal Pod Autoscaler (based on CPU, custom metrics)
- **Cluster Autoscaler**: Add/remove nodes based on pending pods

### 🛠️ Hands-On:
- Install Karpenter via Helm
- Set up provisioners
- Deploy app with HPA:
  ```bash
  kubectl autoscale deployment my-app --cpu-percent=50 --min=1 --max=5
  ```
- Simulate load and observe scaling

### 📚 Resources:
- [Karpenter Docs](https://karpenter.sh/docs/)
- [Autoscaling K8s](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/)

---

## 🗓️ **Week 6: KEDA (Event-Driven Autoscaler) & Ingress**

### 🔹 Topics:
- KEDA: Scale based on Kafka, SQS, Prometheus metrics, etc.
- Ingress Controllers (NGINX, ALB)
- TLS termination & cert-manager

### 🛠️ Hands-On:
- Install KEDA using Helm
- Deploy ScaledObjects (e.g., scale based on queue length)
- Install NGINX Ingress Controller
- Route traffic using Ingress YAML
- Configure HTTPS with cert-manager + Let's Encrypt

### 📚 Resources:
- [KEDA Docs](https://keda.sh/docs/)
- [Ingress Controllers](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)

---

## 🗓️ **Week 7–8: Real-World Projects & CKA Prep (Optional)**

### 🧪 Mini Projects:
1. **EKS Cluster Setup via Terraform + Karpenter + Ingress**
2. CI/CD Deployment via GitHub Actions + Helm
3. Custom HPA using Prometheus metrics
4. KEDA Scaler with SQS

### 🏆 Optional:
- Prepare for **CKA** or **CKAD**
- Practice with [Killer.sh](https://killer.sh/cka/)

---

## ✅ Deliverables for Portfolio:
- GitHub repo: `eks-terraform-cluster`
- Helm chart: custom app with ConfigMap, PVC
- KEDA scaler config files
- Karpenter provisioner YAMLs
- Screenshots or GIFs of autoscaling in action

---

