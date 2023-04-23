# Network Node Performance Analysis Report
## Introduction
The purpose of this report is to provide an analysis of the performance of a network node that is running as a validator node. A series of benchmark tests were conducted to assess the hardware and software performance of the node.

## Hardware Specifications
The network node is running on a machine with the following specifications:
- Processor: AMD EPYC 7282 16-Core Processor
- CPU(s): 4
- RAM: 8GB
- Storage: 194GB

## Software Configuration
The following software is installed on the network node:
- Operating System: Ubuntu 20.04.6 LTS
- Validator Software: Geekbench 5, memtester, info
- Monitoring Software: Prometheus v2.29.1 and Grafana v8.1.2

## Benchmark Tests
The following benchmark tests were conducted to evaluate the performance of the network node:

## CPU Benchmark Test
A CPU benchmark test was run using the **`Geekbench 5`** software.

Install and run Geekbench
```bash
wget https://cdn.geekbench.com/Geekbench-5.3.1-Linux.tar.gz
tar xf Geekbench-5.3.1-Linux.tar.gz
cd Geekbench-5.3.1-Linux/
./geekbench5
```
The test results were as follows:
```text
- Single-Core Score: 646
- Multi-Core Score: 1691
```

## Memory Benchmark Test
A memory benchmark test was run using the **`memtester`** software. 

Install and run
```bash
sudo apt-get install -y memtester
sudo memtester 1024 8
```
The test results were as follows:
```text
- Test Time: 30 minutes
- Test Size: 8GB
- Errors: 0
```

## Storage Benchmark Test
A storage benchmark test was run using the **`fio`** software.

Install and run
```bash
sudo apt-get -y install fio
fio --name=random-write --ioengine=posixaio --rw=randwrite --bs=4k --numjobs=1 --size=4g --iodepth=1 --runtime=60 --time_based --end_fsync=1
```
The test results were as follows:
```text
WRITE: bw=3138KiB/s (3214kB/s), 3138KiB/s-3138KiB/s (3214kB/s-3214kB/s), io=765MiB (802MB), run=249565-249565msec
```

## Bandwidth Usage
The bandwidth usage of the network node was monitored for a period of 24 hours using the Prometheus and Grafana monitoring software. The results showed that the network node was using an average of 1Gbps during peak hours and 200Mbps during off-peak hours.

## Conclusion
Based on the benchmark tests and bandwidth usage monitoring, the performance of the network node is satisfactory. The hardware and software specifications meet the requirements for running a validator node efficiently, and the network bandwidth usage is well within the expected range.

## Bonus 
Additionally, a tool called [celestia-tool](https://github.com/longnh3592/Create_Toolings_For_The_Celestia_Network) was used to monitor resource usage. The following parameters were obtained:
- CPU usage does not exceed 20%
- RAM usage does not exceed 30%
- Disk usage does not exceed 20GB

From this data, it can be inferred that the celestia-light software is not using up the server's resources. This means that the server's resources are redundant, and it may be more cost-effective to move celestia-light to a server with lower specifications.