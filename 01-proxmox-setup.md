# Proxmox Home Lab Setup

## Objective
Set up a local hypervisor to host virtual machines for IT support and Active Directory lab.

---

## Steps Completed
- Installed Proxmox on HP EliteDesk G4 Mini

!["Select boot form usb from EUFI menu"](/BootFromUsb.jpeg)  
!["Image of Proxmox installation screen"](/InstallProxMox.jpg)

- Configured static IP (192.168.0.50)

![Proxmox IP configuration screen](/ConfigureProxMox.jpg)

- Established network connectivity via Ethernet
- Accessed web interface successfully

![Proxmox application in browser](/ProxmoxBrowser.jpg)

- Resolved repository errors (enterprise repo + malformed sources)

---

## Result
Proxmox is fully operational and ready for VM deployment.

---

## Issues Encountered
- No Ethernet connection initially → unable to access web UI.
- Repository errors due to enterprise sources. 
- Malformed .sources files.

---

## Fixes
- Connected Ethernet
- Removed enterprise repo files
- Added no-subscription repo
