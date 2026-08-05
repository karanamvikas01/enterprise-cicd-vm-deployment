# 🚀 Enterprise CI/CD Pipeline on AWS using Jenkins, SonarQube, Nexus & Apache Tomcat

![Architecture](architecture/enterprise-cicd-architecture.png)

## 📖 Project Overview

This project demonstrates an end-to-end Enterprise Continuous Integration and Continuous Deployment (CI/CD) pipeline hosted on AWS EC2 instances.

Every code change pushed to GitHub automatically triggers a Jenkins Continuous Integration pipeline. The application is built using Maven, analyzed using SonarQube, validated through a Quality Gate, published to Nexus Repository Manager, and finally deployed automatically to an Apache Tomcat server through a dedicated Continuous Deployment pipeline.

The objective of this project is to simulate a real-world DevOps workflow by integrating industry-standard tools while following Infrastructure-as-Code and Continuous Delivery best practices.

---

# 🎯 Project Objectives

- Automate application build process
- Perform static code analysis
- Enforce Quality Gates
- Store build artifacts in Nexus Repository
- Automate deployments to Apache Tomcat
- Implement GitHub Webhooks
- Demonstrate Enterprise CI/CD workflow
- Deploy infrastructure on AWS EC2

---

# 🏗 Architecture

The following architecture illustrates the complete CI/CD workflow implemented in this project.

![Architecture](architecture/enterprise-cicd-architecture.png)

---

# 🛠 Technology Stack

| Tool | Purpose |
|------|----------|
| Git & GitHub | Source Code Management |
| Jenkins | Continuous Integration & Deployment |
| Maven | Build Automation |
| SonarQube | Static Code Analysis |
| Nexus Repository | Artifact Management |
| Apache Tomcat | Application Deployment |
| AWS EC2 | Infrastructure Hosting |
| Java | Application Runtime |

---

# 📂 Repository Structure

```text
enterprise-cicd-vm-deployment/
│
├── architecture/
├── deployment/
├── docs/
├── pipeline/
├── screenshots/
├── src/
├── pom.xml
├── README.md
└── LICENSE
```


| Folder | Description |
|----------|-------------|
| architecture | Project Architecture Diagram |
| deployment | Jenkins Continuous Deployment Pipeline |
| docs | Installation Guide, Troubleshooting & Notes |
| pipeline | Jenkins Continuous Integration Pipeline |
| screenshots | Pipeline Execution Screenshots |
| src | Application Source Code |
| pom.xml | Maven Project Configuration |

---

---

# 🔄 Continuous Integration Workflow

The Continuous Integration (CI) pipeline is responsible for automatically building, validating, and packaging the application whenever code is pushed to the GitHub repository.

### CI Pipeline Stages

1. Checkout Source Code
2. Maven Build
3. Unit Testing
4. Checkstyle Analysis
5. SonarQube Static Code Analysis
6. Quality Gate Validation
7. Upload Artifact to Nexus Repository
8. Trigger Continuous Deployment Pipeline

---

## CI Pipeline Execution

The following screenshot shows the successful execution of the complete Continuous Integration pipeline.

![CI Pipeline](screenshots/02-ci-pipeline-success.png)

---

# 🔍 Static Code Analysis

SonarQube is integrated into the pipeline to continuously monitor code quality.

The analysis includes:

- Bug Detection
- Security Vulnerabilities
- Code Smells
- Maintainability Analysis
- Quality Gate Validation

Only builds that successfully pass the Quality Gate proceed to the deployment stage.

![SonarQube](screenshots/03-sonarqube-analysis.png)

---

# 📦 Artifact Management

After a successful build, Jenkins uploads the generated WAR artifact to Nexus Repository Manager.

This allows the deployment pipeline to retrieve a versioned artifact instead of rebuilding the application.

Artifact Details:

- Packaging : WAR
- Repository : Maven Releases
- Versioning : Managed by Maven

![Nexus Repository](screenshots/04-nexus-artifact.png)

---

# 🚀 Continuous Deployment Workflow

The Continuous Deployment (CD) pipeline is automatically triggered after the CI pipeline completes successfully.

Deployment Steps:

1. Checkout Deployment Repository
2. Download WAR Artifact from Nexus
3. Deploy Artifact to Apache Tomcat
4. Verify Successful Deployment

---

## CD Pipeline Execution

The screenshot below demonstrates the successful execution of the deployment pipeline.

![CD Pipeline](screenshots/05-cd-pipeline-success.png)

---

# 🌐 Application Deployment

After deployment, the application becomes accessible through the Apache Tomcat server.

Deployment Target:

- Apache Tomcat 10
- Context Path: `/vprofile`

The screenshot below confirms the successful deployment.

![Tomcat Deployment](screenshots/06-tomcat-deployment.png)

---

# ☁ AWS Infrastructure

The complete solution is hosted on AWS using four dedicated EC2 instances.

Infrastructure Components:

- Jenkins Server
- SonarQube Server
- Nexus Repository Manager
- Apache Tomcat Server

Each service is deployed on an independent EC2 instance to simulate an enterprise-grade DevOps environment.

![AWS Infrastructure](screenshots/07-aws-infrastructure.png)

---

# 📊 End-to-End Pipeline Flow

The following diagram illustrates the complete end-to-end workflow from source code commit to production deployment.

![Enterprise CI/CD Architecture](architecture/enterprise-cicd-architecture.png)

---

# 📸 Jenkins Dashboard

The Jenkins dashboard contains two independent pipelines.

- Continuous Integration Pipeline
- Continuous Deployment Pipeline

Both pipelines are fully automated using GitHub Webhooks.

![Jenkins Dashboard](screenshots/01-jenkins-dashboard.png)

---

# 📁 Project Highlights

✅ End-to-End CI/CD Pipeline

✅ GitHub Webhook Integration

✅ Jenkins Pipeline as Code

✅ SonarQube Static Code Analysis

✅ Maven Build Automation

✅ Nexus Artifact Repository

✅ Apache Tomcat Deployment

✅ AWS EC2 Infrastructure

✅ Automated Continuous Deployment

---

# 🔧 Troubleshooting

Some challenges encountered during implementation:

- GitHub Webhook configuration
- Jenkins SCM configuration
- SonarQube Quality Gate failures
- Nexus Repository authentication
- Tomcat Manager deployment
- Missing Maven settings.xml
- Pipeline syntax validation
- Git branch configuration
- Repository migration
- Jenkins Credentials configuration

Each issue was resolved and documented throughout the implementation.

---

# 💡 Lessons Learned

This project provided practical experience with:

- Building enterprise Jenkins pipelines
- GitHub Webhooks
- Maven project lifecycle
- SonarQube Quality Gates
- Artifact version management
- Jenkins credentials management
- Apache Tomcat deployment automation
- Repository restructuring
- Pipeline troubleshooting
- CI/CD best practices

---

# 🚀 Next Phase – Strategy 2

The next implementation of this project will replace the virtual machine deployment with a container-based deployment strategy.

Upcoming technologies include:

- Docker
- Amazon ECR
- Amazon ECS / Kubernetes
- Helm
- GitOps
- ArgoCD
- Rolling Updates
- Blue-Green Deployment
- Monitoring & Logging
---


# 👨‍💻 Author

**Vikas Karanam**

DevOps | AWS | Jenkins | Docker | Kubernetes | Terraform | Linux

GitHub:
https://github.com/karanamvikas01

---

# ⭐ Support

If you found this project useful, consider giving the repository a ⭐ on GitHub.

It helps others discover the project and motivates future improvements.

---