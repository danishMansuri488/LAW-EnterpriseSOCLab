# Detection Engineering

## Overview

Detection engineering is the process of designing, implementing, validating, and maintaining security detections that identify suspicious or malicious activity within an enterprise environment. This laboratory demonstrates practical detection engineering techniques using Microsoft Sentinel and Splunk Enterprise across Windows infrastructure.

---

## Objectives

The detection engineering workflow within this lab is designed to:

- Develop reliable detection logic
- Reduce false positives through validation
- Monitor authentication and endpoint activity
- Improve visibility into Windows security events
- Support efficient security investigations

---

## Detection Methodology

Each detection use case follows a structured engineering process:

1. Define the security objective.
2. Identify the required log source.
3. Develop the detection logic using KQL or SPL.
4. Generate controlled test events.
5. Validate detection accuracy.
6. Document findings and expected behavior.

---

## Data Sources

The following telemetry is used throughout the project:

- Windows Security Events
- Sysmon Events
- Active Directory Logs
- Windows Authentication Events
- Azure Log Analytics Workspace
- Splunk Indexes

---

## Detection Categories

The laboratory includes detections for:

- Failed Authentication Attempts
- Successful Logon Activity
- Brute Force Attempts
- Account Lockouts
- Privileged Logons
- New User Account Creation
- Group Membership Changes
- Remote Desktop Logons
- After-Hours Authentication
- Suspicious Process Creation (Sysmon)

---

## Detection Workflow

```text
Security Event
      │
      ▼
Log Collection
      │
      ▼
SIEM Ingestion
      │
      ▼
Detection Rule
      │
      ▼
Alert Generation
      │
      ▼
Investigation
      │
      ▼
Validation & Documentation
```

---

## Detection Validation

All detection rules were validated within the isolated laboratory environment by generating controlled security events and confirming successful detection within Microsoft Sentinel and Splunk Enterprise.

---

## Related Documentation

Detailed detection specifications are available in the `/detections` directory.
