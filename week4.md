# Week 4 Initial system configuration and core security

## Planned implementation steps
1. Create non root admin user
- adduser adminuser
- usermod -aG sudo adminuser

2. SSH key based auth from workstation
On workstation:
- ssh-keygen -t ed25519
- ssh-copy-id adminuser@SERVER_IP
Test:
- ssh adminuser@SERVER_IP

3. Harden SSH
Edit /etc/ssh/sshd_config:
- PermitRootLogin no
- PasswordAuthentication no
- PubkeyAuthentication yes
Then:
- sudo systemctl restart ssh

4. Firewall allowlist
Using ufw:
- sudo ufw default deny incoming
- sudo ufw default allow outgoing
- sudo ufw allow from WORKSTATION_IP to any port 22 proto tcp
- sudo ufw enable
- sudo ufw status verbose

## Evidence plan
Screenshots required:
- successful SSH from workstation to server
- before and after sshd_config snippet
- full ufw ruleset output
