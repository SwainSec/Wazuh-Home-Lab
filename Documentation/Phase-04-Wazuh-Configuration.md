# Phase 04 – Agent Deployment

## Objective
Validate the Wazuh platform, deploy a Windows endpoint, and verify successful event collection.

## Tasks Completed
- Verified Wazuh Manager service
- Verified Wazuh Indexer service
- Verified Wazuh Dashboard service
- Accessed the Wazuh Dashboard
- Explored the Threat Hunting interface
- Deployed the Windows Wazuh Agent
- Registered the Windows endpoint
- Verified active communication
- Generated Windows failed logon events
- Verified Event ID 4625 detection

## Results
The Windows endpoint (`WIN10-JEREMY`) successfully enrolled with the Wazuh Manager.

The Wazuh Dashboard confirmed:
- Active endpoint communication
- Windows event collection
- Threat Hunting functionality
- Authentication failure detection

Generated failed Windows logons successfully produced Windows Event ID 4625 alerts within Wazuh.

## Skills Demonstrated
- Wazuh Administration
- Windows Endpoint Monitoring
- SIEM Event Collection
- Threat Hunting
- Windows Event Log Analysis
- Security Monitoring
- Linux Administration

## Outcome
**Status:** ✅ Complete

The Windows endpoint was successfully deployed, enrolled, and validated for event collection and authentication failure detection.

## Next Steps
Proceed to Phase 05: build and test custom detection rules for additional attack scenarios.