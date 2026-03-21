# Day 6 – Custom Detection Rule

## Objective

Develop a custom Wazuh detection rule to identify brute force attacks by correlating multiple failed login events within a defined time window.

---

## Detection Strategy

Based on the pattern analysis from Day 5:

- Multiple failed login attempts were observed
- All attempts targeted the same account (`sega`)
- Events occurred within a short time window

This behavior indicates a brute force attack.

---

## Detection Logic

The following logic was defined:

- Monitor failed login events (Event ID 4625)
- Identify repeated occurrences of failed logins
- Trigger an alert when:
  - **5 or more failed login attempts**
  - occur within **60 seconds**

This approach reduces noise and highlights suspicious behavior.

---

## Custom Rule Configuration

The following rule was added to the Wazuh local rules file:

```xml
<rule id="100003" level="10" frequency="5" timeframe="60">
  <if_matched_sid>60122</if_matched_sid>
  <description>Custom detection: Possible brute force attack detected (multiple failed Windows logins)</description>
  <group>bruteforce,windows,authentication_failed,</group>
  <mitre>
    <id>T1110</id>
  </mitre>
</rule>
```

---

## Rule Explanation

- **if_matched_sid: 60122**
  - References the Wazuh rule for failed login events (Event ID 4625)

- **frequency: 5**
  - Triggers detection after 5 matching events

- **timeframe: 60**
  - Events must occur within 60 seconds

- **level: 10**
  - High severity alert indicating potential attack

- **group**
  - Categorizes the alert as brute force and authentication failure

- **MITRE Mapping**
  - T1110 – Brute Force

---

## Detection Outcome

After implementing the rule:

- Multiple failed login events are correlated
- Instead of multiple alerts, a single high-confidence alert is generated
- Alert noise is significantly reduced
- Detection accuracy is improved

---

## Analyst Insight

This custom rule demonstrates how event correlation can be used to identify attack patterns and improve detection quality in a SIEM environment.

Rather than reacting to individual events, analysts can focus on meaningful alerts that represent real threats.
