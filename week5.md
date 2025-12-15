# Week 5 Advanced security and monitoring scripts

## Mandatory access control
Ubuntu uses AppArmor by default.
Planned checks:
- sudo aa-status
If a profile needs enforcing:
- sudo aa-enforce /etc/apparmor.d/*

## Automatic security updates
Planned:
- sudo apt -y install unattended-upgrades
- sudo dpkg-reconfigure unattended-upgrades
Evidence: config file snippet and status.

## fail2ban
Planned:
- sudo apt -y install fail2ban
- sudo systemctl enable --now fail2ban
- sudo fail2ban-client status
- sudo fail2ban-client status sshd

## security-baseline.sh (planned script outline)
Purpose: verify settings for SSH hardening, firewall, updates, AppArmor, fail2ban.
Checks:
- parse sshd_config for required options
- ufw status and rules include workstation allow
- unattended upgrades config present
- aa-status shows enforcing
- fail2ban running and sshd jail enabled
Output: PASS or FAIL per control with clear messages.

## monitor-server.sh (planned script outline)
Runs on workstation:
- loops every N seconds
- ssh to server and collects: uptime, top snapshot, free -h, df -h, ip -s link
- writes to timestamped CSV

## Reflection
Security controls must be testable. Scripts create repeatable evidence and reduce human error in checks.
