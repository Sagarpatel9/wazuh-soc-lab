# Day 6 – Pattern Analysis

## Objective

Analyze repeated authentication failure events to identify brute force attack patterns and differentiate between normal and suspicious login behavior.

---

## Background

During Day 5, multiple failed login attempts were generated on a Windows endpoint using incorrect credentials.

These events were recorded as:

- **Windows Event ID:** 4625 (Failed logon)
- **Wazuh Rule ID:** 60122
- **Alert Category:** authentication_failed

Individually, these alerts represent normal failed login activity. However, when analyzed collectively, they may indicate malicious behavior.

---

## Observed Pattern

Analysis of Wazuh alerts revealed the following:

- Multiple failed login attempts were generated
- All attempts targeted the same account (`sega`)
- Events occurred within a short time window (seconds)
- Each event corresponded to Event ID 4625

This behavior indicates a repeated authentication failure pattern rather than isolated login errors.

---

## Pattern Indicators of Brute Force

The following characteristics were identified:

- **Repetition:** Multiple failed login attempts
- **Consistency:** Same user account targeted
- **Timing:** Events occurred within seconds
- **Failure Type:** Incorrect password attempts

These indicators align with common brute force attack behavior.

---

## Problem Identified

Wazuh generated separate alerts for each failed login attempt:

- Each Event ID 4625 produced an individual alert (Rule 60122)
- No correlation between related events
- Resulted in alert noise and lack of context

This makes it difficult for analysts to quickly identify attack patterns.

---

## SOC Analysis

From a SOC perspective:

- A single failed login is typically benign
- Multiple failed logins within a short timeframe indicate suspicious activity
- Repeated attempts against the same account suggest credential guessing

This pattern is consistent with a brute force attack.

---

## Detection Gap

The default Wazuh configuration detects individual failed logins but does not correlate them into a single high-confidence alert.

This creates a gap where:

- Analysts must manually identify patterns
- Alert fatigue may occur due to multiple low-level alerts

---

## Conclusion

The analysis confirms that repeated failed login attempts form a brute force attack pattern.

To improve detection, event correlation is required to:

- Group related failed login events
- Reduce alert noise
- Generate a single high-confidence alert

This leads to the development of a custom detection rule in the next phase.
