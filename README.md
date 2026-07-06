# 🛡️ Azure Home SOC Lab using Microsoft Sentinel

> A cloud-based Home Security Operations Center (SOC) lab built on Microsoft Azure to simulate, collect, detect, and investigate real-world authentication attacks using Microsoft Sentinel and Kusto Query Language (KQL).

![Azure](https://img.shields.io/badge/Microsoft-Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Sentinel](https://img.shields.io/badge/Microsoft-Sentinel-5E5E5E?style=for-the-badge)
![KQL](https://img.shields.io/badge/KQL-Query_Language-blue?style=for-the-badge)
![Windows](https://img.shields.io/badge/Windows_Server-2025-0078D6?style=for-the-badge&logo=windows)

---

# 📖 Project Overview

This project demonstrates the deployment of a cloud-native Security Operations Center (SOC) using **Microsoft Azure** and **Microsoft Sentinel**.

A Windows Server virtual machine was intentionally exposed to the internet through **Remote Desktop Protocol (RDP)** to simulate a honeypot environment. Security events generated from authentication attempts were collected using the **Azure Monitor Agent (AMA)**, stored in **Log Analytics Workspace**, and analyzed using **Kusto Query Language (KQL)**.

The project showcases the complete SOC workflow from infrastructure deployment to log collection, threat hunting, analytics rule creation, and security event investigation.

---

# 🎯 Objectives

- Deploy a Windows Server VM in Microsoft Azure
- Configure Azure Log Analytics Workspace
- Integrate Microsoft Sentinel
- Collect Windows Security Events using Azure Monitor Agent (AMA)
- Configure Data Collection Rules (DCR)
- Perform threat hunting using KQL
- Detect failed and successful authentication attempts
- Create scheduled analytics rules for automated detection
- Analyze real-world authentication activity against an exposed RDP service

---

# 🏗️ Architecture

```text
                Internet
                    │
                    ▼
            Azure Public IP
                    │
                    ▼
         Windows Server VM (RDP)
                    │
                    ▼
        Azure Monitor Agent (AMA)
                    │
                    ▼
      Data Collection Rule (DCR)
                    │
                    ▼
      Log Analytics Workspace
                    │
                    ▼
        Microsoft Sentinel
          │               │
          ▼               ▼
    KQL Queries     Analytics Rules
          │
          ▼
   Threat Hunting & Analysis
```

---

# 🛠️ Technologies Used

| Category | Technologies |
|----------|--------------|
| Cloud Platform | Microsoft Azure |
| SIEM | Microsoft Sentinel |
| Log Storage | Azure Log Analytics Workspace |
| Monitoring Agent | Azure Monitor Agent (AMA) |
| Operating System | Windows Server 2025 Datacenter Azure Edition |
| Query Language | Kusto Query Language (KQL) |
| Detection | Scheduled Analytics Rules |
| Remote Access | Remote Desktop Protocol (RDP) |

---

# 📂 Repository Structure

```text
Azure-Home-SOC-Lab/
│
├── README.md
├── LICENSE
│
├── architecture/
│   └── Home_Soc_Lab_Architecure.png
│
├── docs/
│   ├── 01-Virtual-Machine-Deployment.md
│   ├── 02-Log-Analytics-Workspace.md
│   ├── 03-Microsoft-Sentinel-Configuration.md
│   ├── 04-Log-Collection-and-Detection.md
│   └── 05-Threat-Hunting-and-Analysis.md
│
└── queries.md
```

---

# 🔄 SOC Workflow

1. Deploy Azure Virtual Machine
2. Create Log Analytics Workspace
3. Enable Microsoft Sentinel
4. Install Windows Security Events Solution
5. Configure Azure Monitor Agent (AMA)
6. Create Data Collection Rule (DCR)
7. Collect Windows Security Events
8. Execute KQL Queries
9. Create Scheduled Analytics Rule
10. Investigate Authentication Events

---

# 📚 Documentation

| Phase | Documentation |
|--------|---------------|
| Virtual Machine Deployment | [01-Virtual-Machine-Deployment.md](docs/01-Virtual-Machine-Deployment.md) |
| Log Analytics Workspace | [02-Log-Analytics-Workspace.md](docs/02-Log-Analytics-Workspace.md) |
| Microsoft Sentinel Configuration | [03-Microsoft-Sentinel-Configuration.md](docs/03-Microsoft-Sentinel-Configuration.md) |
| Log Collection & Detection | [04-Log-Collection-and-Detection.md](docs/04-Log-Collection-and-Detection.md) |
| Threat Hunting & Analysis | [05-Threat-Hunting-and-Analysis.md](docs/05-Threat-Hunting-and-Analysis.md) |

---

# 🔍 Threat Hunting Queries

The project includes several KQL queries for investigating Windows Security Events.

- Failed Authentication Attempts
- Successful Authentication Events
- Top Attacking IP Addresses
- Targeted Usernames
- Windows Logon Types

All queries are available in the **queries/** directory.

---

# 🚨 Detection Rule

A scheduled Microsoft Sentinel Analytics Rule was created to automatically detect authentication activity.

| Property | Value |
|----------|-------|
| Rule Name | Successful and Failed SignIns |
| Rule Type | Scheduled |
| Severity | Medium |
| MITRE ATT&CK | Initial Access |
| Frequency | Every 5 Minutes |
| Status | Enabled |

---

# 📊 Key Findings

- Successfully deployed a cloud-native SOC environment using Microsoft Azure.
- Windows Security Events were collected through Azure Monitor Agent.
- Microsoft Sentinel successfully ingested authentication logs.
- KQL queries identified both successful and failed authentication events.
- External IP addresses attempted authentication against the exposed RDP service.
- Automated detection was implemented using a scheduled analytics rule.
- Authentication events were successfully analyzed to distinguish legitimate administrator access from unauthorized login attempts.

---

# 🚀 Future Improvements

- Create Microsoft Sentinel Workbooks for visualization
- Display attacker locations on a geographic map
- Configure incident automation using Playbooks
- Integrate Microsoft Defender for Cloud
- Add additional Windows Security Event analytics
- Monitor PowerShell and Sysmon events
- Implement email alerting for high-severity detections

---

# 📖 References

- Microsoft Azure Documentation
- Microsoft Sentinel Documentation
- Azure Monitor Documentation
- Kusto Query Language (KQL) Documentation
- MITRE ATT&CK Framework

---

# Disclaimer

This project was developed for educational and defensive security purposes. The virtual machine was intentionally exposed to the internet in a controlled Azure lab environment to generate and analyze authentication events using Microsoft Sentinel. No unauthorized testing was performed against third-party systems.

---

# 👨‍💻 Author

**Krish Gupta**

Cybersecurity Enthusiast | SOC Analyst | Ethical Hacking | Cloud Security

- LinkedIn: https://www.linkedin.com/in/krishguptaofficial/
- GitHub: https://github.com/krish-gupta21

---

# 📄 License

MIT License

Copyright (c) 2026 Krish Gupta

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
