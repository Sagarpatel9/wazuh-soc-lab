# Day 1 – Initial Validation

## Objective
Confirm that the Wazuh SIEM deployment in Google Cloud is operational and accessible after installation.

---

## 1. Service Status Verification

Verified that all core services are running:

sudo systemctl status wazuh-manager  
sudo systemctl status wazuh-dashboard  
sudo systemctl status opensearch  

Result:
- All services show: active (running)
- No startup failures observed
- No critical errors in logs

---

## 2. Dashboard Access Verification

Accessed the Wazuh dashboard via:

https://34.72.244.154

Validation confirmed:
- HTTPS connection successful
- Login successful
- Dashboard loads without rendering issues
- No cluster errors displayed

---

## 3. OpenSearch Cluster Health

Checked cluster health from dashboard:

- Cluster status: Green
- No node failures
- No index warnings
- System resources within normal limits

---

## 4. Deployment State Summary

Current environment status:

- Wazuh Manager deployed successfully
- Static external IP configured
- Dashboard externally accessible
- No agents connected yet (expected at this phase)

---

## Outcome

The centralized SIEM infrastructure has been successfully deployed and validated. 

The environment is prepared for endpoint agent integration in the next phase.
