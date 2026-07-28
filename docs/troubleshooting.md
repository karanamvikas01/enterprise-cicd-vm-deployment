# Troubleshooting Guide

## Jenkins Out of Memory

### Problem

Pipeline terminated during Maven Build.

### Cause

Insufficient memory on Jenkins EC2.

### Resolution

- Added 2 GB Swap
- Upgraded EC2 instance
- Restarted Jenkins

---

## Java Version Mismatch

### Problem

Java Runtime and Compiler versions differed.

### Resolution

Updated Java alternatives to Java 21.

---

## SonarQube Quality Gate Waiting

### Problem

Pipeline remained in the Quality Gate stage.

### Resolution

Configured SonarQube Webhook to notify Jenkins.

---

## Missing Jenkins Plugins

Required plugins were installed:

- Nexus Artifact Uploader
- Pipeline Maven Integration
- SonarQube Scanner

---

## Nexus Upload Failure

### Cause

Missing Jenkins Credentials.

### Resolution

Configured Username/Password credentials and updated Jenkinsfile.

---

## Pipeline Syntax Errors

Resolved Groovy syntax issues within the Jenkinsfile.

---

# Lessons Learned

- Proper server sizing is important.
- Memory directly impacts Jenkins stability.
- Webhooks are essential for asynchronous Quality Gate notifications.
- Credentials should never be hardcoded.
- Pipeline automation reduces manual effort.