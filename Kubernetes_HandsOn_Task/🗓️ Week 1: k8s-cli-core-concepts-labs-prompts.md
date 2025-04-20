## 🚀 Kubernetes CLI & Core Concepts – 10 Hands-On Labs (Beginner to Super Advanced)


---

### ✅ Prompt 1: Hello Pod - Create & Inspect  
```
🔧 I am a beginner DevOps engineer.  
🎯 I want to create my first Pod in Kubernetes and inspect it using basic kubectl commands.  
💻 Tech Stack: Kubernetes, Minikube, BusyBox container  
📁 Folder:
hello-pod/
├── pod.yaml  

🔣 Input: Pod manifest running `sleep 3600`  
📤 Output: Verify pod with `kubectl get`, `describe`, `logs`, `exec`  

🌍 Environment: Minikube on macOS  
📜 Constraints: Must use lightweight image and minimal resources  
🧾 Output format: YAML + CLI steps + expected output  
🔧 Experience level: Beginner  
🏢 Use case: Learn pod lifecycle, debug with exec  
💡 I want code generation and best practices for inspecting pods  
🚀 Deployment: Local via `kubectl apply`  
🔐 Best practices: Avoid using latest tag in image  
📥 Logs: Show output of `kubectl describe pod` and `kubectl logs`  
🌐 Language: English
```

---

### ✅ Prompt 2: Deploy & Scale Nginx with ReplicaSet  
```
🔧 I am a DevOps engineer learning Kubernetes workloads.  
🎯 I want to deploy an Nginx app using a ReplicaSet and scale it manually.  
💻 Tech Stack: Kubernetes, Docker, Nginx  
📁 Folder:
nginx-replicaset/
├── replicaset.yaml  

🔣 Input: Nginx container with replicas=3  
📤 Output: 3 pods should be running and visible via `kubectl get pods`  

🌍 Environment: Minikube  
📜 Constraints: Stateless, expose only internally  
🧾 Output format: YAML + CLI scale command  
🔧 Experience level: Beginner  
🏢 Use case: High availability web app  
💡 I want YAML with inline comments  
🚀 Deployment: Minikube CLI  
🔐 Best practices: Use `readinessProbe` for production  
📥 Logs: If scaling fails, show describe output  
🌐 Language: English
```

---

### ✅ Prompt 3: Create Deployment and Rollback  
```
🔧 I am a DevOps engineer practicing Deployment lifecycle operations.  
🎯 I want to create a Deployment, perform an update, and roll it back.  
💻 Tech Stack: Kubernetes, Nginx  
📁 Folder:
deployment-rollback/
├── deployment-v1.yaml  
├── deployment-v2.yaml  

🔣 Input: Two versions of Nginx (1.14 & 1.19)  
📤 Output: Deploy v1 → upgrade to v2 → rollback to v1  

🌍 Environment: Minikube  
📜 Constraints: Must use `kubectl rollout` for upgrade/rollback  
🧾 Output format: YAML + CLI commands  
🔧 Experience level: Intermediate  
🏢 Use case: CI/CD rollout simulation  
💡 I want full CLI walkthrough and rollback logs  
🚀 Deployment: Minikube with kubectl  
🔐 Best practices: Use image versioning strictly  
📥 Logs: Provide `kubectl rollout history` and undo result  
🌐 Language: English
```

---

### ✅ Prompt 4: Expose Deployment with NodePort  
```
🔧 I am a DevOps engineer learning Kubernetes service exposure.  
🎯 I want to expose an Nginx Deployment via NodePort and access it via browser.  
💻 Tech Stack: Kubernetes, Minikube, Nginx  
📁 Folder:
expose-nginx/
├── deployment.yaml  
├── service-nodeport.yaml  

🔣 Input: Deployment + NodePort Service  
📤 Output: Access app via `minikube service` or `curl`  

🌍 Environment: Minikube  
📜 Constraints: Use fixed port (e.g., 30036)  
🧾 Output format: YAML + browser URL  
🔧 Experience level: Beginner  
🏢 Use case: Test internal app locally  
💡 I want a curl-ready example  
🚀 Deployment: NodePort  
🔐 Best practices: Use `targetPort` & `port` correctly  
📥 Logs: Help if port forwarding fails  
🌐 Language: English
```

---

### ✅ Prompt 5: Labels and Selectors – Filter Pods  
```
🔧 I am a DevOps engineer learning label-based filtering in Kubernetes.  
🎯 I want to label different pods and use `kubectl` selectors to filter them.  
💻 Tech Stack: Kubernetes CLI  
📁 Folder:
label-selectors/
├── red-pod.yaml  
├── blue-pod.yaml  

🔣 Input: Pods with labels like `env=prod`, `color=red`  
📤 Output: Filter pods using `kubectl get pods -l color=red`  

🌍 Environment: Minikube  
📜 Constraints: Show multi-label queries too  
🧾 Output format: YAML + CLI output  
🔧 Experience level: Intermediate  
🏢 Use case: Manage large workloads using metadata  
💡 I want CLI examples and best labeling patterns  
🚀 Deployment: CLI-driven  
🔐 Best practices: Use consistent label keys  
📥 Logs: Output of `kubectl get pods --show-labels`  
🌐 Language: English
```

---

### ✅ Prompt 6: Multi-Namespace Management  
```
🔧 I am a DevOps engineer practicing namespace isolation.  
🎯 I want to create multiple namespaces and deploy identical apps in each, then inspect them.  
💻 Tech Stack: Kubernetes  
📁 Folder:
namespace-demo/
├── dev-namespace.yaml  
├── prod-namespace.yaml  
├── app-deployment.yaml  

🔣 Input: Deploy `nginx` in `dev` and `prod`  
📤 Output: Namespaced resources visible separately  

🌍 Environment: Minikube  
📜 Constraints: Must use `kubectl --namespace`  
🧾 Output format: YAML + CLI  
🔧 Experience level: Intermediate  
🏢 Use case: Multi-tenant cluster simulation  
💡 I want code + CLI for switching namespaces  
🚀 Deployment: Minikube  
🔐 Best practices: Default quotas for each namespace  
📥 Logs: `kubectl get all -n <ns>` output  
🌐 Language: English
```

---

### ✅ Prompt 7: LoadBalancer Service (Simulated)  
```
🔧 I’m a DevOps engineer testing external access via LoadBalancer Service.  
🎯 I want to define a LoadBalancer Service and simulate it via Minikube tunnel.  
💻 Tech Stack: Kubernetes, Minikube, Nginx  
📁 Folder:
loadbalancer-demo/
├── deployment.yaml  
├── service-loadbalancer.yaml  

🔣 Input: Service type = LoadBalancer  
📤 Output: Access app using `minikube tunnel` and public IP  

🌍 Environment: Minikube (with tunnel)  
📜 Constraints: Simulated LoadBalancer only  
🧾 Output format: YAML + curl result  
🔧 Experience level: Intermediate  
🏢 Use case: Preview production exposure  
💡 I want CLI steps + YAML  
🚀 Deployment: Minikube  
🔐 Best practices: Use secure ports in prod  
📥 Logs: Help troubleshoot if tunnel fails  
🌐 Language: English
```

---

### ✅ Prompt 8: Debugging with exec, logs, describe  
```
🔧 I am a DevOps engineer practicing Kubernetes debugging.  
🎯 I want to deploy a broken container and use kubectl logs, describe, and exec to debug it.  
💻 Tech Stack: Kubernetes, Bash, Alpine image  
📁 Folder:
debug-pod/
├── broken-pod.yaml  

🔣 Input: Pod with missing command or crash loop  
📤 Output: Use CLI to find root cause  

🌍 Environment: Minikube  
📜 Constraints: Must use `kubectl exec`, `describe`, `logs`  
🧾 Output format: Terminal output  
🔧 Experience level: Intermediate  
🏢 Use case: Debugging startup issues  
💡 I want CLI-based walkthrough  
🚀 Deployment: Minikube  
🔐 Best practices: Use sidecars for debugging in prod  
📥 Logs: Show logs and status conditions  
🌐 Language: English
```

---

### ✅ Prompt 9: Zero-Downtime Rolling Update  
```
🔧 I am a DevOps engineer ensuring availability during updates.  
🎯 I want to perform a rolling update of a live Deployment with 0 downtime.  
💻 Tech Stack: Kubernetes, Nginx  
📁 Folder:
rolling-update/
├── deployment.yaml  

🔣 Input: Image v1 → v2 upgrade  
📤 Output: All pods updated one-by-one, no downtime  

🌍 Environment: Minikube  
📜 Constraints: Must verify with `kubectl rollout status`  
🧾 Output format: YAML + command steps  
🔧 Experience level: Advanced  
🏢 Use case: CI/CD blue-green alternative  
💡 I want deployment spec with update strategy  
🚀 Deployment: Minikube  
🔐 Best practices: Use `maxUnavailable`, `maxSurge` wisely  
📥 Logs: Include `rollout status` output  
🌐 Language: English
```

---

### ✅ Prompt 10: Super Advanced – Canary Deployment with Labels  
```
🔧 I’m a senior DevOps engineer simulating canary releases in Kubernetes.  
🎯 I want to deploy v1 of an app to 90% of users and v2 to 10%, using labels and weighted services.  
💻 Tech Stack: Kubernetes, Nginx, Custom Service Routing (e.g., Istio optional)  
📁 Folder:
canary-deploy/
├── deployment-v1.yaml  
├── deployment-v2.yaml  
├── service.yaml  

🔣 Input: Label-based pod selectors  
📤 Output: Weighted traffic split using custom selectors  

🌍 Environment: Minikube with optional Istio  
📜 Constraints: No service mesh allowed unless needed  
🧾 Output format: YAML + curl results  
🔧 Experience level: Super Advanced  
🏢 Use case: Canary rollout for web apps  
💡 I want config with or without service mesh  
🚀 Deployment: K8s native or Istio  
🔐 Best practices: Use metrics to monitor traffic shift  
📥 Logs: Show curl distribution of v1/v2 responses  
🌐 Language: English
```

---

