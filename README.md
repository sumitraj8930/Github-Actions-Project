
## 🚀 Project Overview

This project demonstrates a complete **DevSecOps CI/CD pipeline** using:

* **GitHub Actions** for CI/CD
* **Trivy** for filesystem vulnerability scanning
* **Gitleaks** for secret scanning
* **SonarQube** for code quality & static analysis
* **Docker** for container packaging
* **Docker Hub** for image registry
* **AWS EKS (Kubernetes)** for deployment

The pipeline automates the entire software delivery process from **code commit → security checks → build → quality gate → containerization → deployment**.

---

## 🛠️ **Tech Stack Used**

| Category      | Tools            |
| ------------- | ---------------- |
| CI/CD         | GitHub Actions   |
| Security      | Trivy, Gitleaks  |
| SAST          | SonarQube        |
| Container     | Docker           |
| Registry      | Docker Hub       |
| Cloud         | AWS              |
| Orchestration | Kubernetes (EKS) |
| Language      | Java (JDK 17)    |
| Build Tool    | Maven            |

---

## 🔄 **Pipeline Workflow (End-to-End)**

### **1. Code Compile**

* Checkout code
* Setup JDK 17
* Build using Maven

### **2. Security Checks (DevSecOps Stage)**

✔ **Trivy Scan** → Detect filesystem vulnerabilities
✔ **Gitleaks Scan** → Detect secrets in source code

### **3. Unit Testing**

* Maven test execution

### **4. Code Quality & SAST (SonarQube)**

* Build JAR
* SonarScan for code quality & bugs
* Sonar Quality Gate enforcement

### **5. Docker Image Build + Push**

* Authenticate with Docker Hub
* Build image using Buildx
* Push container image to Docker Hub registry

### **6. Deployment on Kubernetes**

* AWS CLI setup
* kubeconfig setup
* Deploy manifest to AWS EKS cluster

---

## 🌐 **Architecture Diagram (Explain in Simple Flow)**

```
Developer → GitHub → CI/CD Pipeline → Security Checks → SonarQube → Docker Build → Docker Hub → EKS Deployment
```

---

## 🧪 **Security Implemented**

✔ Vulnerability Scanning (Trivy)
✔ Secrets Detection (Gitleaks)
✔ Sonar Quality Gate (Bugs + Code Smell + Coverage)

---

## 📦 **Containerization**

Dockerfile is used to package application into a container:

```
docker build → docker tag → docker push
```

---

## ☁️ **Cloud Deployment**

Deployment takes place on AWS EKS using:

```
kubectl apply -f ds.yml
```

---

## 🔑 **Secrets & Variables Configuration**

This project uses GitHub:

### **Secrets**

* SONAR_TOKEN
* DOCKERHUB_TOKEN
* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* EKS_KUBECONFIG

### **Variables**

* SONAR_HOST_URL
* DOCKERHUB_USERNAME

---

## 📍 **Prerequisites**

✔ Docker Hub account
✔ SonarQube server
✔ AWS EKS cluster
✔ Kubernetes manifest
✔ GitHub Actions Runner (self-hosted)

---

## 📁 **Repository Includes**

| File                         | Purpose                      |
| ---------------------------- | ---------------------------- |
| `.github/workflows/cicd.yml` | Complete pipeline            |
| `Dockerfile`                 | Container build instructions |
| `ds.yml`                     | Kubernetes deployment file   |
| `pom.xml`                    | Maven config                 |
| `src/`                       | Application source code      |

