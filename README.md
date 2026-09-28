# Tenable - Unauthenticated vs. Authenticated Scans
Project that performs both Unauthenticated and Authenticated vulnerability scans with the Tenable platform, to compare the results and information provided by each method in order to demonstrate the importance of using authenticated scans to reveal deeper system vulnerabilities.

This vulnerability scan was conducted on a Windows 11 VM within Azure.

---

## ⚙️ Technology Utilized
- **Tenable.io** – Vulnerability scanning and management platform.
- **Azure Virtual Machines** – Windows 11 VM for scanning and target testing.
- **Azure Network Security Groups (NSG)** - Configuring the NSG to allow Tenable access to the system.
- **Windows Firewall** – Disabled for demonstration of unauthenticated scans.

---

## 📁 Project Structure

---

## 📝 Phase 1: VM Creation and Environment Setup
✅ **Deployed a Windows 11 VM in Azure.**  

<img width="1000" height="800" alt="Deploying VM" src="VM Labs - Images/VM deployed.png"/> 

---

✅ **Configuring Network Security Group Inbound Rule to allow access for Tenable** 

<img width="1000" height="800" alt="Configuring Inbound Rule" src="VM Labs - Images/NSG Configuration - Inbound Rule.png"/> 

---

✅ **Connected to VM via Bastion** 

<img width="1000" height="800" alt="Connecting via Bastion" src="VM Labs - Images/Connecting via Bastion.png"/> 

---

✅ **Turning off Windows Defender Firewalls on VM** 

<img width="1000" height="800" alt="Turning off WDE Firewalls" src="VM Labs - Images/Turning off Windows Defender Firewalls.png"/> 

---

## 📝 Phase 2: Unauthenticated Scan
✅ **Setting up Unauthenticated Scan in Tenable:**  

<img width="1000" height="800" alt="Setting up unauthenticated scan" src="VM Labs - Images/Creating Scan in Tenable.png"/> 

---

✅ **Configuring scan settings and adding the IP Address of our target VM:**  

---

<img width="1000" height="800" alt="Setting up unauthenticated scan" src="VM Labs - Images/Setting up Scan Settings.png"/> 

---

✅ **Configuring the Discovery setting to ensure pinging and fast network discovery are enbled:**

---

<img width="1000" height="800" alt="Setting up unauthenticated scan" src="VM Labs - Images/Setting up Scan Settings 2.png"/> 

---

✅ **Unathenticated Scan in Progress:**

---

<img width="1000" height="800" alt="unauthenticated scan running" src="VM Labs - Images/Unauthenticated Scan Running.png"/> 

---


✅ **Scan Results:**  

<img width="1000" height="800" alt="scan results" src="VM Labs - Images/Scan Results - On Screen.png"/> 

✅ **Exported Executive Summary Scan Results:**  

<img width="1000" height="800" alt="executive summary scan results" src="VM Labs - Images/Scan Results.png"/> 

---

## 📝 Phase 3: Authenticated Scan
✅ **Adjusting settings to an Authenticated Scan in Tenable:**  

<img width="1000" height="800" alt="adjusting scan details to created an authenticated scan" src="VM Labs - Images/Editing Scan Details to add credentials.png"/> 

---

✅ **Adding the VM Credential for Authenticated Scan:** 

<img width="1000" height="800" alt="credentials added" src="VM Labs - Images/Credentials Added.png"/> 

---

✅ **Authenticated Scan Running:**  

<img width="1000" height="800" alt="authenticated scan running" src="VM Labs - Images/Authenticated Scan Running.png"/> 

---

✅ **Authenticated Scan Results:**  


---

## 💬 Group Meeting Chat
**Mock discussion to plan the next steps:**

> **L10 (Security Engineer):** Hey team, I ran the unauthenticated scan on the VM and got four medium vulnerabilities, mostly around TLS and SSL. Ran the authenticated scan and got...  
> **John (SysAdmin):** Awesome, thanks! Lets prioritize That’s expected—no credentials means we miss local issues.  
> **Felipe:** Exactly. After enabling authenticated scans, I found 1 critical, 5 high, and 19 medium vulnerabilities.  
> **John:** Let’s prioritize critical and high findings for the next CAB meeting.  
> **Felipe:** Agreed! I’ll prepare a remediation plan for those.  

---

## 🔍 Comparison of Scan Results
| Metric                       | Unauthenticated Scan | Authenticated Scan |
|------------------------------|----------------------|--------------------|
| Critical Vulnerabilities     | 0                    | 1                  |
| High Vulnerabilities         | 0                    | 5                  |
| Medium Vulnerabilities       | 6                    | 19                 |
| Low Vulnerabilities          | 1                    | 3                  |
| Info/Low-Level Findings      | 29                   | 136                |
| **Total Vulnerabilities**    | 36                   | 164                |

Authenticated scans provide a more accurate view of system vulnerabilities and should be prioritized in enterprise environments.

---
