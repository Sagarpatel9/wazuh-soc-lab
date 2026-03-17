# Day 4 – Attack Simulation

## Objective
The goal of this phase was to simulate attacker behavior on a Windows endpoint in order to validate the custom Wazuh detection rule.

---

## Attack Scenario
After gaining access to a system, attackers commonly perform discovery activities to understand the environment.

One common technique is **process discovery**, where attackers list running processes to identify:
- security tools  
- privileged applications  
- useful targets for further actions  

---

## Simulated Attack

### Command Executed
```powershell
powershell -nop -c "Get-Process"
```

## Why This Command Matters

This command:
- launches PowerShell  
- uses `-nop` (no profile) to avoid loading user configurations  
- executes `Get-Process`  

This mimics realistic attacker behavior where PowerShell is executed with flags to reduce noise or evade detection.

---

## MITRE ATT&CK Mapping

- **Technique:** T1057  
- **Name:** Process Discovery  

---

## Detection Flow

1. PowerShell command executed on Windows endpoint  
2. Windows logs the activity  
3. Wazuh agent forwards the event  
4. Built-in rule `91815` detects PowerShell activity  
5. Custom rule `100002` triggers  
6. Alert appears in Wazuh dashboard  

---

## Observed Behavior

The execution of the PowerShell command successfully generated an alert in Wazuh through the custom rule.

This confirms that:
- log ingestion is working  
- detection logic is functioning  
- alerts are properly generated  

---

## Outcome

The attack simulation successfully validated the custom detection rule and demonstrated how attacker behavior can be simulated and detected in a SOC environment.
