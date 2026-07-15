# Phase 04 – Wazuh Configuration

## Objective
The objective of this phase was to verify the successful deployment of the Wazuh platform by configuring and validating the Wazuh Dashboard, Manager, and Indexer. This phase ensured that all core services were operational and ready to receive endpoint telemetry.

## Lab Environment

**Host System**
- Windows 10 Pro
- VMware Workstation Pro

**Wazuh Server**
- Ubuntu Server
- Hostname: `wazuh-server01`

## Tasks Completed

### 1. Verified Wazuh Services
Confirmed that all core Wazuh services were running successfully.

**Verified services:**
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

**Validated service status using:**
```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

### 2. Accessed the Wazuh Dashboard
Opened the Wazuh Dashboard using a web browser. Successfully authenticated using the administrator account.

**Verified:**
- Dashboard accessibility
- Successful login
- User authentication
- Dashboard responsiveness

### 3. Verified Dashboard Functionality
Confirmed that all primary dashboard components loaded correctly.

**Verified:**
- Overview Dashboard
- Threat Hunting
- Agent Management
- Security Events
- System Health

Confirmed that the Dashboard communicated successfully with both the Wazuh Manager and Wazuh Indexer.

### 4. Validated Platform Health
Performed health checks to ensure the SIEM platform was fully operational before onboarding endpoints.

**Confirmed:**
- Manager service running
- Indexer service running
- Dashboard service running
- No critical service failures
- System ready for agent deployment

## Skills Demonstrated
- SIEM Administration
- Linux System Administration
- Wazuh Dashboard Administration
- Service Management
- OpenSearch Verification
- Security Platform Validation
- Web-Based SIEM Management
- Infrastructure Verification

## Outcome
Successfully validated the Wazuh deployment and confirmed that all core platform services were operating correctly. The Wazuh Dashboard was accessible, authenticated successfully, and communicated properly with the Manager and Indexer. The environment was fully prepared for endpoint onboarding in the next phase.

## Portfolio Value
This phase demonstrates the ability to:
- Verify a SIEM deployment
- Validate service health
- Troubleshoot enterprise security services
- Confirm communication between SIEM components
- Prepare a production-ready monitoring platform for endpoint integration

## Screenshots
- Wazuh Dashboard Login
- Wazuh Dashboard Home
- Wazuh Manager Service Status
- Wazuh Indexer Service Status
- Wazuh Dashboard Service Status
- Wazuh Overview Dashboard
