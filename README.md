# LAW-EnterpriseSOCLab

Microsoft Sentinel Security Operations Center (SOC) laboratory demonstrating security monitoring, detection engineering, analytics rule development, and log investigation using Microsoft Sentinel, Azure Log Analytics Workspace, Azure Monitor Agent (AMA), Sysmon, and Windows Security Events.

---

## Overview

LAW-EnterpriseSOCLab is a hands-on Microsoft Sentinel laboratory designed to simulate core Security Operations Center (SOC) workflows within a controlled environment. The project demonstrates how Windows security telemetry can be collected, analyzed, and investigated to identify suspicious activity using Microsoft Sentinel.

The lab focuses on building a foundational understanding of cloud-native SIEM operations, detection engineering, Kusto Query Language (KQL), analytics rule development, and log investigation while following industry-standard blue team practices.

---

## Objectives

- Deploy Microsoft Sentinel in Azure
- Collect Windows Security Events
- Configure Azure Monitor Agent (AMA)
- Ingest telemetry into Azure Log Analytics Workspace
- Develop Analytics Rules
- Perform log investigation using KQL
- Generate security alerts
- Understand Microsoft Sentinel fundamentals
- Map detections to the MITRE ATT&CK Framework

---

## Key Features

- Microsoft Sentinel Security Monitoring
- Azure Log Analytics Workspace Integration
- Azure Monitor Agent (AMA)
- Windows Security Event Collection
- Sysmon Telemetry Collection
- Analytics Rule Development
- Detection Engineering using KQL
- Security Alert Generation
- Log Investigation
- MITRE ATT&CK Mapping

---

## Technology Stack

| Category | Technology |
|----------|------------|
| SIEM | Microsoft Sentinel |
| Cloud Platform | Microsoft Azure |
| Monitoring Agent | Azure Monitor Agent (AMA) |
| Log Storage | Azure Log Analytics Workspace |
| Operating System | Windows 11 |
| Log Sources | Windows Security Events, Sysmon |
| Query Language | Kusto Query Language (KQL) |
| Framework | MITRE ATT&CK |

---

## Lab Architecture

The laboratory demonstrates how Windows security events are collected, processed, and analyzed within Microsoft Sentinel for security monitoring and investigation.

### Components

- Windows 11
- Sysmon
- Windows Security Events
- Azure Monitor Agent (AMA)
- Azure Log Analytics Workspace
- Microsoft Sentinel

<p align="center">
<img src="diagrams/architecture.png" width="900">
</p>

---

## Repository Structure

```text
LAW-EnterpriseSOCLab
│
├── detections/
├── diagrams/
├── docs/
├── queries/
├── screenshots/
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
└── README.md
```

---

## Documentation

The `docs/` directory contains detailed technical documentation covering:

- Lab Architecture
- Microsoft Sentinel Deployment
- Detection Engineering
- Log Investigation
- Analytics Rules
- MITRE ATT&CK Mapping
- Validation & Testing

---

## Detections

The laboratory includes detection use cases for:

- Failed Logon Detection
- Successful Logon Detection
- Brute Force Detection
- Privileged Logon Detection
- Account Lockout Detection
- New User Creation
- Group Membership Changes
- Suspicious Authentication

---

## Queries

Example Kusto Query Language (KQL) queries are included for:

- Windows Security Event Analysis
- Authentication Monitoring
- Detection Validation
- Threat Investigation
- Security Alert Analysis

---

## Screenshots

The repository includes representative screenshots demonstrating:

- Microsoft Sentinel Analytics Rules
- Log Analytics Queries
- Lab Architecture

---

## Skills Demonstrated

- Microsoft Sentinel
- Detection Engineering
- Security Monitoring
- Log Investigation
- Windows Security Events
- Azure Log Analytics Workspace
- Azure Monitor Agent (AMA)
- Sysmon
- Kusto Query Language (KQL)
- MITRE ATT&CK Framework

---

## Disclaimer

This project was developed for educational and research purposes within an isolated laboratory environment. All detections, monitoring, and investigations were performed exclusively in a controlled environment.

---

## Author

**Danish Mansuri**

Cyber Security | SOC Analyst | Microsoft Sentinel | Detection Engineering | Threat Hunting
