
# SRE Roadmap – 12 Weeks (SLOs + OpenTelemetry + Incidents + Chaos + Capacity)

## Week 1 – Linux + Networking Debugging
- High CPU/memory/disk troubleshooting
- DNS/TLS/latency tools: ss, lsof, tcpdump

## Week 2 – Reliability Engineering Basics
- SLI/SLO/SLA, error budgets
- Define SLO for one service

## Week 3 – Observability Foundation
- Metrics/logs/traces model
- Create RED metrics dashboard in Grafana

## Week 4 – OpenTelemetry End-to-End
- Instrument app traces
- Export to Tempo/Jaeger + Grafana

## Week 5 – Alert Engineering (Burn Rate)
- Multi-window burn-rate alerts
- Reduce noise, severity routing

## Week 6 – Incident Management
- Incident roles, comms, escalation
- Runbook + postmortem template

## Week 7 – Kubernetes Failure Modes
- OOMKilled, CrashLoopBackOff, evictions
- Debug with events, logs, metrics

## Week 8 – Chaos Engineering
- Litmus basics
- Experiments: node kill, pod kill, latency injection

## Week 9 – Capacity Planning
- Load tests (k6)
- Compute requirements, scaling limits

## Week 10 – Resilience Patterns
- timeouts, retries, circuit breaker
- bulkheads & backpressure

## Week 11 – Disaster Recovery
- RTO/RPO, backups, restore drills
- multi-AZ, multi-region concepts

## Week 12 – Capstone
**SRE Reliability Pack**
- SLOs + burn-rate alerts
- OTel tracing
- Chaos experiments
- Incident runbooks
- Capacity plan + load test results

## Exact Projects
1) SLO pack + burn-rate alerts
2) OTel tracing pipeline + dashboards
3) Chaos test suite + resiliency report
4) Incident simulation + postmortem

## Interview Checklist
- Explain SLO vs SLA, error budget policy
- Design alerts to avoid fatigue
- Debug a production incident story
- OTel: context propagation, traces vs logs
- Chaos: what you tested & why
- Capacity: how you estimate and validate
