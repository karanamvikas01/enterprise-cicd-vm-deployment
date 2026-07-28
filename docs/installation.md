# Installation Guide

## Overview

This document describes the setup process for the Enterprise Continuous Integration Pipeline on AWS.

---

# Prerequisites

Before starting, ensure the following resources are available:

- AWS Account
- Ubuntu EC2 Instances
- GitHub Account
- Java 21
- Apache Maven
- Jenkins
- SonarQube Community Edition
- Sonatype Nexus Repository
- Git

---

# Infrastructure Setup

The project uses three EC2 instances.

| Server | Purpose |
|----------|---------|
| Jenkins | CI Server |
| SonarQube | Static Code Analysis |
| Nexus Repository | Artifact Management |

---

# Jenkins Setup

Install:

- Java
- Maven
- Git
- Jenkins

Configure:

- GitHub Repository
- SonarQube Server
- Nexus Credentials
- Required Jenkins Plugins

---

# SonarQube Setup

Install SonarQube Community Edition.

Configure:

- Project
- Authentication Token
- Webhook
- Jenkins Integration

---

# Nexus Setup

Install Nexus Repository Manager.

Create repositories:

- maven-releases
- maven-snapshots
- maven-public

Configure Jenkins credentials for artifact upload.

---

# Pipeline Execution

Execute the Jenkins Pipeline.

Pipeline Stages:

1. Checkout SCM
2. Build
3. Unit Test
4. Checkstyle
5. SonarQube Analysis
6. Quality Gate
7. Upload Artifact

---

# Validation

Verify:

- Successful Jenkins Build
- SonarQube Analysis
- Quality Gate Passed
- WAR Artifact Uploaded to Nexus

---

# Result

A complete enterprise Continuous Integration pipeline was successfully implemented on AWS.