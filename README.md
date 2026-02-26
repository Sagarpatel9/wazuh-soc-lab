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
- Agents: Not yet connected (Next Phase)  

---

## 📂 Project Structure

wazuh-soc-lab/
├── README.md
└── day-1-deployment/
    ├── architecture.md
    ├── installation-steps.md
    ├── initial-validation.md
    ├── troubleshooting.md
    └── screenshots/

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

Phase 2 will focus on:

- Endpoint Agent Deployment  
- Log Ingestion  
- Alert Generation  
- SOC Workflow Simulation  

---

## 🎯 Purpose of This Lab

This lab is part of a structured effort to build hands-on experience in:

- SOC Analyst (Level 1)  
- Blue Team Operations  
- SIEM Management  
- Incident Detection & Analysis  
