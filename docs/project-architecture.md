# Project Architecture

## Overview

This project demonstrates an enterprise Continuous Integration architecture using Jenkins, SonarQube, Nexus Repository, GitHub, Maven, and AWS EC2.

---

# Architecture Components

## GitHub

Stores the application source code and Jenkins pipeline definition.

---

## Jenkins

Acts as the automation server.

Responsibilities:

- Build Automation
- Testing
- Code Analysis
- Artifact Publishing

---

## Maven

Responsible for:

- Dependency Management
- Compilation
- Packaging
- Testing

---

## SonarQube

Performs:

- Static Code Analysis
- Security Analysis
- Maintainability Checks
- Quality Gate Validation

---

## Nexus Repository

Stores build artifacts.

Benefits:

- Artifact Versioning
- Central Repository
- Deployment Readiness

---

## AWS

Infrastructure hosting:

- Jenkins EC2
- SonarQube EC2
- Nexus EC2

---

# Pipeline Workflow

GitHub

↓

Jenkins

↓

Build

↓

Test

↓

Checkstyle

↓

SonarQube

↓

Quality Gate

↓

Nexus Repository

---

# Design Goals

- Automation
- Reliability
- Code Quality
- Repeatable Builds
- Centralized Artifact Storage