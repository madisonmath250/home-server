# Remote Access

## Overview
Tailscale is used in the homelab to provide secure remote access to the server without exposing administrative services directly to the public internet.

The goal is to be able to remotely manage the server while keeping access limited to authorized devices.

### Purpose
The remote-access system is intended to:

- Provide encrypted access to the homelab from outside the local network
- Allow remote administration of the Proxmox environment 
- Reduce the need to expose SSH directly to the public internet
- Provide a reliable way to access the server when away from the local network

[Tailscale Testing](/testing/tailscale.md)
