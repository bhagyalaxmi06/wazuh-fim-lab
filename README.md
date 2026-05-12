# Wazuh File Integrity Monitoring (FIM) Lab

## Objective
Configure Wazuh File Integrity Monitoring between Ubuntu Wazuh Manager and Windows Agent.

## Environment
- Ubuntu VM - Wazuh Manager
- Windows 11 - Wazuh Agent
- VirtualBox NAT Network

## Configuration

Edited:

C:\Program Files (x86)\ossec-agent\ossec.conf

Added:

<syscheck>
  <disabled>no</disabled>
  <directories realtime="yes">C:\Users</directories>
</syscheck>

## Restarted Agent

net stop WazuhSvc
net start WazuhSvc

## Testing
Created, modified, and deleted:

C:\Users\test.txt

## Result
Wazuh detected:
- File added
- File modified
- File deleted

## Skills Learned
- Wazuh
- SIEM
- File Integrity Monitoring
- Windows Agent Configuration
- SOC Monitoring
