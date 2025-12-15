# Week 2 Security planning and testing methodology

## Performance testing plan
Goal: measure baseline and under load, then apply two optimisations and re measure.
Remote monitoring methodology:
- workstation runs a script that connects via SSH and samples metrics
- store results as CSV for charts and graphs

Metrics to capture:
- CPU: top or mpstat
- memory: free, vmstat
- disk IO: iostat or /proc/diskstats
- network: iperf3 for throughput, ping for latency
- service response time: curl time measurements if a web service is used

## Security configuration checklist
Planned controls:
- SSH hardening: key based auth only, disable password auth, disable root login
- firewall: allow SSH only from workstation IP, deny all else
- user privilege: non root admin user, sudo with least privilege
- mandatory access control: AppArmor or SELinux
- automatic security updates enabled
- intrusion detection: fail2ban for SSH

## Threat model (3 threats, mitigations)
1. Brute force SSH login attempts
Mitigation: key based auth, disable password auth, fail2ban, firewall IP allowlist

2. Remote exploitation of unnecessary services
Mitigation: minimal install, disable unused services, service inventory justification, firewall default deny

3. Privilege escalation after initial access
Mitigation: least privilege user, sudo logging, timely updates, AppArmor confinement

## Reflection
Security controls must be implemented in a way that does not lock me out of SSH. My plan is to test key based login first, then tighten SSH settings, then enable firewall rules.
