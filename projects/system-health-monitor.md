# System Health Monitor

## Jenkins Pipeline

![System Health Monitor Jenkins Pipeline](../assets/images/system-health-monitor-jenkins.png)

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

Technologies Used
Linux
Bash / Shell Scripting
Git
GitHub
Jenkins
Jenkins Pipeline
CI/CD
Docker
Monitoring Capabilities

The script monitors:

CPU

Checks CPU utilization against the configured threshold.

Memory

Calculates memory utilization and compares it with the configured threshold.

Disk

Checks root filesystem utilization.

System Information

The report also captures:

Hostname
Current user
Current date
CPU statistics
Memory statistics
Disk usage
System uptime
Jenkins Pipeline

The Jenkins pipeline performs the following:

Checks out the source code from GitHub.
Makes the monitoring script executable.
Executes the Bash monitoring script.
Generates health_report.txt.
Determines the overall system health.
Marks the Jenkins build as SUCCESS or FAILURE.
Archives the health report as a Jenkins artifact.
Example Healthy Result
CPU Usage: 1%
HEALTHY: CPU usage is below 80%.

Memory Usage: 37%
HEALTHY: Memory usage is below 80%.

Root Disk Usage: 1%
HEALTHY: Disk usage is below 80%.

OVERALL SYSTEM HEALTH: HEALTHY
Failure Scenario

If a monitored resource exceeds its configured threshold, the script reports:

CRITICAL: Resource usage exceeded threshold.

System health check failed.

The Jenkins pipeline then returns a failed build.

Jenkins Artifact

Every successful execution generates:

health_report.txt

The report is archived by Jenkins and can be accessed from the build's
Last Successful Artifacts section.

Key DevOps Concepts Demonstrated
CI/CD pipeline implementation
Jenkins Declarative Pipeline
Git-based source control
Linux automation
Bash scripting
Build failure handling
Threshold-based monitoring
Artifact archiving
Automated health reporting
Pipeline troubleshooting
Repository Structure
system-health-monitor/
│
├── Jenkinsfile
├── system_health_monitor.sh
├── README.md
└── health_report.txt
Future Improvements

Possible enhancements include:

Email/Slack notifications
Dockerized monitoring environment
Prometheus metrics
Grafana dashboards
Scheduled monitoring
AWS infrastructure monitoring

### Commit it

Use:

```text
Add System Health Monitor project documentation
