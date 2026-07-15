# Brute Force Detection

## Overview

This detection identifies repeated authentication failures that may indicate a brute-force attack against Windows user accounts. By correlating multiple failed logon events within a defined time window, security analysts can quickly identify password guessing activity and initiate an investigation before account compromise occurs.

---

## Detection Objective

Detect repeated failed authentication attempts targeting one or more user accounts within a short period of time.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Credential Access | Brute Force | T1110 |

---

## Data Sources

- Windows Security Events
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event IDs

| Event ID | Description |
|----------|-------------|
| 4625 | Failed Logon |
| 4740 | Account Lockout *(Optional correlation)* |

---

## Detection Logic

The detection correlates multiple Windows Event ID **4625** events generated within a defined time window from the same source, targeting the same or multiple accounts.

Typical detection characteristics include:

- Multiple failed logons within a short timeframe
- Repeated attempts against a single account
- Password spraying across multiple accounts
- Authentication attempts from the same source system

---

## Investigation Guidance

Review the following during analysis:

- Source computer
- Source IP address (if available)
- Target account(s)
- Failure reason
- Authentication package
- Number of failed attempts
- Time interval between events

Determine whether the activity represents:

- User password mistakes
- Password spraying
- Brute-force attack
- Automated authentication attempts
- Unauthorized access activity

---

## Validation

Validation was performed by generating multiple failed authentication attempts within the laboratory environment and confirming successful detection in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Multiple Event ID 4625 events detected
- Detection rule triggered
- Alert generated (if configured)
- Activity available for investigation
- Detection visible in dashboards

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
