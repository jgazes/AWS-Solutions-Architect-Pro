# Enhanced Networking #
- Generally used for High Perfomance Computing use-cases
- Uses single root I/O virtualization (SR-IOV) to deliver higher performance than traditional virtualized network interfaces
- Might have to install driver if other than Amazon Linux HVM AMI
- Intel 82599 VF Interface (10Gbps)
- Elastic Network Adapter (25Gbps)

## Placement Groups ##
Clustered
- What. Instances are placed into a low latency group within a single AZ
- When. Need low network latency and/or high network throughput
- Pros. Get the most out of enhanced networking instances
- Cons. Finite capacity: recommend launching all you might need up front

Spread
- What. Instances spread across underlying hardware
- When. Reduce risk of simultaneous failure if underlying hardware fails
- Pros. Can span multiple AZs
- Cons. Max of 7 instances running per group per AZ

Partition
- What. Instances are grouped into partitions and spread across racks
- When. Reduce risk of correlated hardware failure for multi-instance workloads
- Pros. Better for large distributed or replicated workloads than spread
- Cons. Not supported for Dedicated Hosts
