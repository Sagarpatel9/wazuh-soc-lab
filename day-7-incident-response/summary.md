# Incident Summary – Brute Force Attack Simulation

## 📌 Overview

This incident involved a simulated brute force attack on a Windows endpoint within a controlled SOC lab environment.

The attack consisted of multiple failed login attempts, which were successfully detected by a custom Wazuh rule designed to identify repeated authentication failures.

---

## 🎯 Objectives Achieved

- Simulated brute force attack behavior
- Generated Windows Security Event Logs (Event ID 4625)
- Detected attack using custom Wazuh rule (ID: 100003)
- Investigated alert using SIEM dashboard
- Performed full SOC incident response workflow

---

## 🔍 Key Observations

- Multiple failed login attempts occurred within a short timeframe
- Logon Type 2 (interactive login) was used
- Source IP address was localhost (127.0.0.1), confirming local simulation
- No successful login occurred during the attack
- The targeted account was **sega**

---

## 🛡 Detection Summary

- **Detection Method:** Rule-based correlation
- **Rule Trigger:** 5 failed login attempts within 60 seconds
- **Alert Level:** 10 (High Severity)
- **MITRE Technique:** T1110 – Brute Force
- **Tactic:** Credential Access

---

## ⚙️ SOC Workflow Demonstrated

This project demonstrated the complete SOC workflow:

1. Attack Simulation  
2. Log Collection  
3. Detection (SIEM Alert)  
4. Investigation  
5. Response  
6. Documentation  

---

## 🧠 Key Learnings

- Brute force attacks can be identified through log correlation
- SIEM tools like Wazuh are effective for real-time monitoring
- Custom detection rules improve visibility into attack patterns
- Structured investigation is critical for accurate analysis
- Documentation is essential for SOC operations

---

## 🚀 Final Outcome

The brute force attack simulation was successfully:

- Detected using Wazuh SIEM  
- Analyzed through log investigation  
- Contained in a controlled lab environment  
- Documented following SOC best practices  

This validates hands-on experience in:

- Security monitoring  
- Detection engineering  
- Incident investigation  
- SOC response workflows  
