# Microsoft Sentinel Configuration

## Objective

Configure Microsoft Sentinel to collect Windows Security Events from the Azure virtual machine using the Azure Monitor Agent (AMA) and Data Collection Rules (DCR).

---

## Sentinel Configuration

| Setting | Configuration |
|---------|---------------|
| SIEM Platform | Microsoft Sentinel |
| Connected Workspace | Win11-LogAnalyzer |
| Data Connector | Windows Security Events via AMA |
| Monitoring Agent | Azure Monitor Agent (AMA) |
| Data Collection Rule | WindowsEventsToSentinel |
| Target Resource | Win11 Virtual Machine |
| Collected Events | All Events |

---

## Configuration

Microsoft Sentinel was enabled on the **Win11-LogAnalyzer** workspace. The **Windows Security Events** solution was then installed from the Sentinel Content Hub. After installation, the **Windows Security Events via AMA** data connector was configured, and a Data Collection Rule (DCR) was created to collect Windows Security Event logs from the virtual machine.

---

## Screenshots

**Figure 1:** Adding Microsoft Sentinel to the Log Analytics Workspace.

<img width="1792" height="807" alt="Screenshot 2026-07-06 145904" src="https://github.com/user-attachments/assets/914528e1-b526-41f4-ad49-2094f079c653" />

---

**Figure 2:** Installing the Windows Security Events solution from the Sentinel Content Hub.

<img width="1860" height="855" alt="Screenshot 2026-07-06 150550" src="https://github.com/user-attachments/assets/00d26b94-0048-4995-ba7e-ff726e455971" />

---

**Figure 3:** Data Collection Rule configuration for Windows Security Events.

<img width="847" height="701" alt="Screenshot 2026-07-06 150932" src="https://github.com/user-attachments/assets/2f8584bb-d657-4851-82f2-50fa05e68c5f" />

<img width="846" height="585" alt="Screenshot 2026-07-06 151159" src="https://github.com/user-attachments/assets/0fccbd4e-6b67-450b-a76e-0d65ee21215c" />

---

## Outcome

Microsoft Sentinel was successfully configured to ingest Windows Security Events from the target virtual machine through the Azure Monitor Agent. The collected logs are now available in the Log Analytics Workspace for threat hunting, investigation, and visualization.
