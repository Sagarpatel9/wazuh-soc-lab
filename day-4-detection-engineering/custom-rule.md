# Day 4 – Detection Engineering (Custom Wazuh Rule)

## Objective
The goal of this phase was to create a custom Wazuh detection rule to identify suspicious PowerShell activity on a Windows endpoint.

This phase focuses on detection engineering by extending built-in Wazuh rules using rule chaining.

---

## Detection Use Case
After gaining access to a system, attackers commonly perform discovery activities to understand the environment.

One common technique is **process discovery**, where attackers list running processes to identify:
- security tools
- privileged applications
- useful targets for further actions

In this lab, this behavior was simulated using PowerShell.

**MITRE ATT&CK Mapping:**
- T1057 – Process Discovery

---

## Detection Strategy

A **rule chaining approach** was used.

- **Parent Rule:** `91815` (Wazuh built-in PowerShell detection)
- **Custom Rule:** `100002`

The custom rule triggers only after the parent rule detects PowerShell activity.

This demonstrates how analysts can extend existing SIEM detections instead of building rules from scratch.

---

## Rule File Location
```xml
/var/ossec/etc/rules/local_rules.xml
```
---

### Custom Rule

```
<rule id="100002" level="10">
  <if_sid>91815</if_sid>
  <description>Custom detection: PowerShell process discovery activity detected</description>
  <group>powershell_attack,powershell,</group>
</rule>
```
---

### Rule Breakdown

### `<if_sid>91815</if_sid>`
This ensures the custom rule only triggers if the built-in PowerShell rule has already matched.

---

### `<description>`
Defines how the alert appears in the Wazuh dashboard.

---

### `<group>`
Categorizes the alert under PowerShell-related activity.

---

## Why Rule Chaining Was Used

Rule chaining allows detection to build on existing Wazuh rules.

**Benefits:**
- reduces complexity  
- improves reliability  
- leverages built-in parsing  
- aligns with real SOC workflows  

---

## Expected Detection Flow

1. PowerShell command executed on Windows endpoint  
2. Windows logs the activity  
3. Wazuh agent forwards the event  
4. Built-in rule `91815` detects PowerShell activity  
5. Custom rule `100002` triggers  
6. Alert appears in Wazuh dashboard

### Outcome

The custom rule successfully generated alerts based on PowerShell activity and demonstrated how rule chaining can be used in Wazuh detection engineering.
