## Remote Access Testing: Tailscale

### Test Objective

Verify that an authorized device can remotely access the Proxmox UI/web page and SSH through Tailscale.

### 1. Identify What Will Be Tested

Test the ability to connect to the Proxmox environment remotely through the Tailscale network and establish an SSH session.

### 2. Define Expected Behavior

An authorized device should be able to connect to the environment through its Tailscale address and establish an SSH connection without requiring direct access to the local network.

### 3. Execute the Test

1. Connect the remote device to the Tailscale network.
2. Verify that the environment appears as an available device.
3. Identify the server's Tailscale IP address.
4. Test connectivity to the server.

```bash
ping <tailscale-ip>
```
5. Attempt to connect to the environment using SSH
  
```bash
ssh <ip>@<username>
```

6. Verify that the session is established
7. Ensure normal server commands can be executed through the remote connection

### 4. Results

Tailscale connection: PASS
Server reachable through Tailscale: PASS
SSH connection: PASS 
Remote shell access: PASS 

### 5. Determine If Requirements Were Met

The remote-access requirement is met if an authorized device can successfully reach the environment through Tailscale and establish an SSH session without being connected to the local network.

Requirement Status: PASS
