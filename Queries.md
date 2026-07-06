# KQL Queries

This directory contains the Kusto Query Language (KQL) queries used to investigate Windows Security Events collected by Microsoft Sentinel.

---

## 1. Failed Authentication Attempts

Retrieves all failed Windows logon events (Event ID 4625).

```kusto
SecurityEvent
| where EventID == 4625
| project TimeGenerated, Computer, Account, IpAddress, FailureReason, Status, SubStatus
| order by TimeGenerated desc
```

---

## 2. Successful Authentication Events

Retrieves successful Windows logon events (Event ID 4624).

```kusto
SecurityEvent
| where EventID == 4624
| project TimeGenerated, Account, IpAddress, LogonTypeName
| order by TimeGenerated desc
```

---

## 3. Top Attacking IP Addresses

Displays source IPs with the highest number of failed authentication attempts.

```kusto
SecurityEvent
| where EventID == 4625
| summarize Attempts=count() by IpAddress
| order by Attempts desc
```

---

## 4. Targeted Usernames

Shows usernames targeted during failed login attempts.

```kusto
SecurityEvent
| where EventID == 4625
| summarize Attempts=count() by TargetUserName
```

---

## 5. Logon Types

Displays the distribution of Windows logon types.

```kusto
SecurityEvent
| summarize Count=count() by LogonTypeName
```
