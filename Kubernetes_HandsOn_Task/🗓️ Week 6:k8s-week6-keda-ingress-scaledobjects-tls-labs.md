

### 🧭 KEDA Event-Driven Autoscaling & Ingress – 10 Hands-On Prompts (Beginner to Super Advanced)

---

### 📝  Subtitle:
> Real-world tasks covering KEDA autoscaling with RabbitMQ, Kafka, SQS, and Prometheus metrics; Ingress setups with NGINX, TLS, cert-manager, OAuth2, and rate-limiting — tailored for backend, frontend, and fullstack applications on Kubernetes.

---



### ✅ Prompt 1: **Install KEDA on Kubernetes Using Helm**
**🧠 Level:** Beginner  
```
🔧 I’m a beginner DevOps engineer learning autoscaling.  
🎯 I want to install KEDA in my Kubernetes cluster using Helm.  
💻 Stack: Helm, Kubernetes, KEDA  
📁 Structure:
keda-install/
├── helm-install.sh  

🔣 Input: Helm repo add + install command  
📤 Output: KEDA controller running in `keda` namespace  

🌍 Environment: Minikube or AWS EKS  
📜 Constraints: Helm 3 must be installed  
🧾 Output: `kubectl get pods -n keda` shows KEDA pods  
🔧 Experience Level: Beginner  
🏢 Use Case: Set up event-driven autoscaling  
💡 I want CLI setup and verification steps  
🚀 Deploy: Helm  
🔐 Best Practices: Pin Helm version and chart  
📥 Logs: `kubectl logs` for controller pod  
🌐 Language: English
```

---

### ✅ Prompt 2: **KEDA ScaledObject with RabbitMQ Queue Length**
**🧠 Level:** Intermediate  
```
🔧 I want to scale workers based on a queue.  
🎯 I want to configure a KEDA ScaledObject that scales a worker deployment based on RabbitMQ queue length.  
💻 Stack: KEDA, RabbitMQ, Node.js  
📁 Structure:
keda-rabbitmq/
├── scaledobject.yaml  
├── deployment.yaml  
├── secret.yaml  

🔣 Input: RabbitMQ queue length  
📤 Output: Pods scale up/down dynamically  

🌍 Environment: Minikube or EKS  
📜 Constraints: RabbitMQ URI must be in secret  
🧾 Output: `kubectl get hpa` + queue test  
🔧 Experience Level: Intermediate  
🏢 Use Case: Event-based job processing  
💡 I want full config with inline comments  
🚀 Deploy: kubectl  
🔐 Best Practices: Use `minReplicaCount`, secretRef  
📥 Logs: KEDA logs, queue length monitoring  
🌐 Language: English
```

---

### ✅ Prompt 3: **Ingress for Express Backend Using NGINX Controller**
**🧠 Level:** Intermediate  
```
🔧 I’m a backend developer.  
🎯 I want to expose my Express.js API using the NGINX Ingress controller.  
💻 Stack: Node.js, Express, NGINX Ingress, Kubernetes  
📁 Structure:
express-ingress/
├── app.js  
├── Dockerfile  
├── deployment.yaml  
├── service.yaml  
├── ingress.yaml  

🔣 Input: `/api/hello` endpoint  
📤 Output: Reachable via `http://<minikube-ip>/api/hello`  

🌍 Environment: Minikube with Ingress addon  
📜 Constraints: NGINX controller must be running  
🧾 Output: Ingress resource + curl output  
🔧 Experience Level: Intermediate  
🏢 Use Case: API routing via Ingress  
💡 I want deployment + working ingress config  
🚀 Deploy: kubectl  
🔐 Best Practices: Use `pathType: Prefix`  
📥 Logs: NGINX controller + pod logs  
🌐 Language: English
```

---

### ✅ Prompt 4: **TLS with cert-manager and Let's Encrypt (Staging)**
**🧠 Level:** Intermediate  
```
🔧 I want to secure my app with HTTPS.  
🎯 I want to configure Ingress with cert-manager and use Let’s Encrypt staging issuer to provision a TLS cert.  
💻 Stack: cert-manager, Ingress, Kubernetes  
📁 Structure:
tls-certmanager/
├── issuer.yaml  
├── certificate.yaml  
├── ingress.yaml  

🔣 Input: Valid public domain with DNS A record  
📤 Output: TLS cert provisioned and HTTPS active  

🌍 Environment: EKS or Minikube with domain + DNS  
📜 Constraints: Use Let’s Encrypt staging, not prod  
🧾 Output: Valid TLS from `curl -v https://...`  
🔧 Experience Level: Intermediate  
🏢 Use Case: Secure public services  
💡 I want sample issuer + cert + ingress YAMLs  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Start with staging before using prod  
📥 Logs: cert-manager logs for provisioning status  
🌐 Language: English
```

---

### ✅ Prompt 5: **KEDA ScaledJob for Parallel Processing of SQS Messages**
**🧠 Level:** Hard  
```
🔧 I want to autoscale a batch job on events.  
🎯 I want to use KEDA’s ScaledJob to process AWS SQS messages concurrently in Kubernetes.  
💻 Stack: KEDA, AWS SQS, Node.js, EKS  
📁 Structure:
keda-sqs-scaledjob/
├── scaledjob.yaml  
├── sqs-listener.js  
├── serviceaccount.yaml  

🔣 Input: SQS message queue  
📤 Output: Multiple pods spin up per message burst  

🌍 Environment: AWS EKS with IRSA  
📜 Constraints: IAM role for SQS access  
🧾 Output: Messages processed by parallel pods  
🔧 Experience Level: Hard  
🏢 Use Case: Async event processing  
💡 I want ScaledJob + IRSA + Node.js example  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Set `maxReplicaCount` to avoid overrun  
📥 Logs: SQS logs + job pod logs  
🌐 Language: English
```

---

### ✅ Prompt 6: **Fullstack App with Ingress + TLS + Autoscaling**
**🧠 Level:** Hard  
```
🔧 I’m deploying a fullstack web app securely.  
🎯 I want to expose a React + Node.js app using Ingress with TLS, and autoscale the backend with HPA.  
💻 Stack: React, Node.js, HPA, Ingress, cert-manager  
📁 Structure:
secure-fullstack/
├── backend/  
├── frontend/  
├── ingress.yaml  
├── certificate.yaml  
├── hpa.yaml  

🔣 Input: `/api/` + `/` routes  
📤 Output: Secure app on HTTPS with scaling backend  

🌍 Environment: AWS EKS  
📜 Constraints: Valid domain + staging cert  
🧾 Output: `https://domain.com` shows UI + hits API  
🔧 Experience Level: Hard  
🏢 Use Case: Secure scalable SaaS  
💡 I want Ingress + cert-manager + HPA in one stack  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Split frontend and backend paths  
📥 Logs: HPA events + cert-manager status  
🌐 Language: English
```

---

### ✅ Prompt 7: **Kafka-Based Autoscaling with KEDA + Strimzi Operator**
**🧠 Level:** Super Advanced  
```
🔧 I’m building an event-streaming platform.  
🎯 I want to scale Kafka consumers in EKS based on Kafka topic lag using KEDA + Strimzi.  
💻 Stack: Kafka, KEDA, Strimzi, EKS, Node.js  
📁 Structure:
kafka-keda-autoscale/
├── strimzi-kafka.yaml  
├── scaledobject.yaml  
├── consumer-deployment.yaml  

🔣 Input: Topic with 100+ unprocessed messages  
📤 Output: KEDA scales up consumer pods  

🌍 Environment: AWS EKS + Kafka installed  
📜 Constraints: Topic must be active  
🧾 Output: Lag reduces as pods increase  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Scalable streaming pipeline  
💡 I want Strimzi + KEDA example  
🚀 Deploy: Helm + kubectl  
🔐 Best Practices: Use commit-lag metric  
📥 Logs: KEDA + Kafka consumer logs  
🌐 Language: English
```

---

### ✅ Prompt 8: **Ingress Authentication with OAuth2 Proxy**
**🧠 Level:** Super Advanced  
```
🔧 I want to protect internal dashboards.  
🎯 I want to configure Ingress + OAuth2 proxy with Google auth for secured access.  
💻 Stack: Ingress, OAuth2 Proxy, Google OAuth, EKS  
📁 Structure:
oauth2-ingress/
├── ingress.yaml  
├── oauth2-proxy.yaml  
├── secret.yaml  

🔣 Input: Email login via OAuth  
📤 Output: Protected path redirects to Google login  

🌍 Environment: AWS EKS with external domain  
📜 Constraints: Valid OAuth credentials  
🧾 Output: Access via `/dashboard` after login  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Admin dashboard security  
💡 I want full working ingress + proxy setup  
🚀 Deploy: Helm  
🔐 Best Practices: Allowlist domain emails only  
📥 Logs: OAuth2 proxy logs  
🌐 Language: English
```

---

### ✅ Prompt 9: **Multi-Tenant Ingress with TLS Wildcard Certificate**
**🧠 Level:** Super Advanced  
```
🔧 I’m supporting multiple tenants.  
🎯 I want to expose tenant-specific subdomains using a wildcard TLS cert and NGINX Ingress.  
💻 Stack: cert-manager, NGINX Ingress, DNS, EKS  
📁 Structure:
multi-tenant-ingress/
├── wildcard-certificate.yaml  
├── ingress.yaml  

🔣 Input: `tenant1.domain.com`, `tenant2.domain.com`  
📤 Output: Ingress routes each subdomain via same TLS cert  

🌍 Environment: AWS EKS + Route53  
📜 Constraints: Wildcard DNS and cert  
🧾 Output: Each tenant gets separate route + TLS  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Multi-tenant SaaS  
💡 I want wildcard cert with shared ingress config  
🚀 Deploy: cert-manager + kubectl  
🔐 Best Practices: Use label-based tenant routing  
📥 Logs: NGINX ingress logs  
🌐 Language: English
```

---

### ✅ Prompt 10: **Rate-Limiting and IP Whitelisting via Ingress Annotations**
**🧠 Level:** Super Advanced  
```
🔧 I want to limit traffic and block abuse.  
🎯 I want to use NGINX ingress annotations for rate-limiting and allow-only specific IP ranges.  
💻 Stack: NGINX Ingress, Annotations, Kubernetes  
📁 Structure:
secure-ingress/
├── ingress.yaml  

🔣 Input: Request limits per IP + allowed CIDRs  
📤 Output: Access denied for non-whitelisted IPs  

🌍 Environment: EKS or Minikube  
📜 Constraints: Use NGINX ingress annotation keys  
🧾 Output: HTTP 429 or 403 for blocked users  
🔧 Experience Level: Super Advanced  
🏢 Use Case: Protect public endpoints  
💡 I want annotation-based limit config  
🚀 Deploy: kubectl  
🔐 Best Practices: Use `nginx.ingress.kubernetes.io` annotations  
📥 Logs: Ingress controller logs per access  
🌐 Language: English
```

---

Would you like:
- A **file name + title** for Week 6?
- Markdown export or GitHub-ready setup?
- YAML/Helm files generated for any of these?

Let me know how you'd like to continue!
