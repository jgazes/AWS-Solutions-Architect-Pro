# Amazon Storage Gateway #

[Amazon FSx File Gateway](https://aws.amazon.com/storagegateway/file/fsx/)

- Virtual Machine that you can run on prem with VMWare or HyberV OR via a specially configured Dell hardware appliance
- Provides local storage resoureces backed by AWS s3 and Glacier
- Often used in DR preparedness to sync to AWS
- Useful in cloud migrations

- New Name, Old Name, Interface, Function
- File Gateway, None, NFS/SMB, Allow on-prem or EC2 instances to store objects in s3 via NFS or SMB mount point
- Volume Gateway Stored Mode, Gateway-stored Volumes, iSCSI, Async replication of on-prem data to s3
- Volume Gateway Cached Mode, Gateway-cached Volumes, iSCSI, Primary data stored in s3 with frequently access data cached locally on-prem
- [iSCSI](https://www.techtarget.com/searchstorage/definition/iSCSI)
- Tape Gateway, Gateway-Virtual Tape Library, iSCSI, Virtual media changer and tape library for use with existing backup software

- AWS Storage Gateway has a bandwidth throttling feature.
