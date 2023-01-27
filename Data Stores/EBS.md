# Elastic Block Store #
- Virtual Hard Drives
- Can only be used with EC2
- Tied to a single AZ
- Variety of optimized choices for IOPS, Throughput and Cost.
- Snapshots are great.

## EBS vs Instance Stores ##
- Instance stores are only available when the ec2 is running, locked to the instance, and is erased when rebooted or terminated
- Ideal for caches, buffers, work areas
- Looks like an EBS volume
- Instance stores are directly attached to the instance, whereas EBS travels over the network
- EBS can be snapshotted

## EBS Snapshots ##
- Cost effective and easy backup strategy
- Share data sets with other users or accounts
- Migrate a system to a new AZ or Region
- Convert an unencrypted volume to an encrypted volume

## Data Lifecycle Manager ##
- Schedule snapshots for volumes or instances every X hours
- Retention rules to remove old snapshots

