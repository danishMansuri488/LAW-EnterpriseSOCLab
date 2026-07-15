# New User Account Creation Detection

## Overview

This detection monitors the creation of new user accounts within the Active Directory environment. Since attackers often create new accounts to establish persistence or gain unauthorized access, monitoring account creation events is an important component of identity security.

---

## Detection Objective

Identify newly created user accounts and validate whether the activity was authorized or potentially malicious.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Persistence | Create Account | T1136 |
| Privilege Escalation | Create Account | T1136 |

---

## Data Sources

- Windows Security Events
- Active Directory
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event ID

| Event ID | Description |
|----------|-------------|
| 4720 | A user account was created |

---

## Detection Logic

The detection monitors Windows Event ID **4720**, which is generated whenever a new user account is created within Active Directory or the local system.

Monitoring focuses on:

- Newly created user accounts
- Administrative account creation
- Unexpected account creation outside change windows
- Multiple account creation events within a short period

---

## Investigation Guidance

Review the following during analysis:

- Account creator
- New account name
- Target system
- Time of creation
- Associated administrative privileges
- Related authentication activity

Determine whether the activity represents:

- Authorized administrative action
- Scheduled provisioning
- Unauthorized account creation
- Persistence by an attacker

---

## Validation

Validation was performed by creating a test user account within the laboratory Active Directory environment and confirming successful event collection and visibility in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Windows Event ID 4720 generated
- User creation successfully detected
- Detection query returns expected results
- Activity available for investigation

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
