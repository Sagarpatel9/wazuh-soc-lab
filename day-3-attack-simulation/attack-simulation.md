# Day 3 – Attack Simulation

## Objective

The goal of Day 3 was to simulate common attacker behaviors on a monitored Windows endpoint and observe how the Wazuh SIEM detects and alerts on suspicious activity.

This phase demonstrates how a Security Operations Center (SOC) identifies potential security incidents using endpoint log monitoring and detection rules.

---

## Attack Scenario Overview

Three attack scenarios were simulated on the Windows endpoint:

1. User account creation
2. Privilege escalation
3. Failed login attempts

Each action generated Windows Security Event Logs that were collected by the Wazuh agent and analyzed by the Wazuh manager.

---

## Attack 1 – User Account Creation

### Command Executed

```bash
net user attacker Password123! /add
```

Description
This command creates a new local user account named attacker on the Windows system.

Attackers may create new accounts to maintain persistent access to a compromised machine.

Generated Windows Event  
Event ID: 4720  
Meaning: A user account was created.  

## Attack 2 – Privilege Escalation

### Command Executed
```bash
net localgroup administrators attacker /add
```

Description
This command adds the attacker user to the Administrators group, granting elevated privileges.

Generated Windows Event  
Event ID: 4732  
Meaning: A member was added to a security-enabled local group.  

This type of activity may indicate an attacker attempting to gain administrative control over a system.

## Attack 3 – Failed Login Attempts

### Simulation Method
Multiple incorrect login attempts were performed on the Windows endpoint.

Generated Windows Event  
Event ID: 4625  
Meaning: An account failed to log on.  
Repeated authentication failures may indicate a brute-force attempt to guess valid credentials.  

Summary  
These simulated attacks generated Windows Security Event Logs which were forwarded to the Wazuh manager.

The events were analyzed by Wazuh detection rules and resulted in security alerts that were investigated using the Wazuh dashboard.
