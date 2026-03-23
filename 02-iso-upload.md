# ISO Upload to Proxmox

## Objective
Upload Windows Server ISO for VM deployment.

## Steps
- Navigated to local storage in Proxmox
- Selected ISO Images tab
- Uploaded Windows Server 2022 ISO

## Supporting Image
![Alt text](/ISOUploadProxmox.jpg)

## Result
ISO available for virtual machine creation.

## Notes
HTTPS is providing encryption, but the browser does not accept the self-signed certificate from Proxmox as trusted. Therefore, it shows a not secure error. This is an acceptable risk in my case because I am on an internal (at home), non-public, trusted LAN environment. The self-signed certificate provides the same level of data encryption (TLS) despite not being signed by a recognised Certificate Authority.
 
