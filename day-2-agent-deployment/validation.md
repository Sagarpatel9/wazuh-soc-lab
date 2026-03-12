# Day 2 – Validation

## Objective
Verify that the Windows endpoint successfully connected to the Wazuh manager and is sending security logs.

---

## Agent Registration

After installing and starting the Wazuh agent service, the endpoint appeared in the Wazuh dashboard.

Navigation:

Agents → Dashboard

Agent information:

- **Agent Name:** user1
- **IP Address:** 10.128.0.3
- **Operating System:** Microsoft Windows Server 2025 Datacenter
- **Version:** 4.7.5
- **Status:** Active

When the agent status shows **Active**, it confirms successful communication with the Wazuh manager.

---

## Log Ingestion Verification

After the agent connected, Windows security events began appearing in the Wazuh dashboard.

Navigation:

Modules → Security Events

Examples of detected events:

- Windows agent started
- Windows logon success
- User account changes
- Domain group modifications
- Software protection service events

These events confirm that logs are being successfully collected and analyzed by the Wazuh SIEM.

---

## Dashboard Monitoring

The security events dashboard displayed:

- Alert activity graphs
- Authentication events
- Windows rule triggers
- MITRE ATT&CK mapped detections

This indicates that the endpoint logs are actively being processed by Wazuh.

---

## Result

The Windows endpoint is now fully integrated with the Wazuh SIEM and actively monitored for security events.
