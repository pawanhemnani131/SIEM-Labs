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
