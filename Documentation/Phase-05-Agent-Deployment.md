# Phase 05 – Windows Agent Deployment

## Objective

The objective of this phase was to deploy the Wazuh Windows Agent, establish communication with the Wazuh Manager, and validate endpoint telemetry by collecting Windows Security events.

---

# Lab Environment

**Wazuh Manager**
- Ubuntu Server
- Hostname: wazuh-server01

**Endpoint**
- Windows 10
- Agent Name: WIN10-JEREMY

**Hypervisor**
- VMware Workstation Pro

---

# Tasks Completed

## 1. Installed the Wazuh Windows Agent

Downloaded and installed the Wazuh Windows Agent on the Windows 10 virtual machine.

Configured the agent with:

- Wazuh Manager IP Address
- Agent Name: WIN10-JEREMY

---

## 2. Started the Agent Service

Verified the Wazuh Agent service was installed and running successfully.

Confirmed communication between the Windows endpoint and the Wazuh Manager.

---

## 3. Verified Agent Registration

Logged into the Wazuh Dashboard and confirmed the Windows endpoint appeared as an active agent.

Verified:

- Agent Status: Active
- Agent Name: WIN10-JEREMY
- Operating System: Windows 10

---

## 4. Validated Windows Event Collection

Generated Windows Security events to verify log collection.

Successfully confirmed that Windows Event ID **4625 (Failed Logon)** was collected and forwarded to the Wazuh Manager.

---

## 5. Confirmed End-to-End Telemetry

Validated that Windows Security events successfully traveled through the Wazuh monitoring pipeline.

Confirmed:

- Windows Endpoint
- Wazuh Agent
- Wazuh Manager
- Wazuh Dashboard

All components communicated successfully.

---

# Skills Demonstrated

- Endpoint Security Monitoring
- Windows Agent Deployment
- Windows Event Log Collection
- SIEM Administration
- Windows Security Monitoring
- Endpoint Registration
- Security Event Validation
- Linux Administration

---

# Outcome

Successfully deployed and configured the Wazuh Windows Agent.

Verified secure communication between the Windows endpoint and the Wazuh Manager and confirmed successful ingestion of Windows Security events into the Wazuh Dashboard.

This milestone established the endpoint monitoring foundation required for advanced detection capabilities, including File Integrity Monitoring (FIM), malware detection, and threat hunting.

---

# Portfolio Value

This phase demonstrates the ability to:

- Deploy and manage security monitoring agents
- Configure endpoint communication with a SIEM
- Validate Windows Security event collection
- Troubleshoot endpoint connectivity
- Verify end-to-end telemetry
- Prepare an enterprise endpoint for continuous security monitoring

---

# Screenshots

- Windows Agent Installation
- Wazuh Agent Service Running
- Agent Registration in Wazuh Dashboard
- Active Agent Status
- Windows Event ID 4625 Detection
- Dashboard Validation