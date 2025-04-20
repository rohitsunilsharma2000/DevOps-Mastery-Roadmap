## 🧭 Kubernetes Week 3: Helm Charts & StatefulSets – 20 Hands-On Labs (Beginner to Super Advanced)
---



### ✅ Prompt 1: Helm Install Bitnami Nginx  
**Level:** Easy  
```
🔧 I am a beginner DevOps engineer.  
🎯 I want to install an Nginx server using a public Helm chart.  
💻 Stack: Kubernetes, Helm, Bitnami, Nginx  
📁 Structure:
nginx-helm-install/
├── helm-install.sh  

🔣 Input: `helm install my-nginx bitnami/nginx`  
📤 Output: Running pod, NodePort exposed  

🌍 Environment: Minikube on macOS  
📜 Constraints: No chart modification, expose with service  
🧾 Format: CLI + Helm output + test curl  
🏢 Use case: Basic public chart installation  
💡 I want CLI + YAML output explanation  
🚀 Deploy: Minikube  
🔐 Best practices: Use `--namespace`, never run `--force` in prod  
```

---

### ✅ Prompt 2: View and Modify values.yaml  
**Level:** Easy  
```
🔧 I am a beginner DevOps engineer.  
🎯 I want to install the Bitnami Nginx chart with custom port and replica count using `values.yaml`.  
💻 Stack: Helm, Kubernetes, YAML  
📁 Structure:
nginx-custom-values/
├── values.yaml  
├── install.sh  

🔣 Input: `replicaCount: 2`, `service.port: 8080`  
📤 Output: Nginx with 2 replicas on port 8080  

🧾 Format: values.yaml + CLI  
🚀 Deploy: Helm  
💡 I want Helm override examples  
📥 Logs: `kubectl get svc`, `describe` if port not set  
```

---

### ✅ Prompt 3: Create and Package Your Own Helm Chart  
**Level:** Medium  
```
🔧 I am a DevOps engineer.  
🎯 I want to create a Helm chart for a custom Node.js API backend.  
💻 Stack: Node.js, Express, Helm, Kubernetes  
📁 Structure:
node-api-chart/
├── Chart.yaml  
├── values.yaml  
├── templates/  
│   ├── deployment.yaml  
│   ├── service.yaml  

🔣 Input: Backend image, env variables  
📤 Output: `/health` API accessible via NodePort  

🧾 Format: Chart files + commands  
🏢 Use case: Reusable API backend chart  
🚀 Deploy: Helm install from local  
💡 I want chart skeleton with inline docs  
```

---

### ✅ Prompt 4: Use Helm Hooks to Create DB Init Job  
**Level:** Medium  
```
🔧 I am a backend engineer.  
🎯 I want to use Helm post-install hook to run a DB migration Job.  
💻 Stack: Node.js, Postgres, Helm  
📁 Structure:
backend-chart/
├── templates/db-job.yaml (hook)  

🔣 Input: Init script in container  
📤 Output: Job runs once after install  

💡 I want post-install hook example with logs  
🚀 Deploy: Helm with Job hook  
📥 Logs: `kubectl get jobs`, `describe`  
```

---

### ✅ Prompt 5: StatefulSet for MongoDB with PVC  
**Level:** Medium  
```
🔧 I’m a DevOps engineer deploying a database.  
🎯 I want to deploy MongoDB as a StatefulSet with persistent volume claims.  
💻 Stack: MongoDB, Helm, Kubernetes  
📁 Structure:
mongodb-stateful/
├── statefulset.yaml  
├── service.yaml  
├── pvc.yaml  

🔣 Input: 2 replicas with `volumeClaimTemplates`  
📤 Output: Persistent pods `mongo-0`, `mongo-1`  

🧾 Format: YAML + verification  
🏢 Use case: Persistent DB deployment  
🚀 Deploy: Helm chart or raw manifests  
💡 I want StatefulSet template with volume  
```

---

### ✅ Prompt 6: Fullstack Chart with React + Express  
**Level:** Hard  
```
🔧 I’m a fullstack engineer.  
🎯 I want to deploy a React frontend and Express backend using one Helm chart with subcharts.  
💻 Stack: React, Node.js, MongoDB, Helm  
📁 Structure:
fullstack-chart/
├── charts/backend/  
├── charts/frontend/  
├── values.yaml  

🔣 Input: Mongo URI via secret  
📤 Output: Web app loaded with backend API  

🚀 Deploy: `helm install webapp ./fullstack-chart`  
🧾 Output: UI visible on NodePort  
💡 I want example with subcharts and overrides  
```

---

### ✅ Prompt 7: Helm Rollback Simulation  
**Level:** Medium  
```
🔧 I am a DevOps engineer.  
🎯 I want to simulate a broken chart deployment and perform a Helm rollback.  
💻 Stack: Helm, Kubernetes  
📁 Structure:
rollback-demo/
├── good-values.yaml  
├── bad-values.yaml  

🔣 Input: Install → upgrade with bad config → rollback  
📤 Output: App returns to stable state  

🚀 Deploy: `helm rollback`  
🧾 Output: History from `helm history`  
💡 I want lifecycle with rollback tips  
```

---

### ✅ Prompt 8: Chart for Django + Redis with Dependencies  
**Level:** Hard  
```
🔧 I’m a backend engineer.  
🎯 I want to deploy Django and Redis using Helm with dependencies.  
💻 Stack: Python Django, Redis, Helm  
📁 Structure:
django-chart/
├── requirements.yaml  
├── charts/redis  

🔣 Input: Django app image and Redis password  
📤 Output: Django connected to Redis  

🚀 Deploy: `helm dependency update && helm install`  
🧾 Output: Django web page + Redis cache  
💡 I want dependency injection with `values.yaml`  
```

---

### ✅ Prompt 9: Helm Upgrade with GitHub Actions  
**Level:** Hard  
```
🔧 I’m a DevOps engineer working on GitOps.  
🎯 I want to create a GitHub Actions CI/CD pipeline that upgrades a Helm release on every push.  
💻 Stack: Helm, GitHub Actions, Kubernetes  
📁 Structure:
.github/workflows/deploy.yaml  
values.yaml  

🔣 Input: Git commit  
📤 Output: Helm release upgraded automatically  

🚀 Deploy: Self-hosted cluster  
🧾 Output: GitHub Actions logs  
💡 I want CI pipeline and helm upgrade strategy  
```

---

### ✅ Prompt 10: Helm Chart with Ingress, TLS, and HPA  
**Level:** Super Advanced  
```
🔧 I’m a senior DevOps engineer.  
🎯 I want to create a production-grade Helm chart with Ingress (TLS), HPA, and secrets for backend.  
💻 Stack: Node.js, Ingress NGINX, Cert-Manager, Helm  
📁 Structure:
prod-ready-chart/
├── templates/  
│   ├── ingress.yaml  
│   ├── hpa.yaml  
│   ├── secrets.yaml  

🔣 Input: Autoscaling, Ingress with `cert-manager.io/` annotations  
📤 Output: TLS-enabled public app with HPA  

🚀 Deploy: GKE or Minikube with cert-manager  
🧾 Output: HTTPS access, autoscaled pods  
💡 I want reusable production pattern chart  
```

---

## 🔥 10 Super Advanced Only

---

### ✅ Prompt A1: **Cassandra StatefulSet with Headless Service & DNS**
**🧠 Level:** Super Hard  
```
🔧 I am a senior DevOps engineer.  
🎯 I want to deploy a multi-node Cassandra cluster using Helm, StatefulSet, and a headless Service to enable pod-to-pod DNS resolution.  
💻 Tech Stack: Kubernetes, Helm, Cassandra, StatefulSet  
📁 Structure:
cassandra-cluster-chart/
├── templates/
│   ├── statefulset.yaml
│   ├── service-headless.yaml  
│   └── configmap.yaml  
├── values.yaml  

🔣 Input: 3 replicas, custom cluster name, peer discovery via DNS  
📤 Output: Pod names like `cassandra-0.cassandra.default.svc.cluster.local`  

🌍 Environment: Minikube or AWS EKS  
📜 Constraints: Persistent storage via `volumeClaimTemplates`, use headless service only  
🧾 Output format: YAML + pod DNS resolution example  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Real-time analytics, horizontally scalable NoSQL DB  
💡 I want a production-ready StatefulSet Helm chart with inline documentation  
🚀 Deployment: Helm CLI with storageClass and PVC  
🔐 Best Practices: Use readinessProbe, antiAffinity rules, and correct storage provisioning  
📥 Logs: Show DNS resolution with `nslookup` or `ping` between pods  
🌐 Language: English
```

---

### ✅ Prompt A2: **Blue-Green Deployment Using Helm values.yaml**
**🧠 Level:** Super Hard  
```
🔧 I am a senior DevOps engineer working on safe release strategies.  
🎯 I want to implement a blue-green deployment mechanism via Helm, using custom `values.yaml` to switch active environments.  
💻 Tech Stack: Helm, Kubernetes, Ingress NGINX, Node.js  
📁 Structure:
bluegreen-app/
├── values-blue.yaml  
├── values-green.yaml  
├── templates/
│   ├── deployment.yaml
│   ├── ingress.yaml  

🔣 Input: values with label `env: blue` or `env: green`  
📤 Output: Ingress routes to the active deployment only  

🌍 Environment: Minikube or GKE  
📜 Constraints: Use Helm `--values` flag for switching, no downtime  
🧾 Output format: YAML + before-after traffic test  
🔧 Experience Level: Super Advanced  
🏢 Use Case: CI/CD zero-downtime safe release  
💡 I want Helm chart with multiple environment overlays and ingress switching  
🚀 Deployment: Helm CLI + custom `values-{env}.yaml`  
🔐 Best Practices: Keep blue and green completely isolated and use sticky sessions if needed  
📥 Logs: Test using `curl` + describe ingress  
🌐 Language: English
```

---

### ✅ Prompt A3: **Canary Deployment with Helm and Label Selectors**
**🧠 Level:** Super Hard  
```
🔧 I am a DevOps lead managing progressive rollouts.  
🎯 I want to configure a canary release using Helm where 10% of traffic goes to a labeled pod set.  
💻 Tech Stack: Kubernetes, Helm, Node.js, Ingress NGINX  
📁 Structure:
canary-app/
├── templates/
│   ├── deployment-canary.yaml
│   ├── deployment-stable.yaml
│   ├── service.yaml
│   ├── ingress.yaml  

🔣 Input: 90% traffic to `stable`, 10% to `canary`  
📤 Output: Canary pod gets only 10% requests via label-based selector  

🌍 Environment: GKE or Minikube with NGINX ingress  
📜 Constraints: Use two deployments, one Service with weighted backends  
🧾 Output format: YAML + traffic test results  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Rolling out feature flags or risk-prone APIs  
💡 I want Helm chart with dynamic label-based routing  
🚀 Deployment: Helm + optional TrafficSplit/ServiceMesh  
🔐 Best Practices: Monitor canary with Prometheus alerts  
📥 Logs: Show `curl` output across multiple runs + pod logs  
🌐 Language: English
```

---

### ✅ Prompt A4: **Inject Kubernetes Secrets from HashiCorp Vault via Helm**
**🧠 Level:** Super Hard  
```
🔧 I am a security-conscious DevOps engineer.  
🎯 I want to configure a Helm chart to pull secrets dynamically from HashiCorp Vault using Vault Agent injector.  
💻 Tech Stack: Kubernetes, Helm, HashiCorp Vault, Node.js  
📁 Structure:
vault-app-chart/
├── templates/
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── annotations.yaml  
├── values.yaml  

🔣 Input: Vault secret path, role, and mount  
📤 Output: Pod starts with env injected from Vault  

🌍 Environment: EKS or Minikube + Vault  
📜 Constraints: Use Vault Agent + annotations  
🧾 Output format: YAML, Vault config, curl test  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Secure credential delivery at runtime  
💡 I want secure Vault + Helm integration pattern  
🚀 Deployment: Vault injector sidecar + Helm install  
🔐 Best Practices: Use AppRole auth, renew tokens, do not log secrets  
📥 Logs: Check injected secret with `cat /vault/secrets/...`  
🌐 Language: English
```

---

### ✅ Prompt A5: **Helm Chart with Docker Private Registry Auth**
**🧠 Level:** Super Hard  
```
🔧 I am managing private container deployments.  
🎯 I want to add image pull secret support in a Helm chart to pull from a private Docker registry.  
💻 Tech Stack: Docker Hub, Kubernetes, Helm  
📁 Structure:
private-app-chart/
├── templates/
│   ├── deployment.yaml  
├── values.yaml  
├── secrets.yaml  

🔣 Input: Docker registry creds in values  
📤 Output: App pulls private image successfully  

🌍 Environment: Minikube or GKE  
📜 Constraints: Use `imagePullSecrets` injected via Helm  
🧾 Output format: YAML + CLI  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Enterprises using private image registries  
💡 I want reusable Helm logic to inject pull secrets  
🚀 Deployment: Helm chart with encoded creds  
🔐 Best Practices: Use Secret with `.dockerconfigjson`  
📥 Logs: Pod fails with `ImagePullBackOff` if misconfigured  
🌐 Language: English
```

---

### ✅ Prompt A6: **Multi-Environment Helm Chart with Overrides**
**🧠 Level:** Super Hard  
```
🔧 I manage dev, QA, and prod environments.  
🎯 I want to create a single Helm chart with multiple `values-{env}.yaml` files for seamless multi-env deployments.  
💻 Tech Stack: Helm, Kubernetes, Node.js  
📁 Structure:
multi-env-app/
├── values-dev.yaml  
├── values-qa.yaml  
├── values-prod.yaml  
├── templates/  

🔣 Input: App replicas, env-specific DB URIs  
📤 Output: Customized deployments per environment  

🌍 Environment: All cloud or local environments  
📜 Constraints: One chart, many `-f` overrides  
🧾 Output format: YAML + example helm install commands  
🔧 Experience Level: Super Advanced  
🏢 Use Case: GitOps-ready deployment pipeline  
💡 I want reusable multi-env chart structure  
🚀 Deployment: `helm install app -f values-dev.yaml`  
🔐 Best Practices: Use `.Release.Namespace` and `.Values.env`  
📥 Logs: Validate with `kubectl get all -n env`  
🌐 Language: English
```

---

### ✅ Prompt A7: **Create Helm Repo & Publish Custom Chart**
**🧠 Level:** Super Hard  
```
🔧 I maintain reusable infrastructure code.  
🎯 I want to package my custom Helm chart and publish it to a private Helm repository using GitHub Pages or ChartMuseum.  
💻 Tech Stack: Helm, GitHub Pages / ChartMuseum, Kubernetes  
📁 Structure:
my-awesome-chart/
├── Chart.yaml  
├── values.yaml  
├── templates/  
├── index.yaml (repo)  

🔣 Input: Chart tarball  
📤 Output: Helm repo served via HTTP  

🌍 Environment: GitHub Pages or local ChartMuseum  
📜 Constraints: Use `helm repo index` and `helm push`  
🧾 Output format: CLI + README sample  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Internal DevOps chart registry  
💡 I want Helm repo setup and example URL install  
🚀 Deployment: `helm install mychart myrepo/mychart`  
🔐 Best Practices: Version charts, sign with provenance  
📥 Logs: `helm search repo` and repo index response  
🌐 Language: English
```

---

### ✅ Prompt A8: **Kafka Cluster with StatefulSet and Helm**
**🧠 Level:** Super Hard  
```
🔧 I am deploying big data infra.  
🎯 I want to deploy a 3-node Kafka cluster using StatefulSet Helm chart with persistence and external access.  
💻 Tech Stack: Helm, Kafka, Kubernetes, Zookeeper  
📁 Structure:
kafka-cluster-chart/
├── templates/statefulset.yaml  
├── values.yaml  

🔣 Input: Brokers = 3, storage PVCs, headless service  
📤 Output: Kafka nodes `broker-0`, `broker-1`, `broker-2`  

🌍 Environment: GKE / Minikube  
📜 Constraints: External access via NodePort or LoadBalancer  
🧾 Output format: YAML + Kafka CLI test  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Event streaming platform  
💡 I want StatefulSet Kafka + Zookeeper deployment  
🚀 Deployment: Helm install with proper PVC & ports  
🔐 Best Practices: Use unique broker IDs, configure ISR  
📥 Logs: Kafka pod logs + producer/consumer shell  
🌐 Language: English
```

---

### ✅ Prompt A9: **Helm + ArgoCD GitOps Auto Sync**
**🧠 Level:** Super Hard  
```
🔧 I’m implementing GitOps CI/CD.  
🎯 I want to configure ArgoCD to auto-sync a Helm-based app from a GitHub repo.  
💻 Tech Stack: Helm, ArgoCD, Kubernetes, GitHub  
📁 Structure:
argo-helm-app/
├── application.yaml  
├── helm/  
│   ├── Chart.yaml  
│   ├── templates/  

🔣 Input: GitHub repo with Helm chart  
📤 Output: App auto-synced in ArgoCD UI  

🌍 Environment: ArgoCD in Minikube or EKS  
📜 Constraints: Must auto-sync with Helm chart  
🧾 Output format: YAML + ArgoCD dashboard  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Production GitOps pipeline  
💡 I want ArgoCD app.yaml and Helm integration  
🚀 Deployment: ArgoCD UI or CLI  
🔐 Best Practices: Use `syncPolicy: automated`  
📥 Logs: ArgoCD app events + Helm release log  
🌐 Language: English
```

---

### ✅ Prompt A10: **Fullstack Real-Time Chat App with Helm + Ingress + HPA**
**🧠 Level:** Super Hard  
```
🔧 I am a fullstack engineer building a scalable real-time app.  
🎯 I want to deploy a real-time chat app with React frontend, Node.js backend, Redis pub-sub, secured with TLS Ingress, HPA, and secrets via Helm.  
💻 Tech Stack: React, Node.js, Redis, Kubernetes, Helm, Cert-Manager  
📁 Structure:
chatapp-chart/
├── charts/backend/  
├── charts/frontend/  
├── templates/
│   ├── ingress.yaml  
│   ├── hpa.yaml  
│   ├── secret.yaml  

🔣 Input: WebSocket server, Redis URI, TLS enabled domain  
📤 Output: Scalable chat app with secure HTTPS URL  

🌍 Environment: GKE / Minikube with NGINX + Cert-Manager  
📜 Constraints: Real-time, stateless frontend, pub-sub backend  
🧾 Output format: YAML + UI + autoscaling test  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Slack-style secure chat app  
💡 I want HPA, Ingress, TLS, and secrets in Helm  
🚀 Deployment: Helm install with domain override  
🔐 Best Practices: Use HPA with CPU + connection metrics  
📥 Logs: WebSocket connections + HPA scale events  
🌐 Language: English
```

---
