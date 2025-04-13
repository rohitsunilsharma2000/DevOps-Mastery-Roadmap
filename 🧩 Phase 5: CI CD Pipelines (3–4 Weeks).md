Here’s your **detailed roadmap for Phase 5: CI/CD Pipelines (3–4 weeks)** — designed to help you master continuous integration and delivery using **GitHub Actions, Jenkins, and AWS CodePipeline** with real-world infrastructure deployment.

---

# 🧩 **Phase 5: CI/CD Pipelines (3–4 Weeks)**

### 🎯 **Goal**: Automate the process of building, testing, and deploying containerized apps to EKS using CI/CD pipelines with GitHub Actions, Jenkins, and AWS-native tools.

---

## 🗓️ **Week 1: CI/CD Fundamentals & GitHub Actions**

### 🔹 Topics:
- What is CI/CD? CI vs CD vs CD (Continuous Delivery vs Continuous Deployment)
- GitHub Actions concepts: workflows, jobs, steps, runners
- Secrets & environment variables

### 🛠️ Hands-On:
- Build a workflow:
  ```yaml
  name: Build and Test Node App

  on:
    push:
      branches: [ main ]

  jobs:
    build:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v3
        - name: Install dependencies
          run: npm install
        - name: Run tests
          run: npm test
  ```

- Trigger a job on push/pull request
- Set secrets in GitHub and use `secrets.MY_SECRET`

### 📚 Resources:
- [GitHub Actions Docs](https://docs.github.com/en/actions)
- [Actions Marketplace](https://github.com/marketplace?type=actions)

---

## 🗓️ **Week 2: Jenkins Pipelines for Docker & Kubernetes**

### 🔹 Topics:
- Jenkins installation & setup
- Declarative pipelines using `Jenkinsfile`
- Integrating Docker build & push
- Kubernetes deploy via `kubectl`

### 🛠️ Hands-On:
- Install Jenkins via Docker:
  ```bash
  docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts
  ```

- Sample Jenkinsfile:
  ```groovy
  pipeline {
    agent any
    stages {
      stage('Build') {
        steps {
          sh 'npm install'
        }
      }
      stage('Test') {
        steps {
          sh 'npm test'
        }
      }
      stage('Docker Build & Push') {
        steps {
          sh 'docker build -t myapp .'
          sh 'docker push my-dockerhub/myapp'
        }
      }
      stage('Deploy to K8s') {
        steps {
          sh 'kubectl apply -f k8s/deployment.yaml'
        }
      }
    }
  }
  ```

- Use Docker agent or install `docker`, `kubectl` inside Jenkins

### 📚 Resources:
- [Jenkins Docs](https://www.jenkins.io/doc/)
- [Jenkins Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)

---

## 🗓️ **Week 3: AWS CodePipeline + CodeBuild**

### 🔹 Topics:
- AWS-native CI/CD overview
- CodeCommit (Git), CodeBuild (build), CodePipeline (workflow)
- Using CodePipeline to deploy app to EKS or ECS

### 🛠️ Hands-On:
- Create:
  - CodeCommit repo
  - CodeBuild project (Docker + Helm)
  - CodePipeline stages: Source → Build → Deploy
- Use `buildspec.yml`:
  ```yaml
  version: 0.2
  phases:
    install:
      runtime-versions:
        docker: 18
    build:
      commands:
        - echo Build started
        - docker build -t my-app .
  ```

### 📚 Resources:
- [AWS CodePipeline Tutorial](https://docs.aws.amazon.com/codepipeline/latest/userguide/welcome.html)
- [AWS BuildSpec Reference](https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html)

---

## 🗓️ **Week 4: Real-World CI/CD Projects**

### 📦 Projects:
1. **GitHub Actions**:
   - Push app to DockerHub or ECR
   - Deploy to EKS using Helm
   - Slack notification on success/failure

2. **Jenkins**:
   - Multi-branch pipeline
   - Parameterized builds
   - Secrets via credentials plugin

3. **CodePipeline**:
   - End-to-end pipeline with auto-deploy
   - Email/Slack notifications

### 🔍 Monitoring:
- Logs from GitHub Actions console
- Jenkins build history, Blue Ocean
- CodePipeline visual flow + CloudWatch logs

---

## ✅ Deliverables for Portfolio:
- GitHub repo with `Jenkinsfile`, `buildspec.yml`, and `deployment.yaml`
- Screenshot of successful CI/CD runs
- Live demo link or video of auto-deploy to EKS

---

Would you like a starter GitHub project template for GitHub Actions + Jenkins + Terraform + Helm for EKS?
