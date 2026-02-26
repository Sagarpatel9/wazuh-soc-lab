# Day 1 – Architecture Overview

## Objective
Deploy a centralized Wazuh SIEM manager in Google Cloud to simulate a Security Operations Center (SOC) environment.

## Environment Components

- Google Cloud VM (Ubuntu 22.04 LTS)
- Wazuh Manager
- Wazuh Dashboard (OpenSearch-based)
- Public HTTPS Access (Port 443)

## Network Layout

Internet
   ↓
GCP External IP
   ↓
Wazuh Manager VM

## Security Configuration

- SSH restricted to authorized IP
- HTTPS enabled for dashboard access
- Required Wazuh ports configured (1514, 1515, 55000, 443)
- Principle of least privilege applied to firewall rules

## Purpose of This Phase

This phase establishes the centralized SIEM infrastructure.
Endpoint agents and detection engineering will be implemented in later phases.
