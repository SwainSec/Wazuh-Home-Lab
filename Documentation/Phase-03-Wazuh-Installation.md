# Phase 03 – Wazuh Installation

## Objective
Install and verify a fully functional Wazuh SIEM environment consisting of:
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

The goal of this phase was to deploy the core components of the Wazuh platform and confirm successful operation before deploying monitored endpoints.

## Environment

### Host System
- Windows 10
- AMD Ryzen 7 1700X
- 32 GB RAM
- VMware Workstation

### Virtual Machine
- Ubuntu Server 24.04 LTS
- Hostname: `wazuh-server01`
- IP Address: `192.168.241.129`

## Pre-Installation Verification
The following checks were completed before installation:
- Verified hostname
- Verified internet connectivity
- Verified Ubuntu version
- Verified available disk space
- Verified available memory
- Verified CPU information
- Updated and upgraded the operating system

## Installation
The official Wazuh installation assistant was used to deploy the platform.

**Installed components:**
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

## Service Verification
The following services were verified after installation.

| Service | Status |
|----------|--------|
| Wazuh Manager | ✅ Running |
| Wazuh Indexer | ✅ Running |
| Wazuh Dashboard | ✅ Running |
| Filebeat | ✅ Running |

**Verification commands:**
```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

## Dashboard Access
**Dashboard URL:**
```
https://192.168.241.129
```

**Authentication:**
- Username: `admin`
- Password: Reset after installation

The dashboard loaded successfully and administrative access was verified.

## Issues Encountered

### Installer Download
The initial installer download returned an access denied response.

**Resolution:**
- Downloaded the correct Wazuh installer.
- Verified installer integrity before execution.

### Dashboard Login
The generated administrator password did not authenticate successfully.

**Resolution:**
- Located the Wazuh password management utility.
- Reset the administrator password.
- Successfully authenticated to the dashboard.

## Screenshots
- 01-Hostname.png
- 02-Internet-Connectivity.png
- 03-Ubuntu-Version.png
- 04-Disk-Space.png
- 05-System-Memory.png
- 06-CPU-Information.png
- 07-Wazuh-Installer-Started.png
- 08-Wazuh-Components-Installing.png
- 09-Wazuh-Dashboard-Installing.png
- 10-Wazuh-Installation-Complete.png
- 11-Wazuh-Login-Page.png
- 12-Wazuh-Dashboard-Login-Success.png
- 13-Wazuh-Dashboard-Overview.png

## Lessons Learned
- Verified system readiness before installing enterprise software.
- Learned the architecture of the Wazuh platform.
- Verified Linux services using systemctl.
- Resolved installation and authentication issues through troubleshooting.
- Successfully deployed and validated a production-style SIEM environment.

## Outcome
**Status:** ✅ Complete

The Wazuh SIEM platform was successfully installed, configured, and verified.

## Next Steps
Proceed to Phase 04 – Agent Deployment: deploy Windows endpoints, enroll agents into Wazuh, and validate endpoint communication.