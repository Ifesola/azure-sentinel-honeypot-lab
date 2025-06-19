#  Azure Sentinel Honeypot Lab

This project is a step-by-step cybersecurity lab simulating real-world detection and monitoring using **Azure Sentinel**, 
**Windows VM Honeypot**, **Log Analytics**, **KQL**, and **IP Geolocation Enrichment**.
---

##  Technologies Used

- Azure Virtual Machine (Windows 10)
- Azure Network Security Groups (NSGs)
- Azure Log Analytics Workspace (LAW)
- Microsoft Sentinel (SIEM)
- Kusto Query Language (KQL)
- Event Viewer
- Sentinel Watchlists (GeoIP Enrichment)
- Custom Workbook (Attack Map Visualization)

---

##  Lab Objectives

- Set up a honeypot virtual machine in Azure.
- Capture and analyze failed login attempts.
- Forward security events to a centralized log repository.
- Use KQL to investigate login patterns and security events.
- Enrich logs with GeoIP data using Sentinel Watchlists.
- Visualize attack sources on a world map.

---

##  Lab Steps

###  Part 1: Setup Azure Subscription
- [Create an Azure account](https://azure.microsoft.com/en-us/pricing/purchase-options/azure-account) (Free or Paid).
- Log in to the Azure portal: https://portal.azure.com

---

###  Part 2: Create a Honeypot VM
- Create a **Windows 10 VM** in Azure.
- Allow **inbound traffic** for all ports via NSG rule.
- Disable **Windows Firewall** inside the VM (`wf.msc`).

---

###  Part 3: Simulate Failed Logins & Inspect Logs
- Attempt 3 failed logins using a fake user (e.g., `employee`).
- Use **Event Viewer** to observe `Event ID 4625` (failed logins).
- Prepare to forward logs to a central workspace.

---

###  Part 4: Log Forwarding & KQL Basics
- Create a **Log Analytics Workspace (LAW)**.
- Connect LAW to **Microsoft Sentinel**.
- Configure the **AMA Security Events connector**.
- Use **KQL** to query failed logins:

```kql
SecurityEvent
| where EventID == 4625


## Lessons Learned
How to configure an Azure VM as a honeypot.

Importance of Event ID 4625 in brute-force detection.

Forwarding logs using AMA to Log Analytics & Sentinel.

Writing KQL queries to investigate and enrich security events.

Creating visual security dashboards using Sentinel Workbooks.

##  Author
Ifesola Fadare
Aspiring SOC Analyst | Cloud Security | Cybersecurity Enthusiast



##  Credits
Josh Madakor YouTube Channel

KC7Cyber KQL Learning Platform
