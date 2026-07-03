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
Deploy a Windows endpoint, register it with the Wazuh Manager, and verify successful event collection.

### Completed
- Generated Windows agent deployment package
- Installed the Wazuh Agent on the Windows 10 host
- Configured the agent to communicate with the Wazuh Manager
- Started and verified the Wazuh Agent service
- Registered endpoint `WIN10-JEREMY`
- Confirmed endpoint status as **Active**
- Verified endpoint communication with the Wazuh Manager
- Generated multiple failed Windows logon attempts
- Confirmed detection of Windows Event ID `4625`
- Investigated events using the Threat Hunting dashboard

### Detection Validation
Successfully detected:
- Windows Event ID 4625
- Failed authentication attempts
- Endpoint telemetry from `WIN10-JEREMY`
- Real-time event collection and indexing

### Skills Demonstrated
- Linux Administration
- Wazuh Administration
- Windows Endpoint Monitoring
- SIEM Deployment
- Threat Hunting
- Windows Event Log Analysis
- Security Monitoring
- Incident Investigation
- Endpoint Registration and Management

### Outcome
Successfully deployed and enrolled a Windows endpoint into the Wazuh SIEM environment. Verified end-to-end telemetry collection and confirmed detection of failed Windows authentication events through the Threat Hunting dashboard.