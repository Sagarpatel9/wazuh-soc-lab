# Wazuh SOC Lab – Google Cloud Deployment

## 📌 Project Overview

This project documents the step-by-step deployment of a cloud-based Security Operations Center (SOC) lab using Wazuh SIEM on Google Cloud Platform.

The goal of this lab is to simulate real-world SOC infrastructure, including centralized log management, monitoring, and detection engineering.

---

# 🏗️ Phase 1 – SIEM Infrastructure Deployment (Completed)

## Objectives

- Deploy Wazuh Manager in Google Cloud
- Configure secure external access
- Convert ephemeral IP to static
- Validate service health
- Document deployment process

---

## 🖥️ Environment Details

- Cloud Provider: Google Cloud Platform  
- Operating System: Ubuntu 22.04 LTS  
- SIEM Platform: Wazuh (All-in-One Installation)  
- Static External IP: Configured  
- HTTPS Dashboard Access: Enabled  

---

## ✅ Validation Results

- Wazuh Manager: Running  
- Wazuh Dashboard: Accessible via HTTPS  
- OpenSearch Cluster: Green  
- Static IP: In Use  
- Agents: Windows endpoint successfully connected  

---
🏗️ Phase 2 – Endpoint Agent Deployment (Completed)

Objectives
Deploy Windows endpoint VM
Install Wazuh agent
Configure firewall rules for agent communication
Verify endpoint log ingestion

🖥️ Endpoint Environment
Operating System: Microsoft Windows Server 2025 Datacenter
Agent Version: Wazuh Agent 4.7.5
Manager Internal IP: 10.128.0.2
Endpoint Internal IP: 10.128.0.3

🔐 Firewall Configuration

Allowed ports:

1514 TCP – Log forwarding  
1515 TCP – Agent registration  

Source range:

10.128.0.0/20

✅ Validation Results

Agent status: Active  
Windows logs successfully ingested into Wazuh  
Security events visible in dashboard  
Endpoint communication verified

---

## 📂 Project Structure

```
wazuh-soc-lab/
├── README.md
└── day-1-deployment/
    ├── architecture.md
    ├── installation-steps.md
    ├── initial-validation.md
    ├── troubleshooting.md
    └── screenshots/
└── day-2-agent-deployment/
    ├── installation-steps.md
    ├── validation.md
    ├── troubleshooting.md
    └── screenshots/
```

---

# 🛠️ Skills Demonstrated

- Cloud Infrastructure Deployment  
- Linux Server Administration  
- SIEM Installation & Configuration  
- Network & Firewall Configuration  
- Service Validation & Monitoring  
- Technical Documentation  

---

# 🚀 Next Phase


Phase 3 will focus on:

Attack Simulation
Alert Generation
Threat Detection
SOC Investigation Workflow
MITRE ATT&CK Mapping

---

## 🎯 Purpose of This Lab

This lab is part of a structured effort to build hands-on experience in:

- SOC Analyst (Level 1)  
- Blue Team Operations  
- SIEM Management  
- Incident Detection & Analysis  


