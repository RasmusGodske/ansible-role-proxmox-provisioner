# Creating the Cloud Init


It is possible to set the cloud init settings inside proxmox using the webui and then export the settings by running:
```bash
# Dump user config
qm cloudinit dump 9000 user
# Dump meta config
qm cloudinit dump 9000 network
# Dump meta config
qm cloudinit dump 9000 meta
```


# Notes
The network-ci-snippet.yaml is not in use at the moment. Because I were unable to get it to work at the time of writing this.

Problems:
- There were no signs of the network cloud init settings being applied.
- When using the network cloud init, the network interface would be named `ens18` instead of `eth0` which is the default for the cloud image.
- When using the network cloud init, the network interface would not be configured with DHCP.
