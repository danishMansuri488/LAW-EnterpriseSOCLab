# Group Membership Change Detection

## Overview

This detection monitors changes to security group memberships within Active Directory. Unauthorized modifications to privileged groups can significantly increase an attacker's access and are often associated with privilege escalation or persistence techniques.

---

## Detection Objective

Identify additions or removals of users from security groups, with particular attention to privileged groups such as Domain Admins, Enterprise Admins, and Administrators.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Privilege Escalation | Account Manipulation | T1098 |
| Persistence | Account Manipulation | T1098 |

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
| 4728 | Member added to a security-enabled global group |
| 4729 | Member removed from a security-enabled global group |
| 4732 | Member added to a security-enabled local group |
| 4733 | Member removed from a security-enabled local group |

---

## Detection Logic

The detection monitors security group membership changes and highlights modifications involving privileged groups or unexpected administrative activity.

Monitoring includes:

- Users added to privileged groups
- Users removed from privileged groups
- Multiple membership changes within a short period
- Changes performed outside approved maintenance windows

---

## Investigation Guidance

Review the following during analysis:

- User performing the change
- Target user account
- Group name
- Time of modification
- Source system
- Related administrative activity

Determine whether the activity represents:

- Authorized administrative changes
- Privilege escalation
- Unauthorized access
- Suspicious account manipulation

---

## Validation

Validation was performed by adding and removing a test user from security groups within the laboratory Active Directory environment and verifying successful detection in Microsoft Sentinel and Splunk Enterprise.

---

## Expected Outcome

Successful validation should confirm:

- Appropriate security events generated
- Group membership changes successfully detected
- Detection query returns expected results
- Activity available for investigation

---

## Related Documentation

- `docs/Detection-Engineering.md`
- `docs/Incident-Response.md`
- `queries/`
