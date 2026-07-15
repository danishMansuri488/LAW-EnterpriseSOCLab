# Remote Desktop (RDP) Logon Detection

## Overview

This detection monitors Remote Desktop Protocol (RDP) authentication events to identify remote interactive logons within the enterprise environment. Because RDP is commonly used for remote administration and is frequently targeted by attackers, monitoring these events helps identify unauthorized access and potential lateral movement.

---

## Detection Objective

Identify successful and failed Remote Desktop logons and detect unusual remote access activity requiring investigation.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Lateral Movement | Remote Services | T1021 |

---

## Data Sources

- Windows Security Events
- Microsoft Sentinel
- Splunk Enterprise

---

## Relevant Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon (Logon Type 10) |
| 4625 | Failed Logon (Logon Type 10) |

---

## Detection Logic

The detection monitors Windows authentication events where **Logon Type = 10**, indicating a Remote Desktop session.

Monitoring focuses on:

- Successful RDP logons
- Failed RDP authentication attempts
- Administrative RDP sessions
- Remote logons outside normal business hours
- Repeated RDP authentication failures

---

## Investigation Guidance

Review the following during analysis:

- Username
- Source IP Address
- Source Computer
- Destination Host
- Authentication Time
- Logon Status

Determine whether the activity represents:

- Authorized remote administration
- Routine IT operations
- Unauthorized remote access
- Brute-force attempts against RDP
- Potential lateral movement

---

## Validation

Validation was performed by initiating Remote Desktop sessions within the laboratory environment and confirming successful event collection and visibility in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- RDP authentication events generated
- Detection query returns expected results
- Remote access activity visible for investigation
- Alert generated (if configured)

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
