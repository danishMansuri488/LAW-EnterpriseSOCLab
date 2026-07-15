# Microsoft Sentinel KQL Queries

This document contains Kusto Query Language (KQL) queries used throughout the LAW-EnterpriseSOCLab project for detection engineering, security monitoring, and threat hunting.

---

# Failed Logon Detection

```kql
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Computer, Account, IpAddress, FailureReason
| sort by TimeGenerated desc
```

---

# Successful Logon Detection

```kql
SecurityEvent
| where EventID == 4624
| project TimeGenerated, Computer, Account, LogonType
| sort by TimeGenerated desc
```

---

# Brute Force Detection

```kql
SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count() by Account, Computer, bin(TimeGenerated,5m)
| where FailedAttempts >= 5
```

---

# Account Lockout Detection

```kql
SecurityEvent
| where EventID == 4740
| project TimeGenerated, TargetAccount, Computer
```

---

# Privileged Logon Detection

```kql
SecurityEvent
| where EventID == 4672
| project TimeGenerated, Account, Computer
```

---

# New User Creation

```kql
SecurityEvent
| where EventID == 4720
| project TimeGenerated, TargetAccount, SubjectAccount
```

---

# Group Membership Changes

```kql
SecurityEvent
| where EventID in (4728,4729,4732,4733)
| project TimeGenerated, TargetAccount, Group, SubjectAccount
```

---

# Remote Desktop (RDP) Logon

```kql
SecurityEvent
| where EventID in (4624,4625)
| where LogonType == 10
| project TimeGenerated, Account, Computer, IpAddress
```

---

# After-Hours Logon

```kql
SecurityEvent
| where EventID == 4624
| extend Hour=datetime_part("Hour", TimeGenerated)
| where Hour < 8 or Hour > 18
| project TimeGenerated, Account, Computer
```

---

# Suspicious Authentication

```kql
SecurityEvent
| where EventID in (4624,4625,4672,4740)
| project TimeGenerated, EventID, Account, Computer
| sort by TimeGenerated desc
```
