# SIEM – Malware Analysis & Detection Engineering Lab

## About This Lab

This lab focuses on practical malware analysis, endpoint monitoring, threat investigation and detection engineering using Wazuh.

The idea is to analyze malware samples in an isolated Windows 11 virtual machine, understand their behavior through static and dynamic analysis, collect endpoint telemetry using Sysmon and Wazuh Agent, and investigate those events through the Wazuh dashboard.

Based on the findings, we will develop custom detection rules, generate security alerts and test how effectively our SIEM identifies suspicious activities.

## What We Are Doing

- Collecting malware samples from sources such as MalwareBazaar and VX-Underground.
- Performing static analysis using PEStudio, PE-bear, Detect It Easy and IDA Pro.
- Performing dynamic analysis using System Informer, x64dbg and other debugging tools.
- Monitoring Windows activities through Sysmon.
- Forwarding endpoint logs to Wazuh.
- Investigating process execution, registry modifications, file activity and other suspicious events.
- Creating custom Wazuh detection rules and security alerts.
- Performing controlled adversary emulation to validate detection capabilities.

## Goals

1. Understand malware structure and execution behavior.
2. Develop practical static and dynamic malware analysis skills.
3. Understand Windows endpoint telemetry and security events.
4. Configure and work with Wazuh as a SIEM platform.
5. Develop custom detection rules based on observed behavior.
6. Identify detection gaps and improve detection coverage.
7. Build practical experience in malware analysis, threat hunting and detection engineering.

## Prerequisites

- Basic understanding of Windows and Linux.
- Basic knowledge of networking and cybersecurity concepts.
- Familiarity with virtual machines and VMware Workstation.
- A working Kali Linux environment with Wazuh installed.
- A Windows 11 virtual machine with Wazuh Agent and Sysmon.
- Basic knowledge of PowerShell and Windows processes.

## Sample Handling & Isolation

- Malware samples will be obtained from trusted research sources such as MalwareBazaar and VX-Underground.
- Each sample will be identified using its SHA256 hash and recorded in the sample inventory.
- Actual malware files will never be stored in the GitHub repository.
- Samples will be stored in a dedicated, restricted directory inside the analysis VM.
- Windows 11 will run as an isolated virtual machine in VMware Workstation.
- Shared folders, shared clipboard and drag-and-drop will be disabled.
- Network access will be disabled during initial malware execution. Controlled network simulation may be used when required.
- Snapshots will be taken before each analysis.
- The VM will be reverted to a clean snapshot after testing.

Malware execution will remain restricted to the isolated analysis environment to prevent accidental exposure of the host machine or external systems.

## Documentation

All practical exercises, observations, detection rules, investigation findings and screenshots will be documented in this repository as the lab progresses.

All malware analysis and execution activities will be performed in an isolated virtual environment. Actual malware samples will not be committed to this repository.
