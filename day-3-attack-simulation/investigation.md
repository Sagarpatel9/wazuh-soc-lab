# Day 3 – Alert Investigation

## Objective

After simulating attacker behavior on the Windows endpoint, the next step was to investigate the generated alerts in the Wazuh dashboard.

The purpose of this phase was to understand how Wazuh detects suspicious activity and how a Security Operations Center (SOC) analyst investigates security alerts.

---

## Wazuh Detection Workflow

When the simulated attacks were performed on the Windows endpoint, Windows generated security events that were written to the Windows Security Event Log.

The Wazuh agent installed on the endpoint continuously monitors these logs and forwards them to the Wazuh manager for analysis.

The detection pipeline follows this process:

Windows Endpoint  
↓  
Windows Security Event Logs  
↓  
Wazuh Agent (Log Collection)  
↓  
Wazuh Manager (Analysis Engine)  
↓  
Wazuh Detection Rules  
↓  
Security Alert Generated  

---

## Investigating Alerts in Wazuh Dashboard

The alerts generated during the attack simulation were analyzed in the **Wazuh Security Events dashboard**.

Key fields reviewed during the investigation included:

- Event ID
- Agent name
- Source endpoint
- User account involved
- Rule description
- Alert severity level
- MITRE ATT&CK technique mapping

These fields help SOC analysts determine whether the activity is suspicious or malicious.

---

## Investigation Example – User Account Creation

Generated Windows Event

Event ID: 4720  
Meaning: A user account was created  

Investigation Findings

A new user account named **attacker** was created on the Windows endpoint.

Security Risk

Unauthorized account creation can indicate persistence mechanisms used by attackers.

---

## Investigation Example – Privilege Escalation

Generated Windows Event

Event ID: 4732  
Meaning: A member was added to a security-enabled local group  

Investigation Findings

The **attacker** account was added to the **Administrators group**, granting elevated privileges.

Security Risk

Privilege escalation allows attackers to gain administrative control of a system.

---

## Investigation Example – Failed Login Attempts

Generated Windows Event

Event ID: 4625  
Meaning: An account failed to log on  

Investigation Findings

Multiple failed login attempts were detected on the Windows endpoint.

Security Risk

Repeated authentication failures may indicate brute-force attempts to guess user credentials.

---

## Conclusion

The investigation phase demonstrated how Wazuh SIEM detects suspicious activity using Windows security events and detection rules.

By analyzing event details such as event IDs, user accounts, and MITRE ATT&CK mappings, SOC analysts can identify potential security incidents and determine appropriate response actions.
