# File-Integrity-Monitoring-Using-Wazuh
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
- **1:- Open Wazuh Manager Configuration on the Wazuh Server:**

  -     sudo nano /var/ossec/etc/ossec.conf
![Wazuh - Google Chrome 08-05-2025 12_01_00](https://github.com/user-attachments/assets/122120eb-41a7-4d03-b7ab-df239b60d3fa)

- **2:- Add the following configuration under to monitor sensitive files on Windows**
-     <syscheck>
      <frequency>600</frequency>
      <directories check_all="yes">C:\Users\Public\Documents</directories>
      </syscheck>
![Ubuntu 1 - VMware Workstation 16 Player (Non-commercial use only) 08-05-2025 12_02_47](https://github.com/user-attachments/assets/99c648a5-68e3-4402-b996-923605b6455a)
- **This monitors changes in the Public Documents folder**

- **3:- Restart Wazuh Manager to apply changes**
-     sudo systemctl restart wazuh-manager
![sarim@sarim-virtual-machine_ ~ 08-05-2025 12_12_31](https://github.com/user-attachments/assets/73aa1100-72ef-49bc-961c-c877e2973451)

## Configure wazuh agent for file integrity monitoring
- **1:- Open the file in on a wazuh agent**
-     sudo nano /var/ossec/etc/ossec.conf
![Ubuntu 1 - VMware Workstation 16 Player (Non-commercial use only) 08-05-2025 12_04_40](https://github.com/user-attachments/assets/9ac8adb9-ba0b-42f0-9add-69cc25ff2274)
- **2:- Scroll and go to a file integrity monitoring section**
-  **3:- add the following section**
-     <directories check_all="yes" report_changes="yes" realtime="yes">/hoem/kali</directories>
 ![sarim@sarim-virtual-machine_ ~ 08-05-2025 12_11_22](https://github.com/user-attachments/assets/46157bd7-0bdc-4422-bc85-205b2ece0db3)

-  **This will check all changes  and perform real time monetoring if any chenges have done.**

# Step 2: Simulate an Unauthorized File Change on Wazuh agent

- **Make the file on wazuh agent and check if wazuh monitors the file integrity**
-      touch king7.txt
![Wazuh - Google Chrome 08-05-2025 15_23_00](https://github.com/user-attachments/assets/6a0d585e-90a3-4907-b497-7b0c4aba8dff)

## Step 3 : Monitor file itegrity on wazuh dashboard

- **Log in to a wazuh web interface by login password**
- **click on the endpoint which is our wazuh agent and go to a file integrity section.**
- **We can see the file name which we craeted on the wazuh agent  and other information also.**
![Wazuh - Google Chrome 08-05-2025 15_25_02](https://github.com/user-attachments/assets/9b2956cd-cfbc-4d9f-b49c-142e56ec524c)
- **Click on the event section to see events.**
![Wazuh - Google Chrome 08-05-2025 15_22_42](https://github.com/user-attachments/assets/c9c56f07-7ed0-433a-b7f2-e4c939c9f253)

![Wazuh - Google Chrome 08-05-2025 15_25_33](https://github.com/user-attachments/assets/5cab1917-0760-4174-9308-b6281f433f3c)

# Conclusion
- **This task  help me to  detect and investigate unauthorized file changes on a linux machine using Wazuh File Integrity Monitoring (FIM).I learned how to monitor sensitive files for unauthorized modifications, simulate an attack by modifying a file, and analyze alerts in Wazuh.**


   


  
