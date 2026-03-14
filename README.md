# Wazuh SOC Lab – Google Cloud Deployment

## 📌 Project Overview

This project documents the deployment of a **cloud-based Security Operations Center (SOC) lab** using **Wazuh SIEM on Google Cloud Platform**.

The lab simulates real-world SOC operations including:

- SIEM deployment
- Endpoint monitoring
- Security alert detection
- SOC investigation workflow
- MITRE ATT&CK mapping

---

# 🏗 Lab Phases

## Phase 1 – SIEM Infrastructure Deployment

Deploy Wazuh manager on Google Cloud and configure secure access.

Documentation:

```
day-1-deployment/
```

---

## Phase 2 – Endpoint Agent Deployment

Deploy a Windows endpoint and connect it to the Wazuh manager.

Documentation:

```
day-2-agent-deployment/
```

---

## Phase 3 – Attack Simulation & Detection

Simulate attacker behavior and investigate alerts using Wazuh SIEM.

Documentation:

```
day-3-attack-simulation/
```

---

# 📂 Project Structure

```
wazuh-soc-lab
│
├── README.md
│
├── day-1-deployment
│   ├── architecture.md
│   ├── installation-steps.md
│   ├── initial-validation.md
│   ├── troubleshooting.md
│   └── screenshots
│
├── day-2-agent-deployment
│   ├── installation-steps.md
│   ├── validation.md
│   ├── troubleshooting.md
│   └── screenshots
│
└── day-3-attack-simulation
    ├── attack-simulation.md
    ├── investigation.md
    ├── mitre-mapping.md
    ├── validation.md
    └── screenshots
```

---

# 🛠 Skills Demonstrated

- Cloud Infrastructure Deployment
- Linux Server Administration
- SIEM Installation & Configuration
- Endpoint Monitoring
- Security Event Analysis
- SOC Investigation Workflow
- MITRE ATT&CK Mapping
- Technical Documentation

---

# 🎯 Purpose of This Lab

This project was created to build hands-on experience relevant to:

- SOC Analyst (Level 1)
- Blue Team Operations
- SIEM Management
- Threat Detection & Incident Investigation
