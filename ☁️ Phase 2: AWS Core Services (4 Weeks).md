
---

# ☁️ **Phase 2: AWS Core Services (4 Weeks)**

### 🎯 **Goal**: Learn how to provision, secure, monitor, and scale infrastructure using core AWS services — manually and via CLI, preparing you for IaC with Terraform.

---

## 🗓️ **Week 1: IAM, EC2, and CLI Basics**

### 🔹 Topics:
- IAM: Users, Roles, Policies, Groups
- EC2: Instances, AMIs, key pairs, volumes
- AWS CLI & SDK (basic usage)

### 🛠️ Hands-On:
- Create IAM user with programmatic access
- Generate access keys and configure:
  ```bash
  aws configure
  ```
- Launch EC2 instance (Amazon Linux 2)
- SSH into instance using `.pem` file
- Attach IAM role to instance and test `aws s3 ls`

### 📚 Resources:
- [IAM Tutorial](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [AWS CLI Docs](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

---

## 🗓️ **Week 2: VPC, Subnets, Security Groups, and NAT**

### 🔹 Topics:
- VPC architecture (CIDR blocks)
- Public & private subnets
- Internet Gateway, NAT Gateway
- Route Tables, Security Groups, NACLs

### 🛠️ Hands-On:
- Create a custom VPC:
  - 1 public + 1 private subnet
  - IGW + NAT Gateway
- Configure routing between subnets
- Launch EC2 instances in both and test connectivity
- Use Security Groups and NACLs for access control

### 📚 Resources:
- [VPC Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [VPC Wizard Walkthrough](https://aws.amazon.com/vpc/)

---

## 🗓️ **Week 3: Monitoring with CloudWatch & S3 Storage**

### 🔹 Topics:
- CloudWatch Logs, Metrics, Dashboards, Alarms
- Custom metrics
- Using S3 as a static site host or backup location

### 🛠️ Hands-On:
- Enable detailed monitoring for EC2
- View CPU metrics, set alarm (e.g., >80% CPU usage)
- Send CloudWatch alarm notifications to **SNS**
- Store app logs in CloudWatch Logs
- Upload files to S3, enable static website hosting

### 📚 Resources:
- [CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)
- [S3 Docs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

---

## 🗓️ **Week 4: Load Balancers, Autoscaling, and Pricing**

### 🔹 Topics:
- Application Load Balancer (ALB)
- Target groups, health checks
- Auto Scaling Groups (ASGs)
- Cost optimization & billing basics

### 🛠️ Hands-On:
- Create an ALB and register EC2 targets
- Set up Auto Scaling Group:
  - Launch template → Min/Max/Desired capacity
  - Attach to ALB
  - Trigger scale-in/out based on CPU
- Explore **AWS Cost Calculator**

### 📚 Resources:
- [ALB Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
- [ASG Docs](https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html)
- [AWS Pricing Calculator](https://calculator.aws.amazon.com)

---

## ✅ Deliverables for Portfolio:
- VPC Architecture Diagram
- Terraform or CLI templates for EC2, VPC, and ALB
- Screenshots of CloudWatch alarms & dashboards
- GitHub repo with config files and setup guides

---

