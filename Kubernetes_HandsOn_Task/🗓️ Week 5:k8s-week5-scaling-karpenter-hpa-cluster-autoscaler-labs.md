## 🧭 Kubernetes Week 5: Scaling & Autoscaling with Karpenter, HPA, and Cluster Autoscaler – 10 Hands-On Labs

### 📝  Subtitle :  
> Dive into real-world Kubernetes autoscaling strategies using Karpenter, Horizontal Pod Autoscaler (HPA), and Cluster Autoscaler. Includes fullstack, backend, and frontend scenarios – from basic CPU scaling to dynamic EC2 node provisioning, load simulation, and event-driven scaling with KEDA.

---

### ✅ Prompt 1: **HPA on NGINX Deployment Using CPU**  
**🧠 Level:** Beginner  
```
🔧 I’m a DevOps beginner exploring autoscaling.  
🎯 I want to apply Horizontal Pod Autoscaler (HPA) to an NGINX deployment that scales based on CPU.  
💻 Stack: Kubernetes, HPA, NGINX  
📁 Structure:
hpa-nginx/
├── deployment.yaml  
├── hpa.yaml  

🔣 Input: `cpu: 50m`, min=1, max=3  
📤 Output: Pods auto-scale with CPU load  

🌍 Environment: Minikube or AWS EKS  
📜 Constraints: Must use Metrics Server  
🧾 Output: HPA status via `kubectl describe hpa`  
🔧 Experience Level: Beginner  
🏢 Use Case: Learn Kubernetes HPA basics  
💡 I want YAML files + simulation instructions  
🚀 Deploy: kubectl  
🔐 Best Practices: Always set `resources.requests`  
📥 Logs: `kubectl top pods`, `kubectl get hpa`  
🌐 Language: English
```

---

### ✅ Prompt 2: **Autoscale Express Backend with Load Simulation**  
**🧠 Level:** Intermediate  
```
🔧 I’m a backend engineer.  
🎯 I want to deploy a Node.js Express API and scale it using HPA with load generated via `hey`.  
💻 Stack: Node.js, Express, Kubernetes, HPA  
📁 Structure:
hpa-express/
├── Dockerfile  
├── app.js  
├── deployment.yaml  
├── hpa.yaml  

🔣 Input: `/api/ping` endpoint  
📤 Output: Pods scale up when simulated traffic spikes  

🌍 Environment: AWS EKS or Minikube  
📜 Constraints: CPU-based scaling only  
🧾 Output: HPA reacts to load within 1-2 minutes  
🔧 Experience Level: Intermediate  
🏢 Use Case: Backend autoscaling under stress  
💡 I want working app + load simulation  
🚀 Deploy: kubectl  
🔐 Best Practices: Use readiness probe for better scaling  
📥 Logs: `kubectl logs` + `top pods`  
🌐 Language: English
```

---

### ✅ Prompt 3: **Deploy Karpenter on EKS Using Helm**  
**🧠 Level:** Intermediate  
```
🔧 I’m setting up autoscaling infrastructure.  
🎯 I want to install Karpenter on EKS using Helm and configure a basic Provisioner.  
💻 Stack: AWS EKS, Helm, Karpenter  
📁 Structure:
karpenter-install/
├── provisioner.yaml  
├── karpenter-values.yaml  

🔣 Input: Spot + OnDemand instance types  
📤 Output: Karpenter scales EC2 nodes based on unscheduled pods  

🌍 Environment: AWS EKS  
📜 Constraints: Karpenter IAM role and controller must be in place  
🧾 Output: EC2 nodes created by Karpenter  
🔧 Experience Level: Intermediate  
🏢 Use Case: Dynamic infra scaling  
💡 I want full Helm setup with YAML files  
🚀 Deploy: Helm  
🔐 Best Practices: Use instance weighting and limits  
📥 Logs: `karpenter` controller logs  
🌐 Language: English
```

---

### ✅ Prompt 4: **Autoscale React Frontend with CPU and Custom Metrics**  
**🧠 Level:** Intermediate  
```
🔧 I’m a frontend engineer deploying on Kubernetes.  
🎯 I want to autoscale a React app based on CPU and page hit metrics (via Prometheus Adapter).  
💻 Stack: React, Prometheus, HPA, Custom Metrics  
📁 Structure:
hpa-react-metrics/
├── react-app/  
├── deployment.yaml  
├── service.yaml  
├── hpa.yaml  

🔣 Input: Hit count metric, CPU > 50%  
📤 Output: Replicas scale based on usage  

🌍 Environment: EKS with Prometheus Adapter  
📜 Constraints: Adapter must expose custom metric  
🧾 Output: HPA status + pods increased  
🔧 Experience Level: Intermediate  
🏢 Use Case: UI with variable traffic  
💡 I want React app + custom metric config  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Use proper labels and selectors  
📥 Logs: Prometheus adapter log + HPA status  
🌐 Language: English
```

---

### ✅ Prompt 5: **HPA with Memory-Based Scaling**  
**🧠 Level:** Intermediate  
```
🔧 I want to explore memory-based autoscaling.  
🎯 I want to use HPA that scales pods based on memory instead of CPU.  
💻 Stack: Kubernetes, Metrics Server  
📁 Structure:
hpa-memory/
├── deployment.yaml  
├── hpa-memory.yaml  

🔣 Input: Memory threshold 200Mi  
📤 Output: App scales up with increased memory use  

🌍 Environment: Minikube or EKS  
📜 Constraints: Metrics Server must support memory  
🧾 Output: `kubectl describe hpa` shows memory stats  
🔧 Experience Level: Intermediate  
🏢 Use Case: Apps with high memory but low CPU  
💡 I want clear memory-based HPA example  
🚀 Deploy: kubectl  
🔐 Best Practices: Use limits to enforce boundaries  
📥 Logs: pod metrics + HPA events  
🌐 Language: English
```

---

### ✅ Prompt 6: **Karpenter with Consolidation and Spot Preferences**  
**🧠 Level:** Hard  
```
🔧 I want to optimize node usage dynamically.  
🎯 I want to configure Karpenter with consolidation and weighted instance types (favoring Spot).  
💻 Stack: Karpenter, AWS EKS  
📁 Structure:
karpenter-consolidate/
├── provisioner.yaml  

🔣 Input: Consolidation and capacity type: `spot`  
📤 Output: Spot node scales in/out based on pod spec  

🌍 Environment: EKS  
📜 Constraints: Spot instance IAM policies  
🧾 Output: Consolidation logs and scaling chart  
🔧 Experience Level: Hard  
🏢 Use Case: Cost-efficient auto-provisioning  
💡 I want a provisioner config with priorities  
🚀 Deploy: Helm  
🔐 Best Practices: Set disruption budgets  
📥 Logs: `karpenter` logs and EC2 events  
🌐 Language: English
```

---

### ✅ Prompt 7: **Use Cluster Autoscaler with Multiple Node Groups**  
**🧠 Level:** Hard  
```
🔧 I want to scale nodes with Cluster Autoscaler.  
🎯 I want to configure CA to scale multiple node groups (spot + on-demand) in EKS.  
💻 Stack: AWS EKS, Cluster Autoscaler  
📁 Structure:
cluster-autoscaler/
├── cluster-autoscaler.yaml  
├── nodegroups.tf  

🔣 Input: NodeAffinity for pods  
📤 Output: CA adds/removes nodes per pod affinity  

🌍 Environment: AWS EKS  
📜 Constraints: Multiple ASGs, autoscaler deployment  
🧾 Output: Node scale events  
🔧 Experience Level: Hard  
🏢 Use Case: Flexible node scaling  
💡 I want autoscaler config + IAM policy  
🚀 Deploy: Terraform + kubectl  
🔐 Best Practices: Taint spot nodes for fallback  
📥 Logs: Cluster Autoscaler logs  
🌐 Language: English
```

---

### ✅ Prompt 8: **Fullstack App with CPU HPA + Karpenter Node Scaling**  
**🧠 Level:** Super Advanced  
```
🔧 I’m a fullstack developer deploying scalable infra.  
🎯 I want to deploy a React + Node.js app where pods scale via HPA and nodes auto-provision via Karpenter.  
💻 Stack: React, Node.js, AWS EKS, Karpenter, HPA  
📁 Structure:
fullstack-karpenter-hpa/
├── backend/  
├── frontend/  
├── provisioner.yaml  
├── hpa.yaml  

🔣 Input: Load spikes to both services  
📤 Output: App scales at both pod and node level  

🌍 Environment: AWS EKS  
📜 Constraints: Metrics Server + IAM role for Karpenter  
🧾 Output: Traffic → pod → node scale-up  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Production-ready fullstack app  
💡 I want complete stack with automation  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Consolidation and warm-up buffer  
📥 Logs: `top pods`, `karpenter`, `HPA` status  
🌐 Language: English
```

---

### ✅ Prompt 9: **Custom Metric Autoscaling Using KEDA**  
**🧠 Level:** Super Advanced  
```
🔧 I want to scale using external metrics.  
🎯 I want to install KEDA and configure autoscaling based on Redis queue length.  
💻 Stack: KEDA, Redis, Node.js  
📁 Structure:
keda-autoscale/
├── scaledobject.yaml  
├── deployment.yaml  

🔣 Input: Redis stream backlog  
📤 Output: KEDA scales consumer pods based on queue  

🌍 Environment: EKS with KEDA  
📜 Constraints: External scaler config must be valid  
🧾 Output: Redis spikes → pod increases  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Queue-based worker autoscaling  
💡 I want Redis-based trigger example  
🚀 Deploy: Helm + YAML  
🔐 Best Practices: Use scale cooldown to prevent thrashing  
📥 Logs: KEDA controller logs  
🌐 Language: English
```

---

### ✅ Prompt 10: **Event-Driven Scaling with AWS Lambda Trigger via KEDA**  
**🧠 Level:** Super Advanced  
```
🔧 I want to autoscale based on AWS event triggers.  
🎯 I want to scale a Kubernetes job based on SQS messages using KEDA.  
💻 Stack: AWS EKS, KEDA, AWS SQS, Node.js  
📁 Structure:
keda-sqs-scaler/
├── scaledjob.yaml  
├── deployment.yaml  

🔣 Input: SQS message backlog  
📤 Output: Consumer pods run when messages arrive  

🌍 Environment: AWS EKS, KEDA installed  
📜 Constraints: IRSA required for SQS access  
🧾 Output: Pod spin-up based on SQS trigger  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Serverless-like scaling in K8s  
💡 I want SQS scaler + IRSA sample  
🚀 Deploy: Helm  
🔐 Best Practices: Limit concurrency  
📥 Logs: `kubectl logs` + KEDA SQS adapter  
🌐 Language: English
```

---

## 🔥 Week 5: Scaling & Autoscaling – Super Advanced Prompts (11–20)

---

### ✅ Prompt 11: **Multi-Zone Karpenter Scaling with Zonal Balancing**  
**🧠 Level:** Super Advanced  
```
🔧 I’m optimizing zonal availability.  
🎯 I want to configure Karpenter to balance node provisioning across multiple availability zones.  
💻 Stack: AWS EKS, Karpenter, Helm  
📁 Structure:
karpenter-zonal-balance/
├── provisioner.yaml  

🔣 Input: Multiple AZs in EKS  
📤 Output: EC2 nodes spread across zones based on demand  

🌍 Environment: AWS EKS with subnets in 3 AZs  
📜 Constraints: Proper subnet tagging per zone  
🧾 Output: Nodes created in multiple AZs  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Zonal fault tolerance  
💡 I want Karpenter provisioner example with zone spreading  
🚀 Deploy: Helm + AWS CLI  
🔐 Best Practices: Use `topologySpreadConstraints`  
📥 Logs: `karpenter` controller logs and EC2 AZ check  
🌐 Language: English
```

---

### ✅ Prompt 12: **Karpenter + Spot Termination Handling with Lifecycle Hooks**  
**🧠 Level:** Super Advanced  
```
🔧 I want to gracefully handle spot instance terminations.  
🎯 I want to deploy an app on Karpenter-provisioned Spot instances that handles termination via lifecycle hook.  
💻 Stack: AWS EKS, Karpenter, EC2, Node.js  
📁 Structure:
karpenter-spot-lifecycle/
├── deployment.yaml  
├── lifecycle-handler.js  

🔣 Input: Spot instance termination notice  
📤 Output: App logs the event and gracefully exits  

🌍 Environment: AWS EKS with Spot provisioning  
📜 Constraints: Node must emit termination notice  
🧾 Output: Lifecycle hook prints message before termination  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Stateful apps on Spot  
💡 I want graceful shutdown logic  
🚀 Deploy: Helm  
🔐 Best Practices: Use `terminationGracePeriodSeconds`  
📥 Logs: `karpenter` + app logs before termination  
🌐 Language: English
```

---

### ✅ Prompt 13: **Pod Disruption Budget (PDB) with HPA + Karpenter**  
**🧠 Level:** Super Advanced  
```
🔧 I want to prevent aggressive downscaling.  
🎯 I want to use a Pod Disruption Budget with HPA and Karpenter to protect high-availability backend services.  
💻 Stack: EKS, HPA, Karpenter, Node.js  
📁 Structure:
pdb-karpenter-hpa/
├── deployment.yaml  
├── hpa.yaml  
├── pdb.yaml  

🔣 Input: PDB `minAvailable: 2`, HPA up to 5 pods  
📤 Output: Karpenter and HPA scale, PDB ensures stability  

🌍 Environment: AWS EKS  
📜 Constraints: Minimum pod availability enforced  
🧾 Output: Evictions restricted, PDB honored  
🔧 Experience Level: Super Advanced  
🏢 Use Case: HA backend workloads  
💡 I want full deployment with PDB + scaling  
🚀 Deploy: kubectl  
🔐 Best Practices: PDB + readiness probe = safer scaling  
📥 Logs: Eviction events + PDB status  
🌐 Language: English
```

---

### ✅ Prompt 14: **Auto-Scaling Job Queue with ScaledJob and Workload Identity**  
**🧠 Level:** Super Advanced  
```
🔧 I want event-driven scaling for background jobs.  
🎯 I want to use KEDA’s ScaledJob on EKS to scale workers based on an SQS queue using IAM Roles for Service Accounts.  
💻 Stack: AWS EKS, KEDA, SQS, Node.js  
📁 Structure:
keda-scaledjob-irsa/
├── scaledjob.yaml  
├── serviceaccount.yaml  
├── sqs-listener.js  

🔣 Input: SQS queue depth  
📤 Output: New pods spawn when messages arrive  

🌍 Environment: AWS EKS, IRSA  
📜 Constraints: SQS IAM role attached to SA  
🧾 Output: Queue messages processed at scale  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Background job system  
💡 I want ScaledJob YAML + IRSA setup  
🚀 Deploy: Helm + AWS CLI  
🔐 Best Practices: Use `maxReplicaCount` + timeouts  
📥 Logs: KEDA controller + pod logs  
🌐 Language: English
```

---

### ✅ Prompt 15: **Fullstack Autoscaling with Ingress-Based Traffic Split**  
**🧠 Level:** Super Advanced  
```
🔧 I’m testing A/B autoscaling.  
🎯 I want to deploy 2 versions of a fullstack app (v1, v2), route traffic via Ingress, and autoscale each version separately using HPA.  
💻 Stack: React, Node.js, NGINX Ingress, HPA  
📁 Structure:
fullstack-ingress-ab-hpa/
├── v1-backend/  
├── v2-backend/  
├── frontend/  
├── hpa-v1.yaml  
├── hpa-v2.yaml  
├── ingress.yaml  

🔣 Input: 80% traffic to v1, 20% to v2  
📤 Output: HPA scales pods for both versions independently  

🌍 Environment: AWS EKS with NGINX Ingress  
📜 Constraints: Must track Ingress traffic to both backends  
🧾 Output: 2 HPA resources with different scaling behavior  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Feature testing and canary autoscaling  
💡 I want Ingress-based A/B autoscaling demo  
🚀 Deploy: Helm + YAML  
🔐 Best Practices: Use weighted routing + metrics  
📥 Logs: HPA status per version  
🌐 Language: English
```

---

### ✅ Prompt 16: **GPU-Based Auto-Scaling with Karpenter for ML Workloads**  
**🧠 Level:** Super Advanced  
```
🔧 I want to autoscale GPU resources for training jobs.  
🎯 I want Karpenter to provision EC2 GPU instances dynamically for a TensorFlow job.  
💻 Stack: Karpenter, TensorFlow, AWS EKS, EC2 GPU  
📁 Structure:
karpenter-gpu-autoscale/
├── provisioner-gpu.yaml  
├── training-job.yaml  

🔣 Input: TensorFlow pod with `nvidia.com/gpu` request  
📤 Output: Karpenter schedules pod on new GPU node  

🌍 Environment: AWS EKS, GPU node support  
📜 Constraints: AMI + drivers must support NVIDIA  
🧾 Output: ML job completes on provisioned GPU  
🔧 Experience Level: Super Advanced  
🏢 Use Case: ML training on-demand  
💡 I want GPU auto-scaler with Karpenter  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Use tolerations and node selectors  
📥 Logs: GPU metrics + Karpenter scaling logs  
🌐 Language: English
```

---

### ✅ Prompt 17: **Reactive Scaling with Prometheus + AlertManager Trigger**  
**🧠 Level:** Super Advanced  
```
🔧 I want scaling based on alert conditions.  
🎯 I want to scale a service when Prometheus alerts exceed a threshold using KEDA’s Prometheus scaler.  
💻 Stack: Prometheus, KEDA, EKS  
📁 Structure:
prometheus-keda-scale/
├── scaledobject.yaml  
├── prometheus-rule.yaml  

🔣 Input: CPU usage alert  
📤 Output: Trigger pod scaling when alert fires  

🌍 Environment: AWS EKS  
📜 Constraints: Prometheus metrics must be exposed  
🧾 Output: Alert triggers scaler → pod increase  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Reactive alert-based autoscaling  
💡 I want alert rule + scaled object setup  
🚀 Deploy: Helm  
🔐 Best Practices: Avoid alert flapping  
📥 Logs: AlertManager + KEDA scaler logs  
🌐 Language: English
```

---

### ✅ Prompt 18: **Autoscale CronJobs Based on Queue Length with KEDA**  
**🧠 Level:** Super Advanced  
```
🔧 I want to scale CronJob runs based on queue backlog.  
🎯 I want to use KEDA to schedule and scale a Kubernetes CronJob dynamically based on Redis length.  
💻 Stack: EKS, KEDA, Redis, Node.js  
📁 Structure:
scaled-cronjob-redis/
├── scaledjob.yaml  
├── cronjob-template.yaml  

🔣 Input: Redis queue > 100  
📤 Output: CronJobs run in parallel when load is high  

🌍 Environment: AWS EKS  
📜 Constraints: Redis URI in secret  
🧾 Output: Scaled job runs on trigger  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Queue-based scheduled workloads  
💡 I want CronJob template with KEDA scaler  
🚀 Deploy: Helm + YAML  
🔐 Best Practices: Use TTLSecondsAfterFinished  
📥 Logs: `kubectl get jobs` + `kubectl logs`  
🌐 Language: English
```

---

### ✅ Prompt 19: **Auto-Scaling StatefulSet with Custom Metrics**  
**🧠 Level:** Super Advanced  
```
🔧 I want to autoscale a StatefulSet.  
🎯 I want to scale MongoDB StatefulSet based on disk IOPS metrics using custom Prometheus metrics.  
💻 Stack: EKS, StatefulSet, Prometheus Adapter  
📁 Structure:
stateful-hpa-custom/
├── statefulset.yaml  
├── hpa.yaml  

🔣 Input: IOPS custom metric  
📤 Output: Replica scale-up if metric breached  

🌍 Environment: AWS EKS + Prometheus  
📜 Constraints: Persistent volume metrics must be exposed  
🧾 Output: StatefulSet scaled based on disk pressure  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Stateful DB under load  
💡 I want StatefulSet scaling config  
🚀 Deploy: kubectl  
🔐 Best Practices: Respect pod identity  
📥 Logs: Prometheus metrics + HPA status  
🌐 Language: English
```

---

### ✅ Prompt 20: **Karpenter + HPA + VPA Hybrid Autoscaling Simulation**  
**🧠 Level:** Super Advanced  
```
🔧 I want full hybrid autoscaling.  
🎯 I want to deploy an app that uses HPA for pod scaling, Karpenter for node scaling, and VPA to tune resource requests.  
💻 Stack: EKS, Karpenter, HPA, VPA, Node.js  
📁 Structure:
hybrid-autoscale/
├── deployment.yaml  
├── hpa.yaml  
├── vpa.yaml  
├── provisioner.yaml  

🔣 Input: CPU stress test  
📤 Output: VPA adjusts requests, HPA adds pods, Karpenter adds nodes  

🌍 Environment: AWS EKS  
📜 Constraints: VPA must be in recommendation mode  
🧾 Output: Logs from all 3 autoscalers  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Intelligent self-scaling infrastructure  
💡 I want full hybrid setup with inline comments  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: VPA in recommend-only for HPA compatibility  
📥 Logs: HPA + VPA + Karpenter logs  
🌐 Language: English
```

---

