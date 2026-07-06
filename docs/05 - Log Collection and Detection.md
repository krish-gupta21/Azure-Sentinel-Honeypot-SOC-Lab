# Log Collection and Detection

## Objective

Verify that Windows Security Events are successfully ingested into Microsoft Sentinel and configure a scheduled analytics rule to detect successful and failed sign-in events.

---

## KQL Query

```kusto
SecurityEvent
| where Activity contains "failed"
    or Activity contains "success"
    and Account !contains "system"
```

The query filters Windows Security Events to identify successful and failed authentication attempts while excluding system-generated accounts.

---

## Detection Rule Configuration

| Setting | Value |
|---------|-------|
| Rule Name | Successful and Failed SignIns |
| Rule Type | Scheduled |
| Severity | Medium |
| MITRE ATT&CK | Initial Access |
| Query Frequency | Every 5 Minutes |
| Lookup Period | Last 5 Hours |
| Status | Enabled |

---

## Configuration

After confirming that Windows Security Events were available in Microsoft Sentinel, a KQL query was created to identify authentication events. This query was then used to create a scheduled analytics rule, enabling Microsoft Sentinel to automatically detect and generate alerts for matching events.

---

## Screenshots

**Figure 1:** Windows Security Events retrieved using a KQL query.

<img width="1847" height="842" alt="Screenshot 2026-07-07 014026" src="https://github.com/user-attachments/assets/01eb24f3-6240-4a2a-b4ac-0e090ba1db4f" />

---

**Figure 2:** Scheduled Analytics rule review and deployment.

<img width="652" height="707" alt="Screenshot 2026-07-07 014823" src="https://github.com/user-attachments/assets/deb588e3-1eef-4d71-b0f7-bf57a3e950ff" />

---

**Figure 3:** Detection rule available in Microsoft Defender.

<img width="652" height="707" alt="Screenshot 2026-07-07 014823" src="https://github.com/user-attachments/assets/fe1e2d36-a68b-4e9e-adb4-c1c1cb1f65b2" />

---

## Outcome

Windows Security Events were successfully queried using KQL, and a scheduled analytics rule was deployed to automatically monitor authentication events. The rule is now available within Microsoft Defender and Microsoft Sentinel for continuous monitoring.
