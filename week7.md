# Week 7 Security audit plan and evaluation

## Mandatory audit tasks (planned)
1. Lynis audit
- sudo apt -y install lynis
- sudo lynis audit system
Capture score before and after remediation.

2. nmap network assessment
Only within isolated VirtualBox network:
- nmap -sV -p- SERVER_IP
Goal: verify only expected ports exposed.

3. Access control verification
- sudo aa-status
Explain what is enforced and why.

4. Service inventory and justification
- systemctl --type=service --state=running
Justify each service required, disable unnecessary ones.

5. Remaining risk assessment
Document what risks remain and why, plus next steps.

## Reflection
Security hardening is iterative. Audits help move from assumptions to measured posture, but improvements can trade off usability and time to manage.
