# After-Hours Logon Detection

## Overview

This detection monitors successful user authentications occurring outside defined business hours. After-hours logons may represent legitimate administrative activity or indicate unauthorized access that requires investigation.

---

## Detection Objective

Identify user authentication events occurring outside approved operating hours to improve visibility into potentially suspicious account activity.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Defense Evasion | Valid Accounts | T1078 |
| Persistence | Valid Accounts | T1078 |

---

## Data Sources

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

The detection monitors successful authentication events and compares the event timestamp against defined business hours.

Monitoring includes:

- Successful logons outside business hours
- Administrative account access after hours
- Weekend authentication activity
- Repeated after-hours logons from the same account

---

## Investigation Guidance

Review the following during analysis:

- Username
- Logon time
- Source computer
- Logon type
- Privilege level
- Related authentication history

Determine whether the activity represents:

- Authorized maintenance
- Approved remote administration
- Suspicious account usage
- Potential unauthorized access

---

## Validation

Validation was performed by generating successful logon events outside the configured business hours and confirming successful detection in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- After-hours authentication identified
- Detection query returns expected results
- Activity available for investigation
- Alert generated (if configured)

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Threat-Hunting.md`
- `queries/`
