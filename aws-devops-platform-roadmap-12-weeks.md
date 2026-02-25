## 12-Week AWS DevOps / Platform Roadmap (for 9+ yrs Full-Stack)

Goal: you should be able to **design + build + operate** a production-grade platform on **AWS + Kubernetes + GitOps + Observability + IaC**, and talk confidently in interviews.

---

# Weeks 1–2: Git + CI (Jenkins) + Release Basics

### Learn

* Git: rebase, cherry-pick, revert, tags, clean history, branching strategy
* Jenkins: Declarative pipeline, agents, credentials, artifacts, multi-branch
* Build best practice: versioning, semantic tags, changelog

### Hands-on deliverable

* Pick one app you already know (Spring Boot / Node).
* Jenkins pipeline:

  1. build + unit tests
  2. docker image build (multi-stage)
  3. push to registry (ECR recommended)
  4. generate build metadata (version + commit + timestamp)

**Interview checkpoint:** explain CI vs CD, artifacts, rollback, pipeline stages.

---

# Weeks 3–4: Docker + Local Infra (Compose) + Debugging Skills

### Learn

* Dockerfile best practices, multi-stage builds
* Docker networking, volumes, healthchecks
* Compose for local stacks (app + db + redis)

### Hands-on deliverable

* `docker compose up` runs:

  * app + postgres + redis + nginx
* Add:

  * health endpoints
  * structured logs (JSON)
  * basic load test with `hey` or `k6`

**Interview checkpoint:** container vs VM, image layers, debugging containers.

---

# Weeks 5–6: AWS Core (must-have for Platform)

### Learn (AWS)

* IAM (roles/policies), STS basics
* VPC: public/private subnets, route tables, NAT, security groups
* EC2 + ALB + Auto Scaling basics
* S3 + ECR + CloudWatch logs/metrics
* Secrets: SSM Parameter Store / Secrets Manager

### Hands-on deliverable

* Deploy your docker app on AWS in *one* of these:

  * **ECS Fargate** (fastest path) OR
  * EC2 + ALB (classic)
* Logging to CloudWatch
* Alarm when 5xx spikes

**Interview checkpoint:** VPC diagram explanation, IAM least privilege, ALB vs NLB.

---

# Weeks 7–8: Kubernetes on AWS (EKS) + Helm

### Learn

* K8s: deployments, services, ingress, configmap/secret, HPA, probes
* EKS basics: node groups, add-ons, IAM roles for service accounts (IRSA)
* Helm: values, templates, chart structure

### Hands-on deliverable

* Create EKS (even a small one)
* Deploy app with Helm:

  * env config via configmap/secret
  * HPA
  * ingress (ALB ingress controller or NGINX)

**Interview checkpoint:** how scheduling works, probes, scaling, rollouts.

---

# Weeks 9–10: GitOps CD (Argo CD + Flux) + Environments

### Learn

* GitOps model: pull-based deploy, drift detection
* **Argo CD** (primary)
* **Flux CD** (secondary—know basics)
* Environment strategy: dev → staging → prod

### Hands-on deliverable

* Git repo contains:

  * Helm chart or Kustomize overlays
  * separate env folders
* ArgoCD auto-sync deploys to cluster
* One promotion flow:

  * tag release → update staging → promote to prod

**Interview checkpoint:** why GitOps is better than “kubectl apply from laptop”.

---

# Weeks 11–12: IaC + Observability (Terraform + Prometheus/Grafana)

### Learn

* Terraform: modules, remote state (S3+Dynamo), workspaces, plan/apply
* Prometheus + Grafana:

  * RED metrics (rate, errors, duration)
  * dashboards + alerts
* Bonus: basic log routing (CloudWatch → OpenSearch/ELK/Splunk if available)

### Hands-on deliverable

* Terraform creates:

  * VPC + EKS + nodegroup + ECR + IAM + ALB ingress setup
* Observability:

  * app exposes metrics (`/actuator/prometheus` or `/metrics`)
  * Grafana dashboard shows:

    * request rate, error rate, p95 latency
    * pod restarts, CPU/memory
  * Alerts:

    * 5xx > threshold
    * p95 latency high
    * crashlooping pods

**Interview checkpoint:** explain SLO/SLI, alert fatigue, autoscaling and limits.

---

# 3 Portfolio Projects (pick 2 mandatory + 1 optional)

## Project A (Mandatory): “GitOps EKS Platform”

* EKS + Helm + ArgoCD
* Ingress + HPA + config/secret management
* Full CI pipeline builds image + deploy via GitOps

## Project B (Mandatory): “Terraform AWS Platform”

* Terraform modules for VPC + EKS + ECR + IAM + Observability
* Remote state + environment separation

## Project C (Optional): “Serverless Sidecar”

* Lambda + API Gateway triggers some async job (e.g., image resize, invoice PDF, webhook)
* IaC + logs + alarms

---

# What to Skip / De-prioritize (for Platform roles)

* **AWS OpsWorks**: learn only if your target company uses it. Modern platform stacks prefer **EKS/ECS + IaC**.
* Deep TensorFlow/PyTorch: only if you’re targeting **MLOps** specifically.

---

# Interview Ready Checklist (must be able to explain)

* VPC layout (public/private, NAT, routing)
* IAM policies + roles (least privilege, IRSA)
* CI vs CD, rollback strategy
* Kubernetes deployment lifecycle + HPA + probes
* GitOps benefits, drift, promotion
* Terraform remote state + modules
* Observability: metrics/logs/traces + alert design

---

If you tell me:

1. **Your current comfort level** (Docker: beginner/ok/strong, AWS: beginner/ok/strong, K8s: beginner/ok/strong)
2. Whether you prefer **ECS first or EKS first**

…I’ll generate a **week-by-week daily task plan + exact commands + repo structure** (copy-paste ready).
