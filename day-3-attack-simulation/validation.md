# Day 3 – Detection Validation

## Objective

The purpose of this phase was to verify that the simulated attacker activities generated security alerts within the Wazuh SIEM.

By validating the alerts produced by Wazuh, we confirm that the SIEM is successfully collecting logs, analyzing events, and detecting suspicious behavior on the monitored Windows endpoint.

---

## Validation Process

After performing the attack simulations, the Wazuh dashboard was used to confirm that security alerts were generated for each simulated attack.

The alerts were reviewed within the **Security Events** section of the Wazuh dashboard.

Key alert details validated during this process included:

- Event ID
- Alert description
- Source endpoint
- User account involved
- Alert severity level
- MITRE ATT&CK mapping

---

## Validation Results

The following alerts were successfully detected by Wazuh:

| Attack Simulation | Windows Event ID | Detection Status |
|---|---|---|
| User Account Creation | 4720 | Detected |
| Privilege Escalation | 4732 | Detected |
| Failed Login Attempts | 4625 | Detected |

These results confirm that Wazuh successfully detected the simulated attacker behaviors.

---

## Screenshot Evidence

### Agent Connection

The Windows endpoint agent is successfully connected to the Wazuh manager.

Screenshot:

screenshots/day3-agent-active.png

---

### User Account Creation Detection

Wazuh detected the creation of a new user account on the Windows endpoint.

Screenshot:

screenshots/day3-user-account-created-alert.png

---

### Privilege Escalation Detection

Wazuh detected a modification to the **Administrators group**, indicating privilege escalation activity.

Screenshot:

screenshots/day3-admin-group-change-detection.png

---

### Failed Login Attempt Detection

Multiple failed login attempts were detected and recorded as authentication failures.

Screenshot:

screenshots/day3-failed-login-detection.png

---

## Conclusion

The validation phase confirmed that the Wazuh SIEM successfully detected all simulated attack scenarios.

These detections demonstrate how a Security Operations Center can monitor endpoint activity and identify potential security threats using SIEM-based alerting and log analysis.
