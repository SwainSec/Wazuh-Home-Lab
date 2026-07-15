# Troubleshooting Guide

## Issue 1 – File Integrity Monitoring (FIM) Alerts Not Appearing in the Wazuh Dashboard

### Problem
After configuring File Integrity Monitoring (FIM) on the Windows endpoint, file creation and deletion events were successfully generated. However, the alerts did not initially appear in the Wazuh Dashboard Discover page.

### Symptoms
- Windows Agent reported as **Active**.
- File Integrity Monitoring service was running.
- File changes were detected on the Windows endpoint.
- Alerts were written to:
```
/var/ossec/logs/alerts/alerts.json
```
- No FIM events were visible within the Wazuh Dashboard.

### Troubleshooting Process

**Step 1 — Verified the Windows Agent status.**
*Result:* Agent online, endpoint communicating successfully.

**Step 2 — Verified File Integrity Monitoring configuration.**
Confirmed real-time monitoring enabled and the custom directory `C:\FIM-Test` was being monitored.

**Step 3 — Generated multiple test events.**
Created, modified, and deleted files. Confirmed that Syscheck rules were generated.

**Step 4 — Verified alerts within the Wazuh Manager.**
```bash
sudo grep -i "fim-test" /var/ossec/logs/alerts/alerts.json
```
*Result:* File Integrity Monitoring alerts were successfully written to `alerts.json`.

**Step 5 — Verified Wazuh Indexer health.**
```bash
curl -k -u admin https://localhost:9200/_cluster/health?pretty
```
*Result:* Cluster health `GREEN`.

**Step 6 — Verified Filebeat.**
```bash
sudo systemctl status filebeat
sudo filebeat test output
```
*Result:* Filebeat running, output connection successful.

**Step 7 — Verified OpenSearch indices.**
Initially, no `wazuh-alerts-*` index was present.

### Root Cause
The Filebeat index template had not been loaded into the Wazuh Indexer. Although alerts were successfully generated and stored in `alerts.json`, they could not be indexed until the required template was installed.

### Resolution
Executed:
```bash
sudo filebeat setup -e
```
Restarted Filebeat:
```bash
sudo systemctl restart filebeat
```
Verified:
- `wazuh-alerts-*` index created
- Alerts successfully searchable within the Wazuh Dashboard
- End-to-end log ingestion restored

### Lessons Learned
Always validate every component of the SIEM pipeline individually:
1. Endpoint
2. Wazuh Agent
3. Wazuh Manager
4. alerts.json
5. Filebeat
6. Wazuh Indexer
7. Wazuh Dashboard

Systematic troubleshooting significantly reduces time spent diagnosing complex SIEM issues and helps isolate the root cause more efficiently.