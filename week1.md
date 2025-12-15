# Week 1 System planning and distribution selection

## Target architecture
I will deploy two systems:
- Server: Ubuntu Server (headless), administered only via SSH
- Workstation: my host machine acting as SSH client

Network: isolated VirtualBox network (host only or internal network) so all testing remains local.

## Architecture diagram
Workstation (SSH client)  <---- SSH over isolated VM network ---->  Server (Ubuntu Server headless)
Only the workstation IP is allowed through the server firewall for SSH.

## Distribution choice
Chosen: Ubuntu Server LTS
Reasons:
- strong documentation and community support
- simple package management with apt
- good default security baseline and easy updates
Alternatives considered: Debian stable, Rocky Linux
Trade off: Debian can be more conservative, Rocky aligns with enterprise RHEL ecosystem, Ubuntu is a practical balance for this coursework.

## Network configuration plan
VirtualBox:
- server VM on host only network
- workstation uses host OS SSH client
IP plan: static IP for the server VM, known workstation host only adapter IP.
Reason: firewall rule needs a consistent source IP.

## System specifications commands (planned evidence)
On the server I would capture output for:
- uname -a
- free -h
- df -h
- ip addr
- lsb_release -a

Evidence plan: terminal screenshots showing username@hostname prompts.
