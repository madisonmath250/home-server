### Problem: Proxmox Network Connectivity Failure
## Overview
**Date:** 2026-07-25

**System:** Proxmox Server on Replacement Hardware

### **Observed Behavior:**

The replacement computer successfully booted Proxmox, but the Proxmox web interface was unavailable, and SSH connections were failing. The server was still responding to ping requests.

### **Expected Behavior:**

The Proxmox server should be reachable over the network, allowing access to both the Proxmox web interface and SSH.

### **Testing Steps:**

1. Sent ping requests to the Proxmox server from another computer on the network.
2. Confirmed that the server responded successfully to ping requests.
3. Attempted to connect to the server using SSH.
4. Confirmed that the SSH connection failed.
5. Connected a monitor and keyboard directly to the Proxmox server for local troubleshooting.
6. Checked the SSH service using:

```bash
systemctl status ssh

```
7. Confirmed that the SSH service was active.
8. Checked the network service using

```bash
systemctl status networking
```

9. Received error: `vmbr0: bridge port nic1 does not exist`

10. Listed the available network interfaces using

```bash
ip link
```

11. Found that the replacement hardware indentified the netowrk interface as: `eno1`

12. Compared the interface name with existing Proxmox netowrk config.
13. Found that the vmbr0 bridge was still configured to nic1.
14. Edited `/etc/network/interfaces` and changed `bridge-ports nic1` to `bridge-ports eno1`

15. Restarted the networking services using

```bash
systemctl restart networking
```

16. Tested SSH and Proxmox web interface again.

### **Root Cause:**

After moving the Proxmox drive to the replacement computer, the network interface was given a different name, `eno1`, instead of the original `nic1`. 

The Proxmox configuration was still looking for `nic1`, which no longer existed on the new hardware. Because `vmbr0` was still configured to use `nic1`, the network bridge could not start properly. 

This prevented the server from being accessed through SSH or the Proxmox web interface.

### **Corrective Action:**

Updated the Proxmox network configuration to use `eno1`, instead of `nic1`.

### **Explanation:**

Moving the Proxmox boot drive to different hardware caused Linux to identify the network adapter using a different interface name. The operating system and Proxmox installation remained functional, but the existing bridge configuration was tied to the interface name from the original hardware.

The ip link command was used to identify the new interface name, and the Proxmox bridge configuration was updated accordingly.

### **Result:**

After updating the bridge configuration and restarting networking, the Proxmox network connection was restored. SSH access and the Proxmox web interface became available again.

### **Lessons Learned:**

Hardware changes can affect network interface naming even when the operating system and configuration files remain unchanged. When troubleshooting network issues after a hardware replacement, checking the available interfaces with ip link is an important first step.

A server responding to ping does not necessarily mean that all network services are functioning correctly. Individual services such as SSH and web interfaces should also be tested during network troubleshooting.
