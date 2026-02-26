# Day 1 – Architecture Overview

## Objective
Deploy a cloud-based SOC lab using Wazuh on Google Cloud Platform (GCP).

## Environment Components

- Wazuh Manager (Ubuntu Server)
- Wazuh Dashboard
- Linux Agent
- Google Cloud VM Infrastructure
- Firewall Rules (Port 1514, 1515, 55000, 443)

## Network Layout

Internet
   ↓
GCP External IP
   ↓
Wazuh Manager VM
   ↓
Wazuh Agents

## Security Design Decisions

- SSH restricted to my public IP
- HTTPS enabled for dashboard
- Separate VM for agent testing
- Principle of least privilege applied to firewall rules

## Why This Architecture?

This design simulates a real-world SOC setup where:
- Centralized log aggregation occurs on a manager
- Endpoints forward logs securely
- Alerts are monitored via a dashboard
