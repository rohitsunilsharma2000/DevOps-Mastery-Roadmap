# MLOps Roadmap – 12 Weeks (Kubeflow + MLflow + Serving + Monitoring)

## Week 1 – MLOps System Basics
- batch vs online inference
- drift concepts

## Week 2 – Data Validation
- schema/stat checks (Great Expectations optional)
- pandas pipelines

## Week 3 – Reproducible Training
- deterministic runs
- versioned configs

## Week 4 – MLflow Tracking & Registry
- experiments + model registry + promotion

## Week 5 – Containerize Inference
- build inference image
- local test

## Week 6 – Deploy on Kubernetes
- inference service with HPA
- probes and rollout strategy

## Week 7 – Kubeflow Pipelines
- end-to-end pipeline DAG
- metadata

## Week 8 – GitOps for Model Deploy
- ArgoCD deploys inference
- versioned models

## Week 9 – Model Serving Strategies
- canary model rollout
- rollback

## Week 10 – Model Monitoring
- latency + error + prediction distribution
- drift detection signals

## Week 11 – Retraining Automation
- trigger retrain based on drift
- promote if better

## Week 12 – Capstone
**Production MLOps Platform**
- Kubeflow pipeline + MLflow registry
- k8s inference + GitOps
- monitoring + retraining loop

## Exact Projects
1) MLflow registry + promotion flow
2) Kubeflow pipeline end-to-end
3) K8s inference service + GitOps deploy
4) Drift monitoring + retraining trigger

## Interview Checklist
- Data drift vs concept drift
- Reproducibility strategy
- Safe model rollout and rollback
- How you monitor models in prod
- Kubeflow pipeline components
