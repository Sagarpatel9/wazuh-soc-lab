# Day 1 – Troubleshooting

## 1. External IP Stability

Observation:
The VM was initially assigned an ephemeral external IP address.

Impact:
If the instance were stopped and restarted, the IP address would change, breaking dashboard access.

Resolution:
Promoted the external IP to a static IP:

VPC Network → IP Addresses → Promote to static IP address

Result:
Stable and persistent dashboard access.

---

## 2. Firewall Rule Verification

During deployment, firewall rules were reviewed to ensure required ports were accessible.

Verified required ports:
- 443 (HTTPS – Dashboard)
- 1514 (Agent communication)
- 1515 (Agent registration)
- 55000 (Wazuh API)

No misconfigurations were identified after validation.

---

## 3. Service Health Check

After installation, services were manually verified:

sudo systemctl status wazuh-manager  
sudo systemctl status wazuh-dashboard  
sudo systemctl status opensearch  

All services were confirmed operational.

No critical installation errors were encountered during Day 1 deployment.
