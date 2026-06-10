# Enterprise DevOps Platform

## Project Overview

Enterprise DevOps Platform is an end-to-end CI/CD implementation project demonstrating modern DevOps practices using Jenkins, SonarQube, Docker, Docker Hub, and Kubernetes.

The project automates the complete software delivery lifecycle from source code commit to deployment on a Kubernetes cluster.

---

## Architecture

Developer
↓
GitHub Repository
↓
Jenkins Pipeline
↓
SonarQube Code Analysis
↓
Docker Build
↓
Docker Hub Push
↓
Kubernetes Deployment
↓
Application Service Exposure

---

## Tech Stack

### CI/CD

* Jenkins
* GitHub

### Code Quality

* SonarQube

### Containerization

* Docker
* Docker Hub

### Container Orchestration

* Kubernetes

### Application

* Python Flask

### Infrastructure

* Linux VM
* Docker Runtime

---

## Project Structure

```bash
enterprise-devops-platform/
│
├── app/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── kubernetes/
│   ├── deployment.yaml
│   └── service.yaml
│
├── Jenkinsfile
│
└── README.md
```

---

## Jenkins Pipeline Stages

### Stage 1: Source Code Checkout

Jenkins pulls the latest code from GitHub.

```groovy
git 'https://github.com/Deeksha-chouhan/enterprise-devops-platform.git'
```

---

### Stage 2: SonarQube Analysis

Static code analysis is performed to identify:

* Bugs
* Vulnerabilities
* Code smells
* Security issues

Example:

```bash
sonar-scanner \
-Dsonar.projectKey=enterprise-devops-platform \
-Dsonar.sources=. \
-Dsonar.host.url=<SONAR_URL>
```

---

### Stage 3: Docker Image Build

Application container image is built.

```bash
docker build -t 9691427913/enterprise-devops-platform:latest ./app
```

---

### Stage 4: Docker Hub Push

Docker image is pushed to Docker Hub.

```bash
docker push 9691427913/enterprise-devops-platform:latest
```

---

### Stage 5: Kubernetes Deployment

Deploy application to Kubernetes.

```bash
kubectl apply -f kubernetes/deployment.yaml
```

---

### Stage 6: Service Exposure

Expose application service.

```bash
kubectl apply -f kubernetes/service.yaml
```

---

## Successful Pipeline Execution

The Jenkins pipeline completed successfully.

### SonarQube Analysis

* Analysis Status: SUCCESS
* Kubernetes YAML Scanned
* Dockerfile Scanned
* Python Source Code Scanned

### Docker Build

Image Built Successfully:

```bash
9691427913/enterprise-devops-platform:latest
```

### Docker Push

Image Published Successfully to Docker Hub.

### Kubernetes Deployment

Deployment Status:

```bash
deployment.apps/enterprise-devops-platform unchanged
```

Service Status:

```bash
service/enterprise-devops-service unchanged
```

---

## Key DevOps Features Implemented

* CI/CD Pipeline Automation
* Infrastructure as Code
* Static Code Analysis
* Containerization
* Image Registry Integration
* Kubernetes Deployment
* Automated Build Process
* Automated Release Process

---

## Challenges Faced

### VM Storage Limitation

While extending the project, additional tools such as:

* Trivy
* Prometheus
* Grafana

could not be fully configured due to insufficient storage available on the VM.

Despite this limitation, the complete CI/CD workflow was successfully implemented and validated.

---

## Learning Outcomes

Through this project I gained hands-on experience with:

* Jenkins Pipeline Development
* SonarQube Integration
* Docker Image Management
* Docker Hub Registry Usage
* Kubernetes Deployments
* Kubernetes Services
* CI/CD Best Practices
* DevOps Automation

---

## Future Enhancements

* Integrate Trivy Security Scanning
* Add Prometheus Monitoring
* Add Grafana Dashboards
* Implement Helm Charts
* Add ArgoCD GitOps Deployment
* Multi-Environment Deployment Strategy
* Automated Rollbacks

---

## Author

Deeksha Chouhan

DevOps Engineer

GitHub:
https://github.com/Deeksha-chouhan
LinkedIn:https://www.linkedin.com/in/deeksha-chouhan-devops/





LinkedIn:
(Add Your LinkedIn URL)
