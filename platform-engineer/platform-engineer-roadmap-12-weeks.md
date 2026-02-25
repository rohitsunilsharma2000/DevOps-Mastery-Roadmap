# Platform Engineer Roadmap – 12 Weeks (AWS + EKS + GitOps + IDP)

## Target Outcome
You can build an **Internal Developer Platform (IDP)**:
- Self-service “golden paths”
- GitOps delivery
- Policy-as-code guardrails
- Autoscaling with Karpenter
- Observability & platform reliability basics

---

## Week 1 – Platform Fundamentals
### Learn
- Platform engineering vs DevOps
- Paved roads / golden paths / self-service
- IDP concepts: catalog, templates, service ownership

### Task
- Define 3 golden paths:
  1) API service
  2) Worker/cron
  3) Frontend

### Output
- Platform README: standards (logging, metrics, health endpoints, CI rules)

---

## Week 2 – GitOps Baseline (Argo CD)
### Learn
- GitOps reconciliation, drift, rollback, multi-env
- Argo CD Application/App-of-Apps

### Project Deliverable
- EKS + Argo CD
- Repo structure:
  - `/apps/dev`
  - `/apps/stage`
  - `/apps/prod`

---

## Week 3 – Service Template v1 (Golden Path)
### Learn
- Helm/Kustomize packaging standards
- Repo templating approach

### Build
- “Create new service” template that generates:
  - CI pipeline
  - Dockerfile
  - Helm chart
  - ArgoCD app manifest
  - basic dashboards + alerts placeholders

---

## Week 4 – Backstage IDP Setup
### Learn
- Backstage core: catalog, software templates, techdocs
- Entity ownership (team/service/system)

### Build
- Backstage running (local + k8s)
- Service catalog entry for your sample service
- TechDocs for runbook + SLO draft

---

## Week 5 – Backstage Templates (Scaffolder)
### Learn
- Scaffolder actions: repo create, PR, pipeline triggers
- Repo standards enforcement

### Build
- Template: `create-springboot-service` (or node)
- Output repo includes:
  - CI
  - Helm chart
  - basic k8s manifests
  - README with runbook sections

---

## Week 6 – Policy-as-Code Guardrails
### Learn
- Kyverno or OPA Gatekeeper (choose one)
- Enforce:
  - resource requests/limits
  - no :latest tag
  - required probes
  - approved registries

### Build
- Policy pack + “fail in CI” validation
- Admission control in cluster

---

## Week 7 – Secrets & Config Standard
### Learn
- External Secrets Operator (AWS Secrets Manager/SSM)
- Sealed Secrets vs ESO

### Build
- One golden path uses ESO:
  - secrets stored in AWS
  - synced into k8s
- Document “how to add secret” in Backstage TechDocs

---

## Week 8 – Karpenter (Autoscaling at Platform Level)
### Learn
- Karpenter: node provisioning, consolidation, spot
- Scheduling constraints & instance types

### Build
- Replace node group scaling with Karpenter
- Verify:
  - scale up on load
  - consolidate on idle

---

## Week 9 – Platform Observability (OpenTelemetry optional)
### Learn
- Standard metrics/logs/traces required from all services
- Golden signals dashboards

### Build
- Platform dashboards:
  - cluster health
  - service health (RED)
- Alert rules starter pack

---

## Week 10 – Reliability Features in the Platform
### Learn
- Progressive delivery basics
- Safe rollouts

### Build
- Add canary or blue/green:
  - Argo Rollouts OR simple weighted routing (Ingress/mesh)
- Rollback automation

---

## Week 11 – Multi-Tenant / Multi-Team Readiness
### Learn
- Namespaces, RBAC, resource quotas
- Team isolation model

### Build
- Team onboarding:
  - namespace
  - RBAC role
  - quota
  - default policies

---

## Week 12 – Capstone & Packaging
### Capstone Project
**Internal Developer Platform on AWS**
- Backstage catalog + templates
- Argo CD GitOps deploy
- Policy-as-code guardrails
- Karpenter autoscaling
- Secrets standard
- Observability baseline

### Deliverables
- Architecture diagram
- Demo script (10 minutes)
- Runbook + PRR checklist

---

## Portfolio Projects (Exact)
1) **IDP Starter Platform**
   - Backstage + Templates + TechDocs + Catalog
2) **GitOps Delivery System**
   - ArgoCD multi-env + rollback + promotion
3) **Platform Guardrails Pack**
   - Kyverno/OPA policies + CI validation + admission control
4) **Karpenter Cost + Scale Lab**
   - spot + consolidation + load-based scaling

---

## Platform Engineer Interview Checklist
### Platform Concepts
- What is a golden path and why?
- What problems does an IDP solve?

### GitOps
- How does drift detection work?
- How do you handle secrets in GitOps?

### Kubernetes
- Admission controllers, RBAC, quotas
- Deployment strategies & rollbacks

### Policy-as-Code
- What policies do you enforce and why?
- How do you test policies?

### Autoscaling
- HPA vs Cluster Autoscaler vs Karpenter
- Spot interruptions strategy

### Operational Excellence
- How do teams onboard?
- How do you reduce toil for developers?
