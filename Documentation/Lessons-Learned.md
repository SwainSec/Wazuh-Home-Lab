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