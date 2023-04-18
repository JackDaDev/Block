# CloudFuzz
A blockchain solution for digital forensic evidence storage and verification.

## **REQUIREMENTS**
- *Atleast* 3 systems with minimum specifications:
  + 8Gb RAM
  + 500Gb internal storage
  + i3 processor
  + OS-Ubuntu 18.04.6(Bionic Beaver)
  + NIC(for physical topology setup)
- Multiple Ethernet cables to facilitate topology setup.
- Stable WLAN or LAN connection.
- Stable internet connection during inastallations and setup.

## **PROCEDURE**

 + **set up MicroStack with Cinder Loop Device support*: To install it perform the command `sudo snap install microstack --devmode --beta`
 
 Initialize by executing this command `sudo microstack init --auto --control --setup-loop-based-cinder-lvm-backend --loop-device-file-size 50` in which 50 indicates the amount of cinder space in GB.
 ```
sudo tee /var/snap/microstack/common/etc/cinder/cinder.conf.d/glance.conf <<EOF
[DEFAULT]
glance_ca_certificates_file = /var/snap/microstack/common/etc/ssl/certs/cacert.pem
EOF
```
And to finish off setup 
`sudo snap restart microstack.cinder-{uwsgi,scheduler,volume}`

To add compute nodes to the control node perform the following commands

`sudo microstack add-compute`
## **⚠️Warning⚠️**
It is advised not to run init command more than once on the same PC and to use a unique connection string for a compute node

`sudo microstack init --auto --compute --join <connection-string>`
If any errors occur, execute the below command

`sudo snap remove --purge microstack`

If neutron shows up with an error, well at least it ain't a nuclear one. But if it does perform the following commands
```
sudo systemctl revert snap.microstack.neutron-api.service
sudo systemctl revert snap.microstack.neutron-ovn-metadata-agent.service
```

 
