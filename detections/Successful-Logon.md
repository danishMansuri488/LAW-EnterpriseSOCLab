# Successful Logon Detection

## Overview

This detection monitors successful Windows authentication events to establish visibility into user access patterns and identify potentially suspicious authentication activity. Monitoring successful logons helps detect unauthorized account usage, privileged access, and unusual authentication behavior.

---

## Detection Objective

Monitor successful user authentications to identify abnormal login activity, privileged account usage, and access originating from unexpected systems or time periods.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Valid Accounts | T1078 |
| Persistence | Valid Accounts | T1078 |

---

## Data Source

- Windows Security Events
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event ID

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |

---

## Detection Logic

The detection monitors Windows Security Event **4624**, which records successful authentication events.

Monitoring should include:

- Privileged account logons
- Interactive logons
- Remote Desktop logons
- Unusual authentication times
- Logons from unfamiliar systems
- High-frequency authentication activity

---

## Investigation Guidance

Review the following attributes during analysis:

- Username
- Source computer
- Logon type
- Authentication package
- Logon process
- Timestamp
- Workstation name

Determine whether the activity represents:

- Normal business activity
- Administrative access
- Unauthorized account usage
- Lateral movement
- Suspicious authentication behavior

---

## Validation

Validation was performed by generating successful authentication events within the laboratory environment and confirming successful ingestion and visibility in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Windows Event ID 4624 generated
- Event successfully ingested into SIEM
- Detection query returns expected results
- Authentication activity available for investigation

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
