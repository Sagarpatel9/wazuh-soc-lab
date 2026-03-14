# Day 3 – MITRE ATT&CK Mapping

## Objective

During the attack simulation phase, the detected security events were mapped to the MITRE ATT&CK framework.

MITRE ATT&CK is a globally recognized knowledge base that categorizes attacker techniques and tactics used during cyber attacks.

Mapping detections to MITRE ATT&CK helps security teams understand attacker behavior and prioritize incident response.

---

## Attack Mapping Overview

The simulated attacks generated Windows Security Events which were detected by Wazuh and mapped to MITRE ATT&CK techniques.

| Attack Simulation | Windows Event ID | MITRE Technique | MITRE Tactic |
|---|---|---|---|
| User Account Creation | 4720 | T1136 – Create Account | Persistence |
| Privilege Escalation (Admin Group Change) | 4732 | T1484 – Domain Policy Modification | Privilege Escalation |
| Failed Login Attempts | 4625 | T1110 – Brute Force | Credential Access |

---

## Technique Explanation

### T1136 – Create Account

Attackers may create new user accounts to maintain persistent access to a compromised system.

This behavior is commonly observed after initial system access has been achieved.

---

### T1484 – Domain Policy Modification

This technique involves modifying group memberships or domain policies to escalate privileges or evade security controls.

Adding a user to the **Administrators group** grants elevated privileges and may allow attackers to perform further malicious actions.

---

### T1110 – Brute Force

Brute force attacks involve repeated login attempts to guess valid credentials.

Multiple authentication failures may indicate an attacker attempting to gain unauthorized access to the system.

---

## Importance of MITRE Mapping

Mapping alerts to MITRE ATT&CK techniques helps SOC analysts:

- Understand the stage of the attack
- Classify attacker behavior
- Improve threat detection strategies
- Standardize incident reporting

This approach allows security teams to analyze attacks using a common framework used across the cybersecurity industry.
