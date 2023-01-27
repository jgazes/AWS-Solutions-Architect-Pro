# Elastic File Service #
- Network file share
- EFS is an implementation of NFS file share
- Elastic storage capacity, and pay for only what you use (in contrast to EBS)
- Multi-AZ metadata and data storage
- Configure mount-points in one or many AZs
- Can be mounted from an on-prem system (requires very fast and stable connection like Direct Connect)
- Alternatively rather than mount directly on prem, you can use *Amazon DataSync*.
- Amazon Datasync: data transfer service that simplifies, automates, and accelerates moving data between storage systems and services.
- Amazon Datasync is used for data migration, archiving cold data, data protection, data movement for timely in cloud processing.
- EFS is about 3 times more expensive than EBS and 20 times more expensive than s3.

EFS Use Cases
- Content Repositories
- Development Environments
- Web server farms
- Home directories
- Big data applications
