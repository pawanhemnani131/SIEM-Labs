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
