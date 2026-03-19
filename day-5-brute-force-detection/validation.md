# Day 5 – Validation

## Validation Objective
Verify that repeated failed login attempts are correctly logged by Windows and detected by Wazuh SIEM.

## Validation Steps

1. Simulated multiple failed login attempts against the local administrator account (`sega`)
2. Opened Event Viewer and filtered Security logs for Event ID 4625
3. Confirmed multiple failed logon events were generated within a short time window
4. Queried Wazuh dashboard for authentication failure alerts
5. Analyzed alert details including rule ID, logon type, and failure reason

---

## Observed Results

- **Event ID:** 4625 (Failed logon)
- **Target Account:** sega (local administrator account)
- **Log Source:** Windows Security Log
- **Logon Type:** 2 (Interactive)
- **Failure Reason:** Unknown user or bad password
- **Number of Attempts:** 5–10+
- **Time Window:** ~1 minute
- **Wazuh Rule ID:** 60122
- **Alert Level:** 5 (Medium)
- **Alert Category:** authentication_failed

---

## Evidence

### Event Viewer – Multiple Failed Logins (4625)
![Event Viewer Failed Logins](day-5-brute-force-detection/screenshots/eventviewer-4625-event-details.png)

---

### Wazuh Dashboard – Authentication Failure Pattern
![Wazuh Dashboard Pattern](screenshots/wazuh-dashboard-bruteforce-pattern.png)

---

### Wazuh Alert – Rule Metadata
![Wazuh Rule Metadata](screenshots/wazuh-alert-rule-metadata.png)

---

### Wazuh Alert – Raw Windows Event Message
![Wazuh Raw Event](screenshots/wazuh-alert-windows-message.png)

---

### Wazuh Alert – Parsed Fields
![Wazuh Parsed Fields](screenshots/wazuh-alert-parsed-fields.png)

---

## Result

Validation successful.

Repeated failed login attempts were:
- Successfully recorded by Windows (Event ID 4625)
- Forwarded by the Wazuh agent
- Detected and visualized in the Wazuh dashboard

---

## Analyst Notes

The observed pattern of multiple failed authentication attempts within a short time window is a strong indicator of brute force activity.

In real-world SOC environments, such patterns are critical for early detection of credential-based attacks and should trigger further investigation.

---

## Conclusion

This lab successfully demonstrated brute force attack detection using Wazuh SIEM. By simulating repeated failed login attempts against an existing Windows account, authentication failure events were generated, ingested, and analyzed effectively.

This exercise highlights the importance of monitoring authentication logs and correlating repeated failures to identify potential security threats.
