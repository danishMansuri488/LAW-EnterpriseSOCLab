# Suspicious Authentication Detection

## Overview

This detection identifies authentication activity that deviates from normal user behavior and may indicate unauthorized access, credential misuse, or account compromise. By correlating multiple authentication indicators, security analysts can investigate potentially suspicious login activity before it escalates into a security incident.

---

## Detection Objective

Detect authentication events that exhibit anomalous characteristics requiring further investigation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Valid Accounts | T1078 |
| Credential Access | Brute Force | T1110 |
| Lateral Movement | Remote Services | T1021 |

---

## Data Sources

- Windows Security Events
- Active Directory
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4672 | Special Privileges Assigned to New Logon |
| 4740 | Account Lockout |

---

## Detection Logic

Authentication activity is evaluated for suspicious indicators, including:

- Multiple failed authentication attempts
- Successful logon following repeated failures
- Privileged account authentication
- Authentication outside normal business hours
- Remote Desktop (RDP) logons
- Authentication from unexpected systems

Detection logic correlates related authentication events to identify behaviors that warrant further investigation.

---

## Investigation Guidance

Review the following during analysis:

- Username
- Source computer
- Source IP address (if available)
- Logon type
- Authentication timeline
- Privilege level
- Related authentication events

Determine whether the activity represents:

- Normal user behavior
- Administrative activity
- Brute-force attack
- Password spraying
- Unauthorized account usage
- Potential lateral movement

---

## Validation

Validation was performed by generating controlled authentication scenarios within the laboratory environment and verifying successful event collection, correlation, and visibility in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Authentication events successfully collected
- Suspicious activity identified
- Detection query returns expected results
- Activity available for investigation
- Alert generated (if configured)

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Threat-Hunting.md`
- `docs/Incident-Response.md`
- `queries/`
