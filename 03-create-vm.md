# Creating Domain Controller VM

## Objective
Create a virtual machine in Proxmox to host Windows Server 2022 for an Active Directory lab.

---

## VM Name
`dc01`

---

## Configuration
- **Guest OS:** Microsoft Windows (Windows 11/2022/2025 profile)
- **BIOS:** SeaBIOS
- **Machine type:** q35
- **SCSI Controller:** VirtIO SCSI single
- **Disk bus/device:** SCSI 0
- **Disk size:** 40 GB
- **Storage location:** local-lvm
- **CPU:** 1 socket, 2 cores
- **Memory:** 4096 MB
- **Network bridge:** vmbr0
- **Network adapter model:** VirtIO

---

## Notes
A SCSI disk with a VirtIO SCSI controller was selected for better performance and to more closely reflect modern virtualised server deployments.

VirtIO was also selected for the network adapter to improve virtual machine performance.

SeaBIOS was used instead of UEFI/TPM to keep the initial lab build simpler and reduce unnecessary complexity during installation.

---

## Result
The virtual machine was created successfully and was ready for Windows Server installation.

---

## Screenshots
- VM creation summary
- CPU and memory allocation
- Disk configuration
- Network configuration
