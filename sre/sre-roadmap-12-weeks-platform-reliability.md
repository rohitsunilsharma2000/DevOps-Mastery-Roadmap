# SRE Roadmap – 12 Weeks (Platform & Reliability Focus)

**Target Profile**
- 8–12+ years Full-Stack / Backend experience
- Moving into **Site Reliability Engineer (SRE)** / **Platform Engineer**
- Cloud-first (AWS), Kubernetes-based environments

---

## Core SRE Principles You Must Internalize
- SLO > SLA > SLI
- Error Budgets drive engineering decisions
- Automation over heroics
- Toil reduction
- Blameless postmortems
- Observability ≠ monitoring

---

# Week 1 – Linux, Networking & Production Debugging

### Learn
- Linux internals: CPU, memory, disk, file descriptors
- Networking: DNS, TCP vs UDP, TLS, HTTP/2
- Debugging tools: `top`, `htop`, `ss`, `lsof`, `strace`, `tcpdump`

### Hands-on
- Simulate high CPU / memory leak on a service
- Debug live process without restarting

### Output
- Debug checklist doc
- Shell commands cheat sheet

---

# Week 2 – Git, CI/CD & Release Safety

### Learn
- Git internals (rebase, revert, tags)
- CI pipelines (Jenkins/GitHub Actions)
- Canary vs blue-green vs rolling deploy

### Project
**Safe Release Pipeline**
- Build → test → image → canary deploy → rollback

### SRE Angle
- Fast rollback
- Immutable artifacts
- No manual prod deploys

---

# Week 3 – Containers & Failure Scenarios

### Learn
- Docker internals (cgroups, namespaces)
- Container failure modes
- Healthchecks & graceful shutdown

### Project
**Failure Lab**
- Kill containers
- Break networking
- Observe restart policies

---

# Week 4 – AWS Reliability Fundamentals

### Learn
- IAM least privilege
- Multi-AZ architecture
- ALB vs NLB
- Auto Scaling Groups

### Project
**Highly Available App on AWS**
- EC2/ECS with ALB
- Health checks + scaling
- CloudWatch alarms

---

# Week 5 – Kubernetes Deep Dive (SRE level)

### Learn
- Scheduler, kubelet, controller manager
- Pod lifecycle
- Readiness vs liveness
- Resource requests & limits

### Project
**Resilient K8s Service**
- HPA enabled
- PodDisruptionBudget
- Graceful shutdown

---

# Week 6 – Kubernetes Failure Engineering

### Learn
- CrashLoopBackOff
- Node failures
- Evictions
- OOMKilled

### Project
**Chaos Scenarios**
- Kill nodes
- Introduce latency
- Validate self-healing

---

# Week 7 – GitOps for SRE (Argo CD / Flux)

### Learn
- GitOps reconciliation loop
- Drift detection
- Environment promotion

### Project
**GitOps-Driven Production**
- Argo CD manages prod
- No kubectl access
- Rollback via Git revert

---

# Week 8 – Infrastructure as Code (Terraform)

### Learn
- Terraform state
- Remote backend (S3 + DynamoDB)
- Modules & workspaces

### Project
**Immutable Platform**
- Terraform provisions:
  - VPC
  - EKS
  - Node groups
  - IAM
- Zero manual AWS clicks

---

# Week 9 – Observability (Metrics, Logs, Traces)

### Learn
- RED / USE metrics
- Prometheus scraping
- Grafana dashboards
- Alert fatigue avoidance

### Project
**Golden Signals Dashboard**
- Latency
- Traffic
- Errors
- Saturation

---

# Week 10 – Incident Management & On-Call

### Learn
- Incident severity levels
- Runbooks
- Escalation policies
- MTTR vs MTBF

### Project
**Incident Simulation**
- Trigger alert
- Follow runbook
- Write postmortem

---

# Week 11 – SLOs & Error Budgets

### Learn
- SLI definitions
- SLO math
- Error budget policies

### Project
**SLO-Driven Service**
- Define SLI
- Create SLO
- Burn-rate alerts

---

# Week 12 – Production Readiness & Review

### Learn
- Production Readiness Review (PRR)
- Capacity planning
- Load testing
- Cost vs reliability trade-offs

### Final Capstone
**SRE Production Platform**
- AWS + EKS
- GitOps CD
- Terraform IaC
- Observability
- SLOs + alerts
- Incident runbooks

---

# Interview Checklist (Must Answer Confidently)

## Linux & Networking
- How do you debug high load without restart?
- Difference between TCP backlog and application latency?

## Kubernetes
- Why pods restart?
- How HPA works internally?
- Difference between readiness & liveness probes?

## AWS
- How ALB health checks affect scaling?
- How do you design multi-AZ failure tolerance?

## Observability
- Metrics vs logs vs traces
- What causes alert fatigue?
- What are Golden Signals?

## Reliability
- Define SLO vs SLA
- What happens when error budget is exhausted?
- How do you reduce toil?

## Incidents
- Walk through a real outage
- How do you run a blameless postmortem?

---

# Roles You Can Target After This
- Site Reliability Engineer (SRE)
- Platform Engineer
- Production Engineer
- Cloud Reliability Engineer

---

# Optional Add-Ons
- Chaos Engineering (Litmus / Gremlin)
- AIOps (BigPanda / Moogsoft)
- Capacity modeling
- Cost-aware SRE (FinOps)

---

## End Goal
You should be able to say:
> “I design systems that fail safely, recover automatically, and improve reliability using data.”
