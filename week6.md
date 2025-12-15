# Week 6 Performance evaluation approach and analysis plan

## Testing methodology
For each selected application:
1. record baseline metrics
2. apply load test
3. identify bottleneck
4. implement one optimisation
5. re test and compare

## Example tests (planned)
CPU:
- stress-ng --cpu 2 --timeout 120s
Memory:
- stress-ng --vm 1 --vm-bytes 70% --timeout 120s
Disk IO:
- fio --name=randread --ioengine=libaio --rw=randread --bs=4k --numjobs=1 --size=256M --runtime=120 --time_based
Network:
- iperf3 server on server VM, client on workstation

## Two optimisations (planned)
1. Disable or remove unnecessary services to reduce baseline usage
2. Tune system parameters where justified, for example swappiness, and verify impact on memory behaviour

## Data tables and visualisations
Plan:
- store CSV results
- create charts for CPU, memory, IO throughput, network throughput, latency
- include brief interpretation and trade offs
