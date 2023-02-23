# CloudFuzz
A blockchain solution for digital forensic evidence storage and verification.

## **REQUIREMENTS**
- *Atleast* 3 systems with minimum specifications:
  + 4Gb RAM
  + 500Gb internal storage
  + i3 processor
  + OS-Ubuntu 18.04.6(Bionic Beaver)
  + NIC(for physical topology setup)
- Multiple Ethernet cables to facilitate topology setup.
- Stable WLAN or LAN connection.
- Stable internet connection during inastallations and setup.

## **PROCEDURE**

### *STEP 1*:
 + **CREATE A CLOUD**: Refer to CloudStack documentation to create a private cloud.
 + **SETUP MANAGEMENT SERVER**:Use system with highest specifications as the management server and the rest as Host machines to host VM instances.

### *STEP 2*:
 + **SETUP KVM**: In machines other than the machine with management server, install KVM-QEMU and enable it for virtualization.
 + **SETUP CLOUSTACK AGENT**: Install cloudstack agent and setup according to documentation in CloudStack.

### *STEP 3*:
 + Connect management server machine with the VMs using virtual network and LAN when required. 
