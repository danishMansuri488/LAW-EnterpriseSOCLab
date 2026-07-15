# Splunk SPL Queries

This document contains Splunk Processing Language (SPL) queries used throughout the LAW-EnterpriseSOCLab project for security monitoring, detection engineering, and threat hunting.

---

# Failed Logon Detection

```spl
index=main EventCode=4625
| table _time Account_Name ComputerName Failure_Reason
| sort -_time
```

---

# Successful Logon Detection

```spl
index=main EventCode=4624
| table _time Account_Name ComputerName Logon_Type
| sort -_time
```

---

# Brute Force Detection

```spl
index=main EventCode=4625
| bucket span=5m _time
| stats count by Account_Name ComputerName _time
| where count>=5
```

---

# Account Lockout Detection

```spl
index=main EventCode=4740
| table _time Account_Name ComputerName Caller_Computer_Name
```

---

# Privileged Logon Detection

```spl
index=main EventCode=4672
| table _time Account_Name ComputerName PrivilegeList
```

---

# New User Account Creation

```spl
index=main EventCode=4720
| table _time TargetUserName SubjectUserName ComputerName
```

---

# Group Membership Changes

```spl
index=main EventCode IN (4728,4729,4732,4733)
| table _time TargetUserName GroupName SubjectUserName
```

---

# Remote Desktop (RDP) Logon

```spl
index=main EventCode=4624 Logon_Type=10
| table _time Account_Name ComputerName Source_Network_Address
```

---

# After-Hours Logon

```spl
index=main EventCode=4624
| eval Hour=strftime(_time,"%H")
| where Hour<8 OR Hour>18
| table _time Account_Name ComputerName
```

---

# Suspicious Authentication

```spl
index=main EventCode IN (4624,4625,4672,4740)
| table _time EventCode Account_Name ComputerName
| sort -_time
```
