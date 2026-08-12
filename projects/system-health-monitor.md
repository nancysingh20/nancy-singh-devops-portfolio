# System Health Monitor

## Overview

A Linux system health monitoring project automated through Jenkins CI/CD.

The project collects system information and checks CPU, memory and disk
utilization against defined thresholds. The pipeline generates a health
report and archives it as a Jenkins build artifact.

---

## Architecture

```text
GitHub
   |
   v
Jenkins
   |
   v
Checkout Source Code
   |
   v
Bash Health Monitor
   |
   +---- CPU Check
   |
   +---- Memory Check
   |
   +---- Disk Check
   |
   v
Overall System Health
   |
   +---- HEALTHY
   |
   +---- CRITICAL
   |
   v
health_report.txt
   |
   v
Jenkins Artifact
