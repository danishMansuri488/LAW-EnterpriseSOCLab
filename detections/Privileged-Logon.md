# Privileged Logon Detection

## Overview

This detection monitors authentication events involving privileged accounts to improve visibility into administrative access across the environment. Privileged account activity should be closely monitored, as these accounts have elevated permissions and are common targets for attackers.

---

## Detection Objective

Identify successful logons performed by privileged or administrative accounts and detect unusual or unauthorized administrative access.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Valid Accounts | T1078 |
| Privilege Escalation | Account Manipulation | T1098 |

---

## Data Sources

- Windows Security Events
- Microsoft Sentinel
- Splunk Enterprise
- Active Directory

---

## Relevant Event ID

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4672 | Special Privileges Assigned to New Logon |

---

## Detection Logic

The detection monitors successful authentication events involving privileged accounts and correlates them with Event ID **4672**, which indicates that special administrative privileges were assigned to the session.

Monitoring focuses on:

- Domain Administrator logons
- Enterprise Administrator logons
- Local Administrator logons
- Privileged logons outside business hours
- Administrative access from unusual systems

---

## Investigation Guidance

Review the following during analysis:

- Account name
- Group membership
- Source computer
- Logon type
- Time of authentication
- Assigned privileges
- Related authentication events

Determine whether the activity represents:

- Authorized administrative activity
- Routine maintenance
- Privileged access abuse
- Compromised administrative account
- Suspicious lateral movement

---

## Validation

Validation was performed by logging into the laboratory environment using a privileged account and verifying successful detection within Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Windows Event IDs 4624 and 4672 generated
- Privileged logon successfully detected
- Detection query returns expected results
- Administrative activity available for investigation

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
