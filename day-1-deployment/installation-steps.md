# Day 1 – Installation Steps

## Step 1: Create Google Cloud VM

- OS: Ubuntu 22.04 LTS
- Machine type: e2-medium
- Disk: 20GB
- Allow HTTPS traffic
- Configure firewall rules for required ports

## Step 2: Convert External IP to Static

By default, Google Cloud assigns an ephemeral external IP.
To ensure consistent access to the Wazuh dashboard, the external IP was promoted to static.

- Navigate to VPC Network → IP Addresses
- Select the VM external IP
- Click "Promote to static IP address"
- Assign a name and reserve

This prevents the IP from changing when the VM is stopped.

## Step 3: Install Wazuh All-in-One

curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a

This installs:
- Wazuh Manager
- OpenSearch
- Wazuh Dashboard

## Step 4: Access the Dashboard

https://34.72.244.154

Login using credentials generated during installation.

## Step 5: Verify Services

sudo systemctl status wazuh-manager
sudo systemctl status wazuh-dashboard
sudo systemctl status opensearch
