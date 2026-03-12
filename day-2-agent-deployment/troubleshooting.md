# Day 2 – Troubleshooting

## Issue 1 – Local Windows VM Networking Failure

Initial attempts were made to deploy the Windows endpoint locally using a virtualization environment.

### Problem
The Windows VM failed to detect the network adapter.

Observed behavior:
- Ethernet controller not detected
- Missing network drivers
- Endpoint could not communicate with the Wazuh manager

### Cause
The virtual machine networking drivers were not compatible with the Windows ARM environment.

### Resolution
The Windows endpoint was deployed in **Google Cloud Compute Engine** instead of running locally.

Advantages:
- Stable networking
- Easier communication with the Wazuh manager
- Better performance

---

## Issue 2 – Agent Status Showing "Never Connected"

After installing the Wazuh agent, the dashboard initially showed:

Never connected

### Cause
The Wazuh service had not started after installation.

### Resolution

Start the agent service manually:

```powershell
NET START WazuhSvc
```

Verify the service status:

Get-Service WazuhSvc

Expected output:

Status   Name       DisplayName
------   ----       -----------
Running  WazuhSvc   Wazuh

After starting the service, the agent status changed to Active in the Wazuh dashboard.

## Issue 3 – Firewall Communication Blocked

The Windows endpoint could not communicate with the Wazuh manager until firewall rules were configured.

Required Ports
Port	Protocol	Purpose
1514	TCP	      Log forwarding
1515	TCP     	Agent registration

Firewall Rule

A firewall rule was created in Google Cloud allowing internal communication from:

10.128.0.0/20

After applying the rule, the agent successfully connected to the Wazuh manager.

### Lessons Learned:

Key checks when deploying Wazuh agents:

Confirm network connectivity between endpoint and manager

Verify firewall rules for required ports

Ensure the Wazuh agent service is running

Use the correct manager IP address

Using internal VPC networking simplifies communication between endpoints and the SIEM manager.
