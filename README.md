# Enterprise CI Pipeline on AWS using Jenkins, SonarQube & Nexus

> **An enterprise-inspired Continuous Integration (CI) pipeline built on AWS that automates code compilation, testing, static code analysis, quality validation, and artifact management using Jenkins, Maven, SonarQube, and Nexus Repository Manager.**

---

## Project Overview

Continuous Integration (CI) is a core DevOps practice that enables development teams to automatically validate code changes through builds, testing, and quality checks before they are deployed.

This project demonstrates the implementation of a production-inspired CI pipeline hosted on AWS. The pipeline integrates multiple industry-standard tools to automate the software build lifecycle while improving code quality, consistency, and delivery reliability.

Instead of performing manual compilation and validation, every code change follows a structured workflow where Jenkins retrieves the latest source code, builds the application using Maven, performs unit testing, executes static code analysis using SonarQube, validates Quality Gates, and finally publishes the generated artifact to Nexus Repository Manager.

The objective of this project was not only to implement a working CI pipeline but also to understand how enterprise organizations automate software delivery using DevOps practices.

---

# Project Objectives

This project was designed with the following objectives:

- Build an enterprise-style Continuous Integration pipeline
- Automate Java application builds using Jenkins
- Perform automated unit testing
- Enforce coding standards through Checkstyle
- Integrate SonarQube for static code analysis
- Validate builds using SonarQube Quality Gates
- Store build artifacts in Nexus Repository Manager
- Gain hands-on experience with enterprise CI tools on AWS
- Develop troubleshooting skills by resolving real-world pipeline issues

---

# Architecture Overview

The CI pipeline consists of four major components working together.

```
                GitHub Repository
                       │
                       ▼
                 Jenkins Pipeline
                       │
      ┌────────────────┼────────────────┐
      │                │                │
      ▼                ▼                ▼
   Maven Build    Unit Testing     Checkstyle
                       │
                       ▼
                SonarQube Analysis
                       │
                       ▼
                 Quality Gate
                       │
                       ▼
          Nexus Repository Manager
```

---

# AWS Infrastructure

The project is deployed on Amazon Web Services using separate EC2 instances for each major component.

| AWS Resource | Purpose |
|--------------|---------|
| EC2 Instance | Jenkins Server |
| EC2 Instance | SonarQube Server |
| EC2 Instance | Nexus Repository Manager |
| GitHub | Source Code Management |

Using separate servers closely resembles a production environment where services are isolated for improved scalability and maintainability.

---

# Technology Stack

| Category | Technology |
|-----------|------------|
| Cloud Platform | AWS |
| Operating System | Ubuntu Linux |
| Version Control | Git |
| Repository | GitHub |
| CI Tool | Jenkins |
| Programming Language | Java |
| Build Tool | Apache Maven |
| Static Code Analysis | SonarQube Community Edition |
| Artifact Repository | Nexus Repository Manager |
| Build Artifact | WAR |
| CI Pipeline | Jenkins Declarative Pipeline |

---

# Key Features

- Automated Continuous Integration Pipeline
- GitHub Source Code Integration
- Maven Build Automation
- Unit Test Execution
- Checkstyle Code Validation
- SonarQube Static Code Analysis
- SonarQube Quality Gate Enforcement
- Nexus Artifact Repository Integration
- Automated WAR Artifact Publishing
- AWS Hosted Infrastructure
- Enterprise Project Documentation

---

# Enterprise CI Workflow

The pipeline executes the following workflow automatically whenever a build is triggered.

```
Developer

      │

      ▼

GitHub Repository

      │

      ▼

Jenkins

      │

      ▼

Checkout Source Code

      │

      ▼

Compile Application

      │

      ▼

Execute Unit Tests

      │

      ▼

Checkstyle Analysis

      │

      ▼

SonarQube Analysis

      │

      ▼

Quality Gate Validation

      │

      ▼

Generate WAR Artifact

      │

      ▼

Upload Artifact to Nexus Repository
```

---

# Repository Structure

```
enterprise-ci-pipeline-aws
│
├── application/
│   └── pom.xml
│
├── architecture/
│   ├── enterprise-ci-architecture.png
│   ├── aws-infrastructure.png
│   └── jenkins-pipeline-flow.png
│
├── docs/
│   ├── installation.md
│   ├── project-architecture.md
│   ├── troubleshooting.md
│   └── interview-notes.md
│
├── pipeline/
│   ├── Jenkinsfile
│   └── settings.xml
│
├── screenshots/
│   ├── 01-github/
│   ├── 02-jenkins/
│   ├── 03-sonarqube/
│   ├── 04-nexus/
│   ├── 05-pipeline/
│   ├── 06-aws/
│   └── 07-troubleshooting/
│
├── README.md
├── LICENSE
└── .gitignore
```



# CI Pipeline Stages

The Jenkins Declarative Pipeline consists of seven automated stages.

| Stage | Purpose |
|--------|---------|
| Checkout SCM | Retrieves the latest application source code from GitHub |
| Build | Compiles and packages the application using Maven |
| Unit Test | Executes automated test cases |
| Checkstyle Analysis | Validates Java coding standards |
| SonarQube Analysis | Performs static code analysis |
| Quality Gate | Validates project quality before artifact publication |
| Upload Artifact | Publishes the generated WAR file to Nexus Repository |

---

# Architecture Diagrams

The repository includes architecture diagrams that illustrate the implementation.

Available diagrams:

- Enterprise CI Architecture
- AWS Infrastructure
- Jenkins Pipeline Flow

These diagrams are available in the **architecture/** directory.

# Jenkins Configuration

Jenkins serves as the orchestration engine for the Continuous Integration pipeline. A Declarative Pipeline was implemented to automate the complete software build lifecycle.

### Jenkins Responsibilities

- Pull source code from GitHub
- Execute Maven build lifecycle
- Run automated unit tests
- Perform Checkstyle analysis
- Trigger SonarQube static code analysis
- Wait for Quality Gate validation
- Upload the generated WAR artifact to Nexus Repository Manager

The pipeline configuration is available under:

```
pipeline/
└── Jenkinsfile
```

---

# SonarQube Integration

SonarQube was integrated into Jenkins to perform automated static code analysis.

The SonarQube Scanner analyzes the source code and generates detailed quality reports before allowing the pipeline to continue.

### Metrics Evaluated

- Bugs
- Vulnerabilities
- Code Smells
- Maintainability
- Reliability
- Security
- Duplicated Code
- Technical Debt

A Quality Gate was configured to ensure only code meeting predefined quality standards proceeds to the artifact publishing stage.

---

# Nexus Repository Integration

Sonatype Nexus Repository Manager was used as the centralized artifact repository.

After successful completion of all pipeline stages, Jenkins automatically uploads the generated WAR package to the Maven Releases repository.

### Benefits

- Centralized artifact storage
- Version control for build artifacts
- Easy retrieval for deployment
- Enterprise artifact management

Repository used:

```
maven-releases
```

---

# Project Screenshots

The repository contains screenshots captured throughout the implementation.

## GitHub

Location:

```
screenshots/01-github/
```

Includes:

- Repository Home
- Branch Management
- Jenkinsfile in GitHub

---

## Jenkins

Location:

```
screenshots/02-jenkins/
```

Includes:

- Jenkins Dashboard
- Pipeline Job
- Successful Pipeline Execution
- Console Output

---

## SonarQube

Location:

```
screenshots/03-sonarqube/
```

Includes:

- Dashboard
- Project Overview
- Code Analysis
- Quality Gate

---

## Nexus Repository

Location:

```
screenshots/04-nexus/
```

Includes:

- Repository Home
- Repository List
- Maven Releases Repository
- Uploaded WAR Artifact

---

## Pipeline

Location:

```
screenshots/05-pipeline/
```

Includes:

- Pipeline Stage View
- Successful Build Execution

---

## AWS

Location:

```
screenshots/06-aws/
```

Includes:

- EC2 Instances
- Running Infrastructure

---

# Challenges Faced

The implementation involved several real-world troubleshooting scenarios.

## Technical Challenges

- Java runtime and compiler version mismatch
- Maven installation and configuration
- Jenkins Pipeline syntax validation
- Missing Jenkins plugins
- SonarQube Webhook configuration
- Nexus authentication
- Jenkins Out Of Memory (OOM)
- EC2 resource limitations
- Artifact upload failures
- Pipeline debugging

Each issue was investigated, resolved, and documented to better understand enterprise CI troubleshooting practices.

---

# Lessons Learned

This project provided valuable practical experience in building and operating a Continuous Integration pipeline.

Key takeaways include:

- Importance of pipeline automation
- Benefits of static code analysis
- Artifact management using Nexus
- Quality Gates improve software quality
- Proper server sizing is critical for Jenkins stability
- Secure credential management is essential
- Troubleshooting is an integral part of DevOps engineering

---

# Skills Demonstrated

## Cloud

- AWS EC2
- Linux Administration
- Server Configuration

## DevOps

- Continuous Integration
- Jenkins Pipelines
- GitHub Integration
- Build Automation

## Build Tools

- Apache Maven
- Java Build Lifecycle

## Code Quality

- SonarQube
- Checkstyle
- Quality Gates

## Artifact Management

- Nexus Repository Manager
- Artifact Versioning

## Version Control

- Git
- GitHub

---

# Future Enhancements

The next phase of this project is to extend the CI pipeline into a complete Continuous Deployment (CD) solution.

Planned enhancements include:

- Automated deployment to EC2
- Docker containerization
- Kubernetes deployment using Amazon EKS
- Infrastructure as Code using Terraform
- Jenkins Shared Libraries
- Monitoring using Prometheus and Grafana
- Slack / Microsoft Teams notifications
- Deployment Rollback Strategy

---

# Acknowledgements

The sample Java application used in this project is based on the open-source **VProfile** application.

The primary objective of this repository is to demonstrate the design, implementation, troubleshooting, and documentation of an enterprise-style Continuous Integration pipeline using AWS and modern DevOps tools.

---

# About This Project

This repository represents a hands-on implementation of a production-inspired CI pipeline built for learning, portfolio development, and interview preparation.

During this project, practical experience was gained in:

- Designing CI workflows
- Configuring enterprise DevOps tools
- Integrating multiple platforms
- Troubleshooting build failures
- Managing build artifacts
- Working with Linux servers on AWS

Rather than focusing only on a successful pipeline, this project emphasizes understanding the engineering decisions and troubleshooting required to build reliable Continuous Integration systems.

---

# Author

## Karanam Vikas

Cloud Engineer | Site Reliability Engineering (SRE) Enthusiast

### Connect

- GitHub: https://github.com/karanamvikas01
- LinkedIn: www.linkedin.com/in/karanam-vikas

---

## If you found this repository useful...

⭐ Consider starring the repository.

Feedback and suggestions are always welcome.

---

# Conclusion

This project demonstrates the implementation of a complete enterprise-inspired Continuous Integration pipeline on AWS using Jenkins, Maven, SonarQube, Nexus Repository Manager, GitHub, and Java.

It showcases practical DevOps concepts including automated builds, code quality analysis, artifact management, pipeline automation, and troubleshooting.

The experience gained through this implementation provides a strong foundation for advancing toward enterprise Continuous Deployment (CD), containerization, Kubernetes, and Site Reliability Engineering (SRE) practices.

Final CI/CD Automation testing...