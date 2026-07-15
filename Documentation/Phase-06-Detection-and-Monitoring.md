# Phase 06 – Detection and Monitoring

## Objective
The objective of this phase was to validate the Wazuh SIEM deployment by configuring File Integrity Monitoring (FIM), generating security events from a Windows endpoint, and verifying that alerts were successfully processed through the entire Wazuh pipeline.

## Lab Environment

**Wazuh Manager**
- Ubuntu Server
- Hostname: `wazuh-server01`

**Endpoint**
- Windows 10
- Agent Name: `WIN10-JEREMY`

**Hypervisor**
- VMware Workstation Pro

## Tasks Completed

### 1. Verified Wazuh Services
Verified that the following services were operational:
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

All services were confirmed to be running successfully.

### 2. Configured File Integrity Monitoring (FIM)
Configured the Windows agent to monitor a custom directory.

**Monitored directory:**
```
C:\FIM-Test
```

**Enabled:**
- Real-time monitoring
- Report file changes

### 3. Generated File Events
Created test files inside the monitored directory to trigger File Integrity Monitoring alerts.

**Performed the following actions:**
- Created files
- Modified files
- Deleted files

These actions successfully generated FIM events.

### 4. Verified Alert Generation
Confirmed that alerts were generated within:
```
/var/ossec/logs/alerts/alerts.json
```

**Verified Syscheck alerts including:**
- File Added
- File Modified
- File Deleted

### 5. Indexer Troubleshooting
During validation, alerts were successfully written to `alerts.json` but were not visible within the Wazuh Dashboard.

**Troubleshooting steps included:**
- Verified Wazuh Manager status
- Verified Filebeat status
- Verified Indexer cluster health
- Tested Filebeat output
- Verified Indexer authentication
- Loaded Filebeat index template
- Restarted Filebeat
- Validated index creation

After loading the Filebeat index template, the `wazuh-alerts-*` index was successfully created and alert ingestion resumed.

### 6. Dashboard Validation
Confirmed successful alert ingestion by viewing events within the Wazuh Dashboard Discover page.

**Verified:**
- Windows Security Events
- File Integrity Monitoring Events
- Agent communication
- Indexed security events

## Skills Demonstrated
- SIEM Administration
- Linux Administration
- Windows Endpoint Monitoring
- File Integrity Monitoring (FIM)
- Filebeat Configuration
- OpenSearch Index Troubleshooting
- Threat Monitoring
- Security Event Analysis
- Log Ingestion Validation

## Outcome
Successfully implemented and validated Wazuh File Integrity Monitoring. Verified end-to-end telemetry from the Windows endpoint through the Wazuh Manager, Filebeat, Indexer, and Dashboard. Resolved an indexing issue through systematic troubleshooting and restored successful alert ingestion into the Wazuh Dashboard.

## Portfolio Value
This phase demonstrates the ability to:
- Deploy and manage a SIEM solution
- Configure endpoint monitoring
- Investigate log ingestion issues
- Troubleshoot Filebeat and OpenSearch
- Validate security telemetry
- Perform real-world SOC troubleshooting