# Proxmox Home Lab Setup

## Objective
Set up a local hypervisor to host virtual machines for IT support and Active Directory lab.

---

## Steps Completed
- Installed Proxmox on HP EliteDesk G4 Mini
- Configured static IP (192.168.0.50)
- Established network connectivity via Ethernet
- Accessed web interface successfully
- Resolved repository errors (enterprise repo + malformed sources)

---

## Result
Proxmox is fully operational and ready for VM deployment.

---

## Issues Encountered
- No Ethernet connection initially → unable to access web UI
- Repository errors due to enterprise sources
- Malformed .sources files

---

## Fixes
- Connected Ethernet
- Removed enterprise repo files
- Added no-subscription repo
