
# Account Lockout Detection

## Overview

This detection monitors Windows account lockout events to identify authentication failures that exceed the configured account lockout threshold. Frequent account lockouts may indicate brute-force attacks, password spraying, or repeated authentication failures requiring investigation.

---

## Detection Objective

Identify user accounts that become locked due to excessive failed authentication attempts and determine whether the activity is malicious or the result of normal user behavior.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Credential Access | Brute Force | T1110 |
| Defense Evasion | Valid Accounts | T1078 |

---

## Data Sources

- Windows Security Events
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event ID

| Event ID | Description |
|----------|-------------|
| 4740 | A user account was locked out |

---

## Detection Logic

The detection monitors Windows Event ID **4740**, which is generated whenever a user account is locked after exceeding the configured authentication failure threshold.

Detection should include:

- Multiple account lockouts
- Repeated lockouts for the same account
- Lockouts from the same source system
- Lockouts affecting privileged accounts

---

## Investigation Guidance

Review the following during analysis:

- Locked account
- Source computer
- Time of lockout
- Previous failed logon events
- Related authentication activity
- Privilege level of the affected account

Determine whether the activity represents:

- User password mistakes
- Brute-force attack
- Password spraying
- Misconfigured service account
- Unauthorized authentication attempts

---

## Validation

Validation was performed by generating repeated failed authentication attempts until the configured account lockout threshold was reached and confirming successful detection within Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Windows Event ID 4740 generated
- Account lockout successfully detected
- Detection rule returns expected results
- Alert generated (if configured)
- Event available for investigation

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
