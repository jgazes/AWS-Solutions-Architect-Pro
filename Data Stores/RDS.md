# Amazon RDS #

- Managed database option for MySQL, Maria, PostgreSQL, Microsoft SQL Server, Oracll and MySQL-compatible Aurora
- Best for structured, relational data store needs
- Aims to be drop-in replacement for exist on-prem instances of the same databases
- Automated backups and patching in customer-defined maintenance windows
- Push-button scaling, replication and redundancy

## Anti-Paterns ##

If you need... Dont use RDS, instead use...
- Lots of large binary objects (BLOBs), s3
- Automated scalability, DynamoDB
- Name/Value Data Structure, DynamoDB
- Data is not well structured or unpredicatable, DynamoDB
- Other DB unsupported by RDS (IBM DB2 or SAP HANA), EC2
- Complete control over the DB, EC2

## Other Notes ##
- In a multi AZ environment, the stand-by DB will be syncronously replicated
- Read replica's are Aysnchronously replicated
- If one AZ fails, the stand-by in another AZ assumes the role of Master, and the Read Replicas keep on
