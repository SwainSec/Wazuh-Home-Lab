# Lessons Learned

This document tracks the key takeaways from each phase of the Wazuh Home Lab project — the curated, portfolio-facing insights, as opposed to the raw session notes in the Build Log.

## Phase 1 — Infrastructure Setup
Focused on building the virtual infrastructure to host the Wazuh SIEM server.

- Proper planning makes future phases easier.
- VMware provides a safe environment for cybersecurity labs.
- Ubuntu Server is preferred over Ubuntu Desktop for infrastructure services.
- NAT networking is appropriate for initial lab deployment.
- Documentation should be created alongside the project, not after it.

## Phase 2 — Server Preparation
Focused on verifying system functionality, applying updates, and building foundational Linux administration skills before installing Wazuh.

### Linux Fundamentals
Linux administration relies heavily on the command line. Understanding navigation, file management, and package management is essential before deploying enterprise applications.

### Server Verification
Before installing any software, verify:
- Hostname
- Network connectivity
- Internet access
- Operating system status

This reduces troubleshooting later.

### Package Management
Ubuntu uses the APT package manager.

Important commands:
```bash
sudo apt update
sudo apt upgrade
```

These should always be performed before installing production software.

### VMware Snapshots
Snapshots provide an easy rollback point before major configuration changes. Creating snapshots before software installation greatly reduces recovery time if something goes wrong.

### Professional Workflow
Every milestone should include:
- Documentation
- Screenshots
- Lessons Learned
- Git commit
- VMware snapshot

Documenting throughout the project produces a much higher quality portfolio than documenting everything at the end.

## Phase 3 — Wazuh Installation
Focused on deploying the core Wazuh platform and verifying successful operation.

- Learned the Wazuh architecture.
- Installed Wazuh Manager, Indexer, and Dashboard.
- Verified services with `systemctl`.
- Troubleshot installer download issues.
- Reset the Wazuh administrator password.
- Successfully logged into the dashboard.

## Phase 4 — Agent Deployment
This milestone provided hands-on experience deploying and managing a Windows endpoint within a Wazuh SIEM environment. I learned how endpoint agents serve as the primary source of security telemetry and how proper agent configuration is essential for effective monitoring and threat detection.

### Key Takeaways
- Learned how to install and configure the Wazuh Windows Agent.
- Successfully connected a Windows endpoint to the Wazuh Manager.
- Verified secure communication between the endpoint and the SIEM platform.
- Confirmed the Windows endpoint was successfully registered and displayed as **Active** in the Wazuh Dashboard.
- Generated Windows Security events to validate log collection.
- Successfully detected Windows Event ID `4625` (Failed Logon) within the Wazuh Dashboard.
- Gained experience validating endpoint connectivity and troubleshooting agent communication.

### Professional Skills Developed
- Endpoint Security Monitoring
- Wazuh Agent Deployment
- Windows Event Log Analysis
- SIEM Administration
- Security Event Validation
- Windows System Administration
- Log Collection and Monitoring
- Endpoint Troubleshooting

### Reflection
This milestone demonstrated how endpoint agents provide the visibility required for effective security monitoring. Successfully deploying the Windows agent and validating Windows Security event collection established the foundation for future detection, threat hunting, and incident response activities. It also reinforced the importance of verifying communication between endpoints and the SIEM before implementing advanced security monitoring features such as File Integrity Monitoring and malware detection.

## Phase 6 — Detection and Monitoring
During this milestone, I gained a deeper understanding of how security events travel through the Wazuh SIEM architecture. Although File Integrity Monitoring (FIM) was correctly detecting file changes on the Windows endpoint, the alerts initially did not appear in the Wazuh Dashboard. This required troubleshooting the entire ingestion pipeline rather than assuming the issue was with the endpoint.

### Key Takeaways
- Learned how to configure File Integrity Monitoring (FIM) on a Windows endpoint.
- Gained experience generating and validating file creation, modification, and deletion events.
- Confirmed that Wazuh stores alerts in `/var/ossec/logs/alerts/alerts.json` before they are forwarded to the Indexer.
- Learned how Filebeat forwards alerts from the Wazuh Manager to the Wazuh Indexer.
- Verified the health of the Wazuh Indexer using OpenSearch API commands.
- Resolved an indexing issue by loading the Filebeat index template and restarting Filebeat.
- Confirmed successful creation of the `wazuh-alerts-*` index.
- Validated end-to-end telemetry from the Windows endpoint through the Wazuh Manager, Filebeat, Indexer, and Dashboard.

### Professional Skills Developed
- SIEM Administration
- Linux System Administration
- Windows Endpoint Monitoring
- File Integrity Monitoring (FIM)
- Filebeat Troubleshooting
- OpenSearch Index Management
- Log Ingestion Validation
- Security Event Analysis
- Root Cause Analysis
- Systematic Troubleshooting

### Reflection
This milestone reinforced the importance of validating every layer of a SIEM deployment. Rather than focusing on a single component, I learned to systematically verify the endpoint, manager, log files, Filebeat, Indexer, and Dashboard until the root cause was identified. This structured troubleshooting approach mirrors the methodology used by SOC Analysts and Security Engineers in production environments.
