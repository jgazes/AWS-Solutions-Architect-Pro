# Other Database Options #

## Athena ##
- SQL Engine overlaid on s3 base on Presto
- Query raw data objects as they sit in s3
- Use or convert data into Parquet format if possible for performance jump
- Similar concept to Redshift spectrum but... Use Athena if data lives mostly on s3 without the need to perform joins with other data sources.  Use Redshift Spectrum if you want to join s3 data with existing RedShift tables or create union products.

## Quantum Ledger Database ##
- Based on blockchain concepts
- Provides immutable and transparent journal as a service without havining to set up and maintain an entire blockchain framework
- Centralized design (as opposed to decentralized consensus based design for common blockchain frameworks) allows for higher performance and scalability.
- Append-only concept where each record contributes to the integrity of the chain

## Amazon Managed Blockchain ##
- Fully managed blockchain framework supporting open source frameworks of Hyberledger Fabric and Ethereum
- Distributed consensus-based concept consisting of a nework, members (other AWS accounts), nodes (instances) and potentailly applications
- Uses the Amazon QLDB ordering service to maintain complete hisory of all transactions

## Amazon Timestream Databasee ##
- Fully managed database service specifically built for storing and analyzing time-series data.
- Alternative to DynamoDB or Redshift and includes some built-in analytics like interpolation and smoothing.
- Use cases include industrial machinery, sensor networks, equipment telemetry

## Amazon DocumentDB  ##
- Has MongoDB compatibility
- AWS's inventon that emulates the Mongo DB API so it acts like MongoDB to existing clients and users
- Fully managed with all the good stuff (multi-AZ HA, scalable, integrated with KMS, backed up to s3)
- An option if you currently use MongoDB

## Amazon OpenSearch (Elasticsearch) ##
- Not to be confused with ElastiCache
- Mostly a search engine but also a document store 
- Service components are sometimes referred to as an ELK stack
- Formerly known as Elasticsearch, now referred to as OpenSearch
[Announcing Amazon OpenSearch Service which Supports OpenSearch 1.0](https://aws.amazon.com/blogs/aws/announcing-amazon-opensearch-service-which-supports-opensearch-10/)
[Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/)

Analytics - Kibana
Intake - LogStash | Cloudwatch, Firehose, IoT
Search and Storage - OpenSearch


