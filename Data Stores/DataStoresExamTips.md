# Data Stores Exam Tips #
[AWS Storage Options](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/storage-services.html)

Know when to use various data stores:

RDS
- Traditional relational data models
- Existing apps requiring RDBMS
- OLTP, ACID-compliant
DynamoDB
- High I/O needs
- Scale dynamically
S3
- BLOBs
EC2
- Database not supported under RDS
- Need complete control
Redshift
- OLAP

## Whitepapers ##
[SaaS Storage Strategies](SaaS Storage Strategies)
[Performance at Scale with Amazon ElastiCache](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://d0.awsstatic.com/whitepapers/performance-at-scale-with-amazon-elasticache.pdf)
[s3 Optimizing Performance Best Practices](https://docs.aws.amazon.com/whitepapers/latest/s3-optimizing-performance-best-practices/introduction.html)
[Performance Efficiency Pillar](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/storage-architecture-selection.html)

## Pro Tips ##
- Archiving and Backup often a great "pilot" to build AWS business cases
- Make use of the s3 endpoints within your VPC. (S3 endpoint to VPC)
- Learn how to properly secure your s3 bucket
- Encryption
- Consider Aurora for your pord MySQL/Maria or PostgreSQL needs. (includes automatic failover)
- Consider NoSQL if you don't need relational database features.
- Databases on EC2 cost less on the surface than RDS, but remember to factor in management (backups, patching, OS-level hardening)
- There can be a performance hit when RDS backups run if you have only a single AZ
