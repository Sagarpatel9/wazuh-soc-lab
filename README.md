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

## Phase 4 – Detection Engineering

Design and implement custom Wazuh detection rules to identify specific attacker behaviors using rule chaining.

Documentation:

```
day-4-detection-engineering/
```

---

## Phase 5 – Brute Force Attack Detection

Simulate brute force login attempts on a Windows endpoint and analyze repeated authentication failures using Wazuh SIEM.

This phase focuses on identifying patterns of failed logins (Event ID 4625), validating alert generation, and mapping the activity to MITRE ATT&CK.

Documentation:

```
day-5-brute-force-detection/
```

---

## Phase 6 – Detection Engineering & Event Correlation

Design and implement a custom Wazuh detection rule to identify brute force attacks by correlating multiple failed login events within a defined time window.

This phase focuses on reducing alert noise, improving detection accuracy, and applying SOC-level analysis to transform multiple low-level alerts into a single high-confidence detection.

Documentation:

```
day-6-detection-analysis/
```

---

## Phase 7 – Incident Response & Reporting

Perform a full SOC incident response workflow based on the detected brute force attack.

This phase focuses on:

- Investigating alerts in detail
- Analyzing event logs and metadata
- Building a timeline of attacker activity
- Performing incident response actions
- Creating a structured incident report

Documentation:

```
day-7-incident-response/
```

---

# 📂 Project Structure

```
wazuh-soc-lab
│
├── README.md
│
├── day-1-deployment
│ ├── architecture.md
│ ├── installation-steps.md
│ ├── initial-validation.md
│ ├── troubleshooting.md
│ └── screenshots
│
├── day-2-agent-deployment
│ ├── installation-steps.md
│ ├── validation.md
│ ├── troubleshooting.md
│ └── screenshots
│
├── day-3-attack-simulation
│ ├── attack-simulation.md
│ ├── investigation.md
│ ├── mitre-mapping.md
│ ├── validation.md
│ └── screenshots
│
├── day-4-detection-engineering
│ ├── custom-rule.md
│ ├── attack-simulation.md
│ ├── validation.md
│ └── screenshots
│
├── day-5-brute-force-detection
│ ├── attack-simulation.md
│ ├── validation.md
│ ├── mitre-mapping.md
│ └── screenshots
│
└── day-6-detection-analysis
├── pattern-analysis.md
├── custom-rule.md
├── validation.md
└── screenshots
├── day-7-incident-response
│   ├── investigation.md
│   ├── response.md
│   ├── summary.md
│   └── screenshots

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
- Detection Engineering
- Custom SIEM Rule Development (Wazuh)
- Brute Force Detection & Authentication Analysis (Event ID 4625)
- Event Correlation & Alert Reduction
- Brute Force Detection Engineering (Custom Wazuh Rules)
- Threshold-Based Detection Logic (Frequency & Timeframe)
- Incident Response & SOC Workflow Execution
- Security Incident Reporting & Documentation
- Alert Investigation & Threat Analysis
- Timeline-Based Event Analysis

---

# 🎯 Purpose of This Lab

This project was created to build hands-on experience relevant to:

- SOC Analyst (Level 1)
- Blue Team Operations
- SIEM Management
- Threat Detection & Incident Investigation
