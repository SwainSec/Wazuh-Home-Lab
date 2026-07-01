# Phase 01 - Infrastructure Setup

## Objective
Build the virtual infrastructure required to host a Wazuh SIEM server.

## Completed
- Installed VMware Workstation Pro
- Verified CPU virtualization support
- Created Ubuntu Server virtual machine
- Allocated:
  - 8 GB RAM
  - 4 vCPUs
  - 100 GB virtual disk
- Configured NAT networking
- Installed Ubuntu Server 24.04 LTS
- Enabled OpenSSH Server
- Created server account
- Configured hostname:
  - wazuh-server01

## Design Decisions

### Network
- NAT networking
- DHCP addressing

**Reason:** Provides internet access while isolating the virtual machine from the home network.

### Storage
- Entire disk
- ext4 filesystem
- LVM disabled

**Rationale:** Simplifies administration and aligns with common Wazuh deployment guides.

### SSH
- OpenSSH installed
- Password authentication enabled

**Why:** Allows secure remote administration from the Windows host during initial setup. Password authentication was chosen for lab convenience in this phase; key-based authentication will be configured in a later phase to harden remote access.

## Outcome
Ubuntu Server installed successfully and ready for post-installation configuration.

## Next Steps
Proceed to Phase 02: install and configure the Wazuh Manager, Indexer, and Dashboard on the newly provisioned server.
