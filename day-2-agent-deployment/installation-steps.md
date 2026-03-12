# Day 2 – Windows Endpoint Agent Deployment

## Objective
Deploy a Windows endpoint in Google Cloud and connect it to the Wazuh manager to begin collecting endpoint security logs.

---

## Step 1 – Create Windows Endpoint VM

A Windows Server VM was created in Google Cloud to simulate an enterprise endpoint.

Configuration used:

- **Operating System:** Microsoft Windows Server 2025 Datacenter  
- **Region:** us-central1  
- **Machine type:** e2-standard-2  
- **External IP:** Used for RDP access  
- **Internal IP:** Used for communication with Wazuh manager  

---

## Step 2 – Configure RDP Access

A firewall rule was created to allow Remote Desktop connections.

Allowed port:

TCP 3389

Steps:

1. Created firewall rule allowing TCP 3389
2. Generated Windows password in Google Cloud
3. Connected using Remote Desktop

---

## Step 3 – Configure Firewall for Wazuh Agent

A firewall rule was created to allow the Windows endpoint to communicate with the Wazuh manager.

Allowed ports:

TCP 1514
TCP 1515

Source range:

10.128.0.0/20

This allows internal communication between the endpoint and manager inside the VPC network.

---

## Step 4 – Deploy Wazuh Agent

From the Wazuh dashboard:

Deploy new agent → Windows


Selected:

- **Package:** MSI 32/64 bit
- **Server address:** 10.128.0.2
- **Agent name:** user1
- **Agent group:** default

The **internal IP** of the Wazuh manager was used because both machines are in the same network.

---

## Step 5 – Install Agent via PowerShell

Executed the installation command provided by Wazuh:

```powershell
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.7.5-1.msi -OutFile $env:tmp\wazuh-agent
msiexec.exe /i $env:tmp\wazuh-agent /q WAZUH_MANAGER='10.128.0.2' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='user1' WAZUH_REGISTRATION_SERVER='10.128.0.2'
```

## Step 6 – Start and Verify the Wazuh Agent Service

After the installation completes, the Wazuh agent service must be running so the endpoint can communicate with the Wazuh manager.

Open **PowerShell as Administrator** and start the service:

```powershell
NET START WazuhSvc
```

If the command succeeds, PowerShell will return:

The Wazuh service is starting.
The Wazuh service was started successfully.

Next, verify the service status:

```Get-Service WazuhSvc```

Expected output:

Status   Name       DisplayName
------   ----       -----------
Running  WazuhSvc   Wazuh

When the service status shows Running, the agent is active and able to communicate with the Wazuh manager.

At this point the Windows endpoint should appear in the Wazuh dashboard under:

Agents → Active

