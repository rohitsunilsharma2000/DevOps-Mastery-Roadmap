
# DevSecOps Roadmap – 12 Weeks (Supply Chain + K8s Security + IAM + Scanning/Signing)

## Week 1 – Security Fundamentals for Cloud
- Shared responsibility, threat modeling basics
- IAM least privilege mindset

## Week 2 – AWS IAM Deep
- roles, trust policies, boundaries
- IRSA for EKS

## Week 3 – Container Security Basics
- image hardening, minimal base
- non-root, read-only FS

## Week 4 – Scanning (SAST/DAST/Image)
- Trivy image scan + fail CI
- dependency scanning

## Week 5 – Supply Chain (SBOM)
- generate SBOM (CycloneDX/SPDX)
- track vulnerabilities by SBOM

## Week 6 – Signing & Verification
- cosign signing
- verify before deploy (policy gate)

## Week 7 – Kubernetes Security
- RBAC, namespaces, quotas
- Pod Security Standards

## Week 8 – Network Security
- NetworkPolicies
- Ingress controls, WAF concepts

## Week 9 – Policy-as-Code Security Gates
- Kyverno/OPA policies:
  - no privileged
  - no hostPath
  - no latest
  - require probes/limits
  - only signed images

## Week 10 – Secrets Management
- Secrets Manager + External Secrets Operator
- secret rotation

## Week 11 – Runtime Security
- Falco basics (optional)
- audit logs, detection mindset

## Week 12 – Capstone
**Secure Delivery Pipeline**
- CI scans + SBOM + signing
- Admission policies enforce signed images
- Secure EKS baseline with RBAC + network policies

## Exact Projects
1) Secure CI: scan + SBOM + sign
2) Secure EKS baseline: RBAC + PSS + policies
3) Admission control: verify signatures
4) Secrets workflow: ESO + rotation docs

## Interview Checklist
- Explain IRSA and least privilege
- SBOM purpose and how you use it
- How to prevent deploying vulnerable images
- Pod Security, NetworkPolicy use cases
- Supply chain threats & mitigation
