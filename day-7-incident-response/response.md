# Incident Response – Brute Force Attack

## 🎯 Response Objective

The objective of this response was to contain and mitigate a detected brute force attack targeting a local user account.

---

## 🚨 Immediate Actions Taken

- Identified repeated failed login attempts (Event ID 4625)
- Confirmed brute force behavior using custom Wazuh rule (ID: 100003)
- Verified source of activity (localhost – lab simulation)
- Determined no external threat actor involvement

---

## 🔒 Containment Measures

- Stopped further login attempts by ending testing activity
- Ensured no successful login occurred during the attack
- Verified system remained secure and uncompromised

---

## 🛠 Mitigation Steps

- Reviewed authentication logs for anomalies
- Validated Wazuh detection rule accuracy
- Ensured alert thresholds were correctly configured
- Confirmed SIEM visibility into failed login events

---

## 🔁 Recovery Actions

- Restored normal login activity
- Verified system stability after attack simulation
- Ensured no account lockout or system misconfiguration persisted

---

## 🧠 Lessons Learned

- Brute force attacks can be effectively detected using event correlation
- Threshold-based detection improves alert accuracy
- Monitoring failed login patterns is critical for early detection
- Even local attacks generate valuable detection signals

---

## 🚀 Recommendations

- Implement account lockout policies after multiple failed attempts
- Enable alerting for abnormal login patterns
- Monitor authentication logs continuously
- Consider multi-factor authentication (MFA) for added security

---

## ✅ Conclusion

The brute force attack simulation was successfully detected, analyzed, and contained.

The response process validated:

- Detection capability of Wazuh SIEM
- Effectiveness of custom rule implementation
- Proper SOC response workflow execution
