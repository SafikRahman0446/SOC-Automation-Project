# SOC-Automation-Project
SOC Automation Project – An end-to-end Security Operations Center (SOC) automation lab integrating Wazuh (SIEM + EDR), TheHive (Incident Response), Shuffle (SOAR), and VirusTotal (Threat Intelligence). Includes attack simulation with Mimikatz on Windows 10, automated alert enrichment, case creation, and SOC team notifications.

### 🔧 Tools & Technologies
- **Wazuh** – SIEM + EDR (Log collection & monitoring)
- **TheHive** – Incident Response Platform
- **Shuffle** – SOAR automation workflows
- **VirusTotal** – Threat Intelligence API
- **Windows 10** – Endpoint with Wazuh Agent + Mimikatz (attack simulation)
- **Ubuntu 22.04** – Hosting TheHive & Shuffle
- **Ubuntu** – Hosting Wazuh Manager

## 🔄 Workflow
1. **Attack Simulation**:
   - On Windows 10, **Mimikatz** is executed to simulate credential dumping.
   - Logs are collected by the **Wazuh Agent**.

2. **Log Analysis**:
   - Logs are forwarded to **Wazuh Manager**.
   - Alerts are triggered based on detection rules.

3. **Automation with Shuffle**:
   - Alerts are sent via **Webhook → Shuffle Workflow**.
   - Workflow extracts SHA256 file hashes from the alert.
   - Hashes are checked in **VirusTotal** for reputation.

4. **Automated Response**:
   - If malicious → **Case is created in TheHive** for incident investigation.
   - **Email Notification** is sent to SOC team with details.
     
