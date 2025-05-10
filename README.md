# FIM-Using-Wazuh
# 🧠 Introduction to EDR (Endpoint Detection and Response)
- **EDR refers to tools that monitor, record, and analyze activities on endpoints (servers, desktops, laptops) to detect malicious behavior, help in incident response, and enable threat hunting.**

# 🔎 How Does a SOC Analyst Use EDR?

 SOC Analysts rely on EDR tools to:
  
- **Detect suspicious behaviors (e.g., process injection, lateral movement)**
- **Investigate alerts and correlate activity over time**
- **Isolate or respond to infected endpoints**
- **Pull forensic artifacts like logs, memory dumps, and timelines.**
- **Hunt for threat indicators (IOCs)**

# 🛡️ Wazuh?
- **Wazuh is a free and open-source security tool that acts like a smart security guard for your computers and servers. It helps you monitor, detect, and respond to cyber threats by checking for unusual behavior, file changes, malware, and insecure settings.**

# 🧪 LAB:- File Integrity Monitoring.

##  Setting up wazuh 

   ## Requirements
- **System 1: Ubuntu 22.04/20.04 (Wazuh Server)**
- **System 2: Ubuntu 22.04/20.04 (Agent Machine to be monitored)**
- **Minimum Hardware for Wazuh Server:**
    - **CPU: 4 vCPUs**
    - **RAM: 8GB+**
    - **Storage: 50GB+**
**Network Connectivity: Ensure both systems can communicate over the network.**
**User Permissions: Root or sudo privileges on both machines.**

## Configure the wazuh
 - **downloaded wazuh server on first ubuntu machine**
 - **setting up wazuh agent on secon ubuntu machine**
 - **Now third machine for attack**





# Step 1: Configure File Integrity Monitoring (FIM) in Wazuh
- 1:- Open Wazuh Manager Configuration on the Wazuh Server:
  -      sudo nano /var/ossec/etc/ossec.conf
![Wazuh - Google Chrome 08-05-2025 12_01_00](https://github.com/user-attachments/assets/122120eb-41a7-4d03-b7ab-df239b60d3fa)

  
