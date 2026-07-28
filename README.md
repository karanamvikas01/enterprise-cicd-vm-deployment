---

# Project Repository Structure

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
├── docs/
│   ├── installation.md
│   ├── project-architecture.md
│   ├── troubleshooting.md
│   └── interview-notes.md
│
├── README.md
├── LICENSE
└── .gitignore
```

---

# CI Pipeline Stages

The Jenkins Declarative Pipeline automates the complete Continuous Integration workflow.

| Stage | Description |
|--------|-------------|
| Checkout SCM | Retrieves the latest source code from GitHub |
| Build | Compiles the application using Maven |
| Unit Test | Executes automated test cases |
| Checkstyle Analysis | Validates coding standards |
| SonarQube Analysis | Performs static code analysis |
| Quality Gate | Ensures the project meets quality requirements |
| Upload Artifact | Publishes the generated WAR file to Nexus Repository |

---

# Jenkins Integration

Jenkins acts as the central automation server responsible for orchestrating the CI pipeline.

Responsibilities include:

- Source code checkout from GitHub
- Maven build execution
- Unit testing
- Checkstyle analysis
- SonarQube integration
- Quality Gate validation
- Artifact publishing to Nexus Repository

---

# SonarQube Integration

SonarQube was integrated with Jenkins to perform automated static code analysis.

The analysis provides insights into:

- Bugs
- Vulnerabilities
- Code Smells
- Code Coverage
- Duplicated Code
- Maintainability Rating
- Reliability Rating
- Security Rating

A Quality Gate was configured to validate code quality before publishing artifacts.

---

# Nexus Repository Integration

Nexus Repository Manager serves as the centralized artifact repository.

The generated WAR package is uploaded automatically after the Quality Gate passes.

Benefits include:

- Centralized artifact storage
- Version management
- Reliable artifact distribution
- Enterprise repository management

---

# Project Screenshots

The repository contains screenshots demonstrating the complete implementation.

| Folder | Description |
|---------|-------------|
| 01-github | Source code repository and branch management |
| 02-jenkins | Jenkins configuration and successful builds |
| 03-sonarqube | Static code analysis and Quality Gate |
| 04-nexus | Artifact repository and uploaded WAR package |
| 05-pipeline | Successful Jenkins pipeline execution |
| 06-aws | AWS EC2 infrastructure |
| 07-troubleshooting | Troubleshooting documentation and solutions |

---

# Challenges Encountered

During implementation, several real-world engineering challenges were encountered and resolved.

Major issues included:

- Java version mismatch
- Maven installation issues
- Jenkins Pipeline syntax errors
- Missing Jenkins plugins
- SonarQube webhook configuration
- Nexus credentials configuration
- Jenkins Out Of Memory (OOM)
- AWS EC2 resource limitations
- Quality Gate waiting indefinitely
- Artifact upload failures

Resolving these issues provided practical troubleshooting experience with enterprise CI environments.

---

# Skills Demonstrated

This project demonstrates practical experience with:

- Continuous Integration (CI)
- Jenkins Declarative Pipelines
- Apache Maven
- Java Build Automation
- SonarQube Integration
- Nexus Repository Manager
- AWS EC2 Administration
- Linux System Administration
- Git & GitHub
- Static Code Analysis
- Artifact Management
- CI Pipeline Troubleshooting

---

# Future Enhancements

Potential improvements include:

- Continuous Deployment (CD) pipeline
- Docker containerization
- Kubernetes deployment
- Jenkins Shared Libraries
- Infrastructure as Code (Terraform)
- Monitoring with Prometheus & Grafana
- Automated deployment to Amazon EKS
- Pipeline notifications using Slack or Microsoft Teams

---

# Acknowledgements

The sample Java application used in this project is based on the open-source VProfile application.

This repository focuses on designing, implementing, and documenting an enterprise Continuous Integration (CI) pipeline using Jenkins, SonarQube, Nexus Repository Manager, GitHub, and AWS.

---

# Author

**Karanam Vikas**

Cloud & Site Reliability Engineering (SRE) Enthusiast

If you found this repository useful, consider giving it a ⭐ on GitHub.

---

