# Threat Hunting

## Overview

Threat hunting is a proactive security practice focused on identifying suspicious or malicious activity that may evade traditional detection mechanisms. This laboratory demonstrates structured hunting methodologies using Microsoft Sentinel, Splunk Enterprise, and Windows security telemetry.

---

## Objectives

The primary objectives of threat hunting within this laboratory are to:

- Identify anomalous authentication activity
- Investigate privileged account usage
- Detect suspicious endpoint behavior
- Validate detection coverage
- Improve visibility across Windows infrastructure

---

## Hunting Methodology

Threat hunting activities follow a repeatable process:

1. Define a hunting hypothesis.
2. Identify relevant telemetry sources.
3. Execute KQL or SPL hunting queries.
4. Analyze returned events.
5. Validate findings.
6. Document observations and conclusions.

---

## Data Sources

The following telemetry is used during threat hunting:

- Windows Security Events
- Sysmon Operational Logs
- Active Directory Events
- Windows Authentication Logs
- Microsoft Sentinel
- Splunk Enterprise

---

## Hunting Scenarios

The laboratory includes threat hunting scenarios for:

- Multiple Failed Logons
- Brute Force Activity
- Privileged Account Usage
- Account Lockouts
- New User Creation
- Group Membership Changes
- Remote Desktop Logons
- After-Hours Authentication
- Suspicious Process Execution
- Unusual Endpoint Activity

---

## Hunting Workflow

```text
Hunting Hypothesis
        │
        ▼
Telemetry Collection
        │
        ▼
KQL / SPL Queries
        │
        ▼
Event Analysis
        │
        ▼
Investigation
        │
        ▼
Findings & Documentation
```

---

## Outcome

Threat hunting within this laboratory complements detection engineering by enabling proactive identification of suspicious behaviors, validating existing detections, and improving overall visibility into enterprise security events.

---

## Related Documentation

Detailed hunting scenarios and queries are available in the `/hunting` and `/queries` directories.
