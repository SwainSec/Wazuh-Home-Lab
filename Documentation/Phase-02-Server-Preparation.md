# Phase 02 - Server Preparation

## Objective
Prepare the Ubuntu Server for Wazuh installation by verifying system functionality, applying updates, installing VMware integration tools, and learning foundational Linux administration commands.

## Tasks Completed

### System Verification
- Logged into Ubuntu Server
- Verified server hostname
- Verified operating system information
- Confirmed VMware virtualization

**Command used:**
```bash
hostnamectl
```

### Network Verification
Verified the server received a valid IP address and confirmed internet connectivity.

**Commands used:**
```bash
ip addr
```
```bash
ping -c 4 google.com
```

### System Updates
Updated the Ubuntu package repository and installed the latest available updates.

**Commands used:**
```bash
sudo apt update
```
```bash
sudo apt upgrade -y
```

**Result:**
- System fully updated
- No pending security updates
- Kernel up to date

### VMware Integration
Verified Open VM Tools were installed and running correctly.

**Command:**
```bash
sudo apt install open-vm-tools -y
```

**Verification:**
```bash
systemctl status open-vm-tools
```

**Result:**
- Service active
- VMware integration working correctly

### Linux Fundamentals
Practiced the following commands:
- `pwd`
- `ls`
- `ls -la`
- `cd`
- `mkdir`
- `touch`
- `cp`
- `mv`
- `rm`
- `nano`
- `cat`

Created a practice directory and text file to reinforce Linux file management concepts.

### VMware Snapshot
Created snapshot: `Milestone-02-Server-Preparation`

**Purpose:** Provides a stable restore point before installing Wazuh.

## Outcome
Ubuntu Server is fully updated, verified, and ready for Wazuh installation.

## Next Steps
Proceed to Phase 03: install the Wazuh Manager, Indexer, and Dashboard on the prepared server.