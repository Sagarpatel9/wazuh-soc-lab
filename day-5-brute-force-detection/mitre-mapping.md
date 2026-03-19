# Day 5 – MITRE ATT&CK Mapping

## Detection Summary

A brute force attack simulation was performed by generating repeated failed login attempts against a Windows endpoint.

The activity was captured using Windows Security Event ID 4625 and detected by Wazuh SIEM as multiple authentication failure alerts.

---

## MITRE ATT&CK Technique

- **Technique ID:** T1110  
- **Technique Name:** Brute Force  

---

## Justification

Brute force attacks involve repeated attempts to gain access by guessing user credentials.

In this lab:

- Multiple failed login attempts were generated  
- The same account (`sega`) was targeted repeatedly  
- Attempts occurred within a short time window  
- All attempts resulted in authentication failures (Event ID 4625)  

These characteristics align with brute force attack behavior as defined in MITRE ATT&CK.

---

## Note on Wazuh Mapping

While Wazuh default rules mapped the activity to generic authentication-related techniques (such as valid account or account manipulation categories), these mappings are based on individual events.

Manual analysis of the repeated failed login pattern provides stronger evidence of brute force activity. Therefore, the behavior was mapped to:

- **T1110 – Brute Force**

---

## Relevant Telemetry

- Windows Security Event ID: **4625 (Failed logon)**  
- Target Account: **sega (local administrator account)**  
- Log Source: Windows Security Log  
- Failure Reason: Incorrect password  
- Logon Type: Interactive (Type 2)  
- Repeated authentication failures within a short timeframe  

---

## Detection Value

This detection is critical because:

- Brute force attacks are a common method of initial access  
- Repeated failed logins may indicate credential guessing or account abuse  
- Early detection helps prevent unauthorized access and account compromise  

---

## Analyst Takeaway

A single failed login attempt may be benign; however, multiple failed attempts against the same account within a short period strongly indicate suspicious or malicious behavior.

SOC analysts should correlate authentication failures over time to identify brute force activity and respond accordingly.
