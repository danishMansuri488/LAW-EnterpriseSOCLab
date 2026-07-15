# MITRE ATT&CK Mapping

## Overview

Detection and threat hunting use cases within this laboratory are aligned with the MITRE ATT&CK framework to provide standardized mapping between observed behaviors and adversary techniques. This mapping improves detection coverage analysis and supports consistent investigation workflows.

---

## ATT&CK Coverage

| Tactic | Technique | ID |
|--------|-----------|----|
| Initial Access | Valid Accounts | T1078 |
| Credential Access | Brute Force | T1110 |
| Persistence | Create Account | T1136 |
| Privilege Escalation | Account Manipulation | T1098 |
| Defense Evasion | Valid Accounts | T1078 |
| Discovery | Account Discovery | T1087 |
| Lateral Movement | Remote Services (RDP) | T1021 |
| Collection | Data from Local System | T1005 |

---

## Detection Alignment

The laboratory includes detection use cases that support:

- Authentication Monitoring
- Brute Force Detection
- Account Lockout Detection
- Privileged Logon Monitoring
- User Account Creation
- Group Membership Changes
- Remote Desktop Activity
- Endpoint Process Monitoring

---

## Purpose

MITRE ATT&CK mapping provides a common framework for understanding adversary behavior, validating detection coverage, and identifying opportunities to improve security monitoring within the laboratory environment.
