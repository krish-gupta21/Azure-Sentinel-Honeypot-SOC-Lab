# Virtual Machine Deployment

## Objective

Deploy a Windows Server virtual machine in Microsoft Azure that will act as a honeypot for collecting RDP attack telemetry. The VM is intentionally exposed to the internet so that authentication events can later be monitored using Microsoft Sentinel.

---

## Deployment Configuration

| Setting | Configuration |
|---------|---------------|
| Resource Group | Win11-rg |
| Virtual Machine | Win11 |
| Region | East Asia |
| Availability | Availability Zone (Zone 2) |
| Security Type | Trusted Launch |
| Operating System | Windows Server 2025 Datacenter Azure Edition (Gen2) |
| VM Size | Standard_D2s_v3 (2 vCPU, 8 GB RAM) |
| Authentication | Username & Password |
| Virtual Network | Win11-vnet |
| Subnet | Default (10.1.0.0/24) |
| Public IP | Enabled |
| Network Security Group | Basic |
| Inbound Port | RDP (TCP/3389) |
| OS Disk | Premium SSD (127 GB) |
| Boot Diagnostics | Enabled |

---

## Deployment

A Windows Server 2025 virtual machine was deployed using the above configuration. A new virtual network, subnet, network interface, managed disk, and public IP address were created during deployment. RDP (TCP/3389) was intentionally enabled to simulate real-world brute-force attacks and generate security logs for later analysis in Microsoft Sentinel.

> **Note:** Exposing RDP to the internet is not recommended for production environments. It was enabled only for this controlled SOC lab.

---

## Screenshot

> **Figure 1:** Azure Virtual Machine configuration and deployment.

<img width="482" height="712" alt="image" src="https://github.com/user-attachments/assets/65629920-aa7c-449a-b393-96b8cac1262f" />

<img width="446" height="585" alt="image" src="https://github.com/user-attachments/assets/2cf58610-92df-4b3c-b3fb-70791abf4871" />

<img width="486" height="722" alt="Screenshot 2026-07-06 143146" src="https://github.com/user-attachments/assets/6d6c1d5a-dda5-4d67-a25d-99acdb714545" />

---

## Outcome

The virtual machine was successfully deployed and is ready for:
- Remote Desktop access
- Log collection
- Microsoft Sentinel integration
- Threat monitoring and analysis
