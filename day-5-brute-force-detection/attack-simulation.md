# Day 5 – Brute Force Attack Simulation

## Objective
Simulate a brute force attack by generating repeated failed login attempts on a Windows endpoint and validate detection using Wazuh SIEM.

## Lab Environment
- SIEM Platform: Wazuh (Google Cloud)
- Endpoint: Windows 11 (VMware Fusion)
- Log Source: Windows Security Event Log
- Detection Focus: Failed logon events (Event ID 4625)

## Attack Scenario
A brute force-style attack was simulated by repeatedly attempting to log in to an existing Windows account (local administrator account: `sega`) using incorrect passwords within a short time window.

## Steps Performed

1. Verified that the Windows endpoint was connected to the Wazuh manager and actively sending logs
2. Opened Event Viewer and confirmed Security logs were being generated
3. Locked the Windows system using `Win + L`
4. Attempted login using incorrect passwords multiple times against the account `sega`
5. Generated multiple failed login events (Event ID 4625)
6. Observed events in Event Viewer under Windows Logs → Security
7. Queried Wazuh dashboard to identify corresponding failed authentication alerts

## Commands / Actions Used

- Lock system:
```
Win + L
```

- Event Viewer navigation:

Event Viewer → Windows Logs → Security → Filter (Event ID 4625)

## Expected Outcome

- Multiple Event ID 4625 entries generated in Windows
- Failed login attempts forwarded to Wazuh
- Alerts visible in Wazuh dashboard
- Pattern of repeated authentication failures identifiable
