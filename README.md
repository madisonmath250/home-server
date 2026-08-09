# Home Lab — Systems Engineering & Infrastructure
Documentation for my personal home lab, built to develop hands-on experience with systems engineering, Linux administration, virtualization, networking, cybersecurity, integration, and testing.

By experimenting with configurations, services, and infrastructure, I use this environment to understand how systems work, diagnose failures, and develop practical skills that can be applied in professional systems engineering and IT fields.

## Objectives

My main objectives are to apply real-world technical concepts to gain hands-on experience.

- Design and manage virtualized infrastructure
- Develop practical networking and troubleshooting skills
- Practice system integration and validation
- Develop repeatable testing and verification procedures
- Explore infrastructure security and access control
- Document technical decisions, configurations, and lessons learned
- Build experience with self-hosted and containerized services

## System Overview

The lab began with a Proxmox VE virtualization platform and an Ubuntu Server virtual machine

Using an old PC, I wiped the current OS and installed my Proxmox Linux instance. In the future, I want to be able to access my environment remotely without exposing it to the public internet. This is going to be done using Tailscale

## Integration and Testing

Throughout this process, I will be testing features and components to meet my requirements specified in the documentation. 

Examples of planned validation include:
- Network connectivity testing
- IP configuration verification
- DNS resolution testing
- Gateway and routing validation
- VM connectivity testing
- Remote access validation
- Service availability testing
- Container health checks
- Firewall rule validation
- Network segmentation testing
- System resource monitoring

Testing procedures and results are documented in docs/integration-testing.md.

## Documentation

### Architecture
- Systems Architecture
- Requirements 

### Infrastructure 
- Proxmox
- Ubuntu Server
- Networking

### Security
- Security

### Testing
- Integration & Testing
- Troubleshooting

## Project Status
### Completed
- Proxmox VE installation
- Proxmox virtualization environment
- Ubuntu Server VM deployment
- Static network configuration
- Proxmox virtualization environment
- Ubuntu Server VM deployment
- Static network configuration

### In Progress
- Tailscale remote access
- Docker/containerized services
- Self-hosted applications
- Expanded testing documentation
- Infrastructure monitoring

### Planned 
- Additional virtual machines
- Automated backups
- Infrastructure automation
- Expanded security controls 
- Firewall 
- VLAN segmentation


## Lessons Learned 
This repository is also used to document problems encountered during implementation and how they were diagnosed and resolved.

Troubleshooting documentation focuses on:
1. **Problem identification**
2. **System investigation**
3. **Root-cause analysis**
4. **Corrective action**
5. **Verification**
6. **Lessons learned**
