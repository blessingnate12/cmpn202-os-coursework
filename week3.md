# Week 3 Application selection for performance testing

## Application selection matrix
I will test a mix of workload types:

| Workload type | Application choice | Why chosen | Expected resource profile |
|---|---|---|---|
| CPU intensive | stress ng | controllable CPU load | high CPU, moderate memory |
| RAM intensive | stress ng memory workers | controllable memory pressure | high memory usage |
| Disk IO intensive | fio | repeatable IO patterns | high IO, possible latency impact |
| Network intensive | iperf3 | throughput and stability | high network usage |
| Server service | nginx | common server baseline | low CPU, network bound under load |

## Installation commands (planned)
- sudo apt update && sudo apt -y upgrade
- sudo apt -y install stress-ng fio iperf3 nginx

## Monitoring strategy
For each test:
- capture baseline for 2 to 5 minutes
- run load for 5 to 10 minutes
- capture cooldown after stopping load
- record results in CSV
