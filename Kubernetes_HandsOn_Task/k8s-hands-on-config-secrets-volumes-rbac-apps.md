## Kubernetes Essentials: 10 Practical Labs on Config, Secrets, Storage, and Access Control
---

### ✅ Prompt 1: ConfigMap with Node.js App  
```
🔧 I am a DevOps engineer learning Kubernetes basics.  
🎯 I want to deploy a Node.js app using a Kubernetes ConfigMap to externalize values like PORT and APP_NAME.  
💻 Tech Stack: Node.js, Express, Docker, Kubernetes (Minikube)  
📁 Folder structure:
node-configmap-demo/
├── app/
│   ├── index.js
│   └── Dockerfile
├── k8s/
│   ├── configmap.yaml
│   ├── deployment.yaml
│   └── service.yaml  

🔣 Input: ConfigMap with PORT=3000 and APP_NAME=HelloKube  
📤 Output: `/` endpoint returns "Hello from HelloKube"  

🌍 Environment: Minikube on macOS  
📜 Constraints: Beginner-level, no sensitive data, should expose via NodePort  
🧾 Output format: Code + YAML files + command-line steps  
🔧 Experience level: Beginner  
🏢 Use case: Can be extended to config-driven microservices  
💡 I want code generation and best practices  
🚀 Deployment: Minikube (local)  
🔐 Security tips: Avoid secrets in ConfigMap  
📥 Logs: If service fails, provide pod logs and common misconfigurations  
🌐 Language: English
```

---

### ✅ Prompt 2: Secrets with Flask App  
```
🔧 I am a DevOps engineer learning how to secure application secrets.  
🎯 I want to pass an API key securely to a Flask app using Kubernetes Secrets (mounted as env var).  
💻 Tech Stack: Python, Flask, Docker, Kubernetes  
📁 Structure:
flask-secret-api/
├── app.py
├── Dockerfile
├── k8s/
│   ├── secret.yaml
│   ├── deployment.yaml
│   └── service.yaml  

🔣 Input: Secret with API_KEY=12345ABCDEF  
📤 Output: `/secret` returns "Your API key is 12345ABCDEF"  

🌍 Environment: Minikube on Ubuntu  
📜 Constraints: Key must not be logged or hardcoded  
🧾 Output format: Flask code + YAML + README  
🔧 Experience level: Beginner  
🏢 Use case: Any backend interacting with external APIs  
💡 I want code generation with inline comments  
🚀 Deployment: Kubernetes via Minikube  
🔐 Best practices: Avoid mounting Secrets as volumes in shared pods  
📥 Logs: If API_KEY is missing, show example traceback  
🌐 Language: English
```

---

### ✅ Prompt 3: emptyDir Volume Sharing Between Containers  
```
🔧 I am a DevOps learner trying to understand volumes and inter-container communication.  
🎯 I want to use emptyDir to share data between two containers in the same pod (one writes, one reads).  
💻 Tech Stack: Shell script in Alpine image, Kubernetes  
📁 Structure:
emptydir-demo/
├── writer.sh
├── reader.sh
├── k8s/
│   ├── pod.yaml  

🔣 Input: Writer script creates /shared/data.txt  
📤 Output: Reader container logs contents of data.txt  

🌍 Environment: Minikube (Linux)  
📜 Constraints: Temporary data only during pod lifecycle  
🧾 Output format: YAML and sample shell output  
🔧 Experience level: Beginner  
🏢 Use case: Simulating shared cache, inter-process communication  
💡 I want YAML + shell script generation  
🚀 Deployment: Local Minikube  
🔐 Security: Set read-only mount for reader  
📥 Logs: Show reader container log using `kubectl logs`  
🌐 Language: English
```

---

### ✅ Prompt 4: PersistentVolume with Spring Boot File Upload  
```
🔧 I’m a backend + DevOps developer building a file upload app.  
🎯 I want to persist uploaded files in Kubernetes using PVC (hostPath or local PV).  
💻 Tech Stack: Java Spring Boot, Docker, Kubernetes  
📁 Structure:
springboot-pvc-upload/
├── src/
├── Dockerfile
├── k8s/
│   ├── pvc.yaml
│   ├── deployment.yaml
│   └── service.yaml  

🔣 Input: Multipart file upload to `/upload`  
📤 Output: Files persist in mounted path even after container restart  

🌍 Environment: Minikube on Linux  
📜 Constraints: Avoid in-memory storage; reuse across pod restarts  
🧾 Output format: Java controller, YAML files  
🔧 Experience level: Intermediate  
🏢 Use case: Upload service in a microservices ecosystem  
💡 I want backend code and full deployment config  
🚀 Deployment: PVC + hostPath  
🔐 Best practices: Use StorageClass in cloud setups  
📥 Logs: Describe what to expect if PVC not bound  
🌐 Language: English
```

---

### ✅ Prompt 5: Role-Based Access Control (RBAC)  
```
🔧 I am a DevOps engineer exploring Kubernetes security.  
🎯 I want to create a Role that allows a pod to list resources and bind it to a ServiceAccount.  
💻 Tech Stack: Kubernetes  
📁 Structure:
rbac-pod-list-demo/
├── service-account.yaml
├── role.yaml
├── rolebinding.yaml
├── pod.yaml  

🔣 Input: Create Role with `get`, `list` on pods  
📤 Output: Pod can run `kubectl get pods` using mounted SA credentials  

🌍 Environment: Minikube (or GKE if applicable)  
📜 Constraints: SA should only work in one namespace  
🧾 Output format: YAML with explanation  
🔧 Experience level: Intermediate  
🏢 Use case: Monitoring pod for observability tools  
💡 I want YAML + step-by-step RBAC validation steps  
🚀 Deployment: Kubernetes role + SA  
🔐 Best practices: Avoid ClusterRole unless needed  
📥 Logs: If permission denied, provide exact log from pod  
🌐 Language: English
```

---

### ✅ Prompt 6: Fullstack App with Secrets and ConfigMap  
```
🔧 I am a fullstack developer learning Kubernetes config and secret management.  
🎯 I want to build a fullstack (React + Node.js) app where backend loads env vars from ConfigMap and Secrets, and frontend displays it.  
💻 Tech Stack: Node.js, React, Docker, Kubernetes  
📁 Structure:
config-secret-ui/
├── backend/
│   ├── server.js
│   └── Dockerfile
├── frontend/
│   ├── App.js
│   └── Dockerfile
├── k8s/
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── backend-deployment.yaml
│   ├── frontend-deployment.yaml
│   └── services.yaml  

🔣 Input: ConfigMap(APP_NAME) and Secret(API_KEY)  
📤 Output: UI displays "App: APP_NAME, Key: API_KEY"  

🌍 Environment: Minikube  
📜 Constraints: Must mount values as env in backend  
🧾 Output format: Code + YAML + screenshots  
🔧 Experience level: Intermediate  
🏢 Use case: Configuration-driven UI behavior  
💡 I want code generation and security guidance  
🚀 Deployment: Kubernetes with NodePort  
🔐 Best practices: Only expose what is needed to frontend  
📥 Logs: Handle React CORS or fetch issues if backend is unreachable  
🌐 Language: English
```

---

### ✅ Prompt 7: ClusterRole + Audit Logs  
```
🔧 I am a DevOps engineer implementing least-privilege access.  
🎯 I want to create a ClusterRole, bind it, and verify via audit logs whether unauthorized actions are blocked.  
💻 Tech Stack: Kubernetes (with audit logging enabled)  
📁 Structure:
rbac-audit-demo/
├── clusterrole.yaml
├── clusterrolebinding.yaml
├── serviceaccount.yaml
├── pod.yaml  

🔣 Input: ClusterRole with limited pod access  
📤 Output: Unauthorized API actions show in audit log  

🌍 Environment: Minikube with audit policy  
📜 Constraints: Read-only access to pods  
🧾 Output format: YAML + `audit.log` example  
🔧 Experience level: Advanced  
🏢 Use case: Compliance checks and security audits  
💡 I want YAML files and help interpreting logs  
🚀 Deployment: K8s with custom audit policy  
🔐 Best practices: Validate audit policies per namespace  
📥 Logs: Include sample from `/var/log/audit.log`  
🌐 Language: English
```

---

### ✅ Prompt 8: PostgreSQL PVC + Backup with CronJob  
```
🔧 I am a DevOps engineer deploying stateful apps.  
🎯 I want to run PostgreSQL using a PVC, and set up a Kubernetes CronJob that backs up the DB regularly to a volume.  
💻 Tech Stack: PostgreSQL, Kubernetes, Docker, PVC, CronJob  
📁 Structure:
postgres-backup/
├── postgres-deployment.yaml
├── pvc.yaml
├── cronjob-backup.yaml  

🔣 Input: DB data and `pg_dump` output  
📤 Output: Backups are persisted daily in `/backup` volume  

🌍 Environment: Minikube or AWS EKS  
📜 Constraints: Must use local PV or hostPath  
🧾 Output format: YAML + optional bash backup script  
🔧 Experience level: Advanced  
🏢 Use case: Backup automation for stateful apps  
💡 I want YAMLs with logging examples  
🚀 Deployment: Local PV with CronJob  
🔐 Best practices: Store backups off-cluster for disaster recovery  
📥 Logs: Show successful CronJob and backup file presence  
🌐 Language: English
```

---

### ✅ Prompt 9: Feature Flags in React from ConfigMap  
```
🔧 I’m a frontend developer enabling feature toggles using backend config.  
🎯 I want to externalize feature flags using ConfigMap and render flags in the React UI.  
💻 Tech Stack: React, Kubernetes, ConfigMap, Node.js  
📁 Structure:
feature-flag-ui/
├── backend/
│   ├── index.js
├── frontend/
│   ├── App.js
├── k8s/
│   ├── configmap.yaml
│   ├── deployments.yaml
│   └── services.yaml  

🔣 Input: ConfigMap with FEATURE_X_ENABLED=true  
📤 Output: UI shows "Feature X: Enabled"  

🌍 Environment: Minikube  
📜 Constraints: ConfigMap should not need frontend rebuild  
🧾 Output format: ConfigMap YAML, React code  
🔧 Experience level: Advanced  
🏢 Use case: A/B testing in real-world frontend apps  
💡 I want code snippets and CI/CD integration tip  
🚀 Deployment: NodePort exposure  
🔐 Best practices: Do not hardcode logic; rely on env  
📥 Logs: React fetch error logs if endpoint fails  
🌐 Language: English
```

---

### ✅ Prompt 10: Secure Fullstack App with Secrets, PVC, RBAC  
```
🔧 I’m a fullstack DevOps engineer building a production-grade app.  
🎯 I want to build a secure React + Node.js + MongoDB app using Secrets for DB credentials, PVC for data, and RBAC for resource control.  
💻 Tech Stack: React, Node.js, MongoDB, Kubernetes, Docker  
📁 Structure:
secure-fullstack/
├── backend/
│   └── Dockerfile
├── frontend/
│   └── Dockerfile
├── mongo/
│   └── Dockerfile
├── k8s/
│   ├── secrets.yaml
│   ├── pvc.yaml
│   ├── deployments.yaml
│   ├── rbac.yaml
│   └── services.yaml  

🔣 Input: Secrets (MONGO_URI), PVC for MongoDB  
📤 Output: Fully functional app with persisted data and secured access  

🌍 Environment: Minikube or AWS  
📜 Constraints: Stateful backend + secure envs  
🧾 Output format: Full code + YAML + monitoring setup  
🔧 Experience level: Advanced  
🏢 Use case: SaaS-grade platform with user auth and data  
💡 I want full implementation with security best practices  
🚀 Deployment: Kubernetes with PVC and RBAC  
🔐 Best practices: Secure secrets, encrypt backups, use readinessProbes  
📥 Logs: MongoDB and backend logs for debugging auth failures  
🌐 Language: English
```

---

Would you like me to now:
- Create a **GitHub repo-ready folder template** for any of the above?
- Start generating **code or YAML** for one of them?

Let me know your next move!
