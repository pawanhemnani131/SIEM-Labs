Kali Linux – Wazuh Server
RAM: 8 GB
CPU: 8 Cores
Disk Space: 140 GB
OS: Kali Linux Rolling
Hypervisor: VMware Workstation
Wazuh: Manager, Indexer and Dashboard (Docker)

Windows 11 – Analysis Machine
RAM: 4 GB
CPU: 2 Cores
Disk Space: 48 GB
OS: Windows 11 Pro
Hypervisor: VMware Workstation
Sysmon: Installed and Running
Wazuh Agent: Installed and Running

Network Configuration
Hypervisor: VMware Workstation
Network Mode: NAT
Kali Linux and Windows 11 are connected to the same virtual network.
Both machines communicate for Wazuh agent-server connectivity.

Wazuh Agent Connectivity
Wazuh Agent is installed on Windows 11.
Windows service status: Running.
Wazuh Dashboard status: Active.
Agent successfully connected to Wazuh Manager.

By default sysmon is not installed in windows and we have to configure that in configure file
In windows  "C:\Program Files (x86)\ossec-agent\ossec.conf" this is the exact location of the configuration file
<localfile>
  <location>Microsoft-Windows-Sysmon/Operational</location>
  <log_format>eventchannel</log_format>
</localfile>
This is the xml format which will be pasted inside ossec.conf 

Time Configuration
Set Windows 11 timezone to India Standard Time (IST).
Synchronized Windows system clock.
Set Kali timezone to Asia/Kolkata.
Enabled NTP time synchronization on Kali.
Verified time using Get-Date, date, and timedatectl.
Updated Wazuh Dashboard timezone to Asia/Kolkata.
Changed timestamp format to 12-hour format (AM/PM).
Verified that new events display the correct timezone and format.
We do this because if this all time is not right we get logs with wrong time.

Wazuh Dashboard Planning for monitoring Sysmon events and specific windows events
Dashboard 1 – Sysmon: Monitor Sysmon events during malware execution to identify process, file, registry, network and other system activities.
Dashboard 2 – Windows Events: Monitor important Windows Security Event IDs related to malware execution and investigation.
Purpose: Keep both event sources organised separately and make important activities easier to identify during malware analysis.

Editing Custom Wazuh Rules
Wazuh Dashboard does not provide direct editing of local_rules.xml.
The file is stored inside the Wazuh Manager Docker volume.
File location on Kali:
/var/lib/docker/volumes/single-node_wazuh_etc/_data/rules/local_rules.xml
Commands
Check existing rules:
bash
sudo cat /var/lib/docker/volumes/single-node_wazuh_etc/_data/rules/local_rules.xml
Edit the file using Nano on Kali:
bash
sudo nano /var/lib/docker/volumes/single-node_wazuh_etc/_data/rules/local_rules.xml
Save: Ctrl + O, Enter
Exit: Ctrl + X
NOTE: I have installed docker for my wazuh installation on kali linux and you can do this on ubuntu also without docker. 
