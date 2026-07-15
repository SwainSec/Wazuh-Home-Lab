# Wazuh Home Lab Build Log

## Session 1 — June 30, 2026

### Completed
- Planned overall project
- Created project folder structure
- Created GitHub repository
- Installed VMware Workstation Pro
- Created Ubuntu Server virtual machine
- Installed Ubuntu Server
- Configured networking
- Configured storage
- Enabled OpenSSH
- Booted Ubuntu Server successfully

### Lessons
- Learned the purpose of NAT networking.
- Learned why LVM was not required.
- Learned Linux hostname conventions.
- Learned the importance of documenting engineering decisions.

### Next Session
- Log into Ubuntu
- Update Ubuntu
- Install Open VM Tools
- Learn basic Linux commands
- Create VMware snapshot

## Session 2 — July 1, 2026

### Objectives
Prepare Ubuntu Server for Wazuh deployment.

### Completed
- Logged into Ubuntu Server
- Verified hostname
- Verified network configuration
- Verified internet connectivity
- Updated Ubuntu repositories
- Installed available updates
- Verified Open VM Tools
- Practiced essential Linux commands
- Created VMware restore snapshot

### Linux Commands Learned
```bash
hostnamectl
ip addr
ping
sudo apt update
sudo apt upgrade
pwd
ls
ls -la
cd
mkdir
touch
cp
mv
rm
nano
cat
```

### Snapshot Created
`Milestone-02-Server-Preparation`

### Ready For
Milestone 3 – Wazuh Installation

## Session 3 — July 2, 2026

### Milestone
**Milestone 3 – Wazuh Installation**
**Status:** ✅ Completed

### Objective
Deploy the Wazuh SIEM platform by installing the core components required for centralized security monitoring.

### Completed
- Verified system readiness
- Verified internet connectivity
- Verified Ubuntu version
- Verified disk space
- Verified available memory
- Verified CPU information
- Downloaded the Wazuh installation assistant
- Installed Wazuh Manager
- Installed Wazuh Indexer
- Installed Wazuh Dashboard
- Installed and configured Filebeat
- Verified all services were running
- Successfully accessed the Wazuh Dashboard
- Reset the administrator password
- Successfully authenticated to the dashboard

### Commands Used
```bash
hostnamectl
ping -c 4 google.com
lsb_release -a
df -h
free -h
lscpu
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
chmod +x wazuh-install.sh
sudo ./wazuh-install.sh -a
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

### Issues Encountered

**Installer Download**
The initial installer download failed due to an incorrect package URL.
*Resolution:* Downloaded the correct Wazuh installation assistant before continuing.

**Dashboard Login**
The automatically generated administrator password did not authenticate successfully.
*Resolution:* Located the Wazuh password management utility, reset the administrator password, and successfully authenticated to the dashboard.

### Verification
Successfully verified:
- Wazuh Manager running
- Wazuh Indexer running
- Wazuh Dashboard running
- Filebeat running
- Dashboard accessible from Windows host
- Administrator login successful

### Screenshots Captured
- Hostname
- Internet Connectivity
- Ubuntu Version
- Disk Space
- System Memory
- CPU Information
- Wazuh Installer Download
- Installation Progress
- Dashboard Installation
- Installation Complete
- Dashboard Login
- Dashboard Overview

### Lessons
- Learned the architecture of the Wazuh platform.
- Verified Linux services using `systemctl`.
- Learned how to troubleshoot installation issues.
- Reset administrative credentials using Wazuh management tools.
- Successfully deployed a production-style SIEM platform.

### Outcome
Milestone 3 was completed successfully. The Wazuh SIEM platform is fully operational and ready for endpoint deployment.

### Ready For
Milestone 4 – Agent Deployment

## Session 4 — July 2, 2026

### Completed
- Verified Wazuh Manager
- Verified Wazuh Indexer
- Verified Wazuh Dashboard
- Connected Windows 10 endpoint
- Successfully registered `WIN10-JEREMY`
- Generated Windows failed logon events
- Verified Windows Event ID 4625 detection
- Confirmed end-to-end SIEM functionality

### Outcome
Successfully completed Wazuh configuration and validated live endpoint monitoring.

## Session 5 — July 2, 2026

### Milestone
**Milestone 4 – Wazuh Configuration**

### Objective
Validate the Wazuh platform, verify core services, and confirm the SIEM is operating correctly before onboarding endpoints.

### Completed
- Verified Wazuh Manager service
- Verified Wazuh Indexer service
- Verified Wazuh Dashboard service
- Logged into the Wazuh Dashboard
- Explored the Threat Hunting interface
- Reviewed available security modules
- Confirmed platform health and readiness

### Outcome
Successfully validated the Wazuh deployment. All core services were active and the dashboard was fully operational.

## Session 6 — July 2, 2026

### Milestone
**Milestone 5 – Windows Agent Deployment**

### Objective
Deploy the Wazuh Windows Agent, register it with the Wazuh Manager, and verify successful endpoint communication.

### Completed
- Downloaded and installed the Wazuh Windows Agent on the Windows 10 endpoint.
- Configured the agent to communicate with the Wazuh Manager.
- Assigned the agent name `WIN10-JEREMY`.
- Started the Wazuh Agent service.
- Verified successful registration with the Wazuh Manager.
- Confirmed the endpoint appeared in the Wazuh Dashboard.
- Validated agent status as **Active**.
- Generated Windows Security events to test log collection.
- Confirmed Windows Event ID `4625` (Failed Logon) was successfully collected and displayed in the Wazuh Dashboard.

### Challenges Encountered
- Corrected the Wazuh Manager IP address during agent configuration.
- Verified Windows Firewall and network connectivity between the endpoint and the Wazuh Manager.
- Confirmed the Wazuh Agent service was running after installation.

### Resolution
Validated communication between the Windows endpoint and the Wazuh Manager by confirming agent registration and successful ingestion of Windows Security logs into the Wazuh Dashboard.

### Outcome
Successfully deployed the Windows endpoint, established secure communication with the Wazuh Manager, and verified end-to-end telemetry from the Windows system into the SIEM platform. This milestone completed the endpoint onboarding process and prepared the environment for advanced detection and monitoring activities.

## Session 7 — July 14–15, 2026

### Milestone
**Milestone 6 – Detection and Monitoring**

### Objective
Configure File Integrity Monitoring (FIM), validate Windows endpoint telemetry, and confirm end-to-end alert ingestion into the Wazuh Dashboard.

### Completed
- Verified Wazuh Manager, Indexer, Dashboard, and Filebeat services.
- Configured File Integrity Monitoring (FIM) on the Windows endpoint.
- Added a custom monitored directory (`C:\FIM-Test`) with real-time monitoring enabled.
- Restarted the Wazuh Windows Agent to apply the updated configuration.
- Generated test events by creating, modifying, and deleting files in the monitored directory.
- Confirmed FIM events were written to `/var/ossec/logs/alerts/alerts.json`.
- Verified Syscheck rules for file creation and deletion.
- Investigated why alerts were not appearing in the Wazuh Dashboard.
- Confirmed Wazuh Indexer cluster health was GREEN.
- Verified Filebeat service status and connectivity to the Indexer.
- Loaded the Filebeat index template and validated communication with the Wazuh Indexer.
- Confirmed creation of the `wazuh-alerts-*` index.
- Verified Windows security events and FIM alerts were searchable in the Wazuh Dashboard Discover page.

### Challenges Encountered
- File Integrity Monitoring alerts were successfully generated but initially did not appear in the Wazuh Dashboard.
- The `wazuh-alerts-*` index was not being populated as expected, requiring troubleshooting of the log ingestion pipeline.
- Encountered authentication and command syntax issues while validating Indexer connectivity, which were resolved during the troubleshooting process.

### Resolution
Systematically validated each component of the Wazuh architecture:
1. Windows Agent
2. Wazuh Manager
3. alerts.json
4. Filebeat
5. Wazuh Indexer
6. Wazuh Dashboard

After confirming Filebeat connectivity and loading the required index template, alert ingestion resumed successfully. The `wazuh-alerts-*` index was created and security events became visible within the Discover dashboard.

### Outcome
Successfully completed File Integrity Monitoring validation and confirmed end-to-end telemetry from the Windows endpoint through the Wazuh SIEM platform. This milestone demonstrated the ability to configure endpoint monitoring, troubleshoot SIEM data ingestion, validate Indexer health, and investigate security events using Wazuh.
