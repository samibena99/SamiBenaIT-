# 🌐 Network Troubleshooting Runbook

## Overview
A standardized runbook for diagnosing and resolving common LAN/WAN connectivity issues — designed to reduce mean time to resolution (MTTR) and help junior technicians handle network incidents confidently.

## Problem
Network incidents were handled inconsistently, with no documented escalation path. Junior staff spent excessive time on basic issues, and recurring problems lacked root-cause documentation.

## Solution
Created a structured runbook with decision trees, common fixes, and escalation thresholds — used as a living document updated after each resolved incident.

---

## Troubleshooting Decision Tree

```
User reports: "No internet / Cannot connect"
        │
        ▼
Is it one user or multiple?
 ├── One user ──► Check workstation (NIC, IP, DNS, browser)
 └── Multiple ──► Check switch/router, ISP, DHCP server
        │
        ▼
Can the user ping the default gateway?
 ├── No  ──► IP conflict / DHCP issue / cable fault
 └── Yes ──► DNS issue / proxy / firewall / ISP outage
        │
        ▼
Can the user ping 8.8.8.8?
 ├── No  ──► ISP or WAN issue — escalate to ISP / network admin
 └── Yes ──► DNS resolution issue — flush DNS / update DNS servers
```

---

## Common Issues & Fixes

| Symptom | Likely Cause | Fix |
|---------|-------------|-----|
| No IP address | DHCP failure | Release/renew IP (`ipconfig /release` + `/renew`) |
| Limited connectivity | IP conflict | Assign static IP or check DHCP leases |
| Slow internet | Congestion / DNS lag | Change DNS to 8.8.8.8, check bandwidth usage |
| Cannot reach internal servers | DNS / VLAN issue | Check local DNS, verify VLAN assignment |
| Wi-Fi drops randomly | Driver / AP issue | Update NIC drivers, check AP load |
| VPN not connecting | Firewall / credentials | Check firewall rules, verify VPN credentials |

---

## Diagnostic Commands (Windows)

```cmd
# Check IP configuration
ipconfig /all

# Test connectivity
ping 8.8.8.8
ping google.com

# Trace network path
tracert 8.8.8.8

# Flush DNS cache
ipconfig /flushdns

# Check open connections
netstat -an

# Release and renew IP
ipconfig /release
ipconfig /renew
```

## Technologies Used
- Windows Networking Tools (ipconfig, ping, tracert, netstat)
- Network switches and routers (basic CLI)
- LAN/WAN infrastructure
- DHCP and DNS servers

## Outcome
- Reduced average network incident resolution time by **35%**
- Enabled L1 technicians to resolve 70% of network issues independently without escalation
- Used as onboarding material for new IT team members

---

> 📁 [Back to Portfolio](../README.md)
