# Amazon Dynamo DB #
[Using Global Secondary Indexes in DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)

- Managed, multi-AZ NoSQL data store with Cross-Region Replication option
- Defaults to eventual consistency reads but can request strongly consistent read via SDK parameter
- Priced on throughput, rather than compute
- Provision read and write capacity in anticipation of need.
- Autoscale capacity adjusts per configured min/max levels.
- On-Demand Capacity for flexible capacity at a small premium cost.
- More cost effective to pre-provision capacity rather than on demand
- Achieve ACID compliance with DynamoDB Transactions

## Relational vs NoSQL ##

- Relational is good when data is structured very well
- NoSQL excell at managing name value pairs, self contained, doesnt need to relate to other tables (json etc.)
- Primary key must be UNIQUE, also known as the Partition Key.  We can have occurrences of the same partition key, so long as the sort key is different

## Secondary Indexes ##
Index Type, Description, How to remember
- Global Secondary Index, Partition key and sort key can be different from those on the table, Not restricted to just the partitioning set forth by the partition key
- Local Secondary Index, Same partition key as the table but different sort key, Have to stay local and respect the table's partition key, but can choose whatever sort key needed.

- There is a limit to the number of indexes and attrubutes per index
- Indexes take up storage space

- Global Secondary Index is used when you want a fast query of attributes outside the primary key without having to do a table scan (read everything sequentially). E.G. I'd like to query Sales Orders by Customer number rather than Sales Order Number
- Local Secondary Index is used when you already know the partition key and want to quickly query on some other attribute. E.G. I have the Sales Order Number, but I would like to retrieve only those records with a certain Material Number.

- When you create an index, you need to select which attributes are projected into that index

Use cases for secondary indexes

If you need to... Consider... Cost... Benefit...
- Access just a few attributes the fastes way posible, Projecting just those few attributes into a global secondary index, minimal, lowest possible latency access for non-key items
- Frequently access some non-key attributes, Projecting those attribtues into a global secondary index, Moderate; aim to offset cost of table scans, lowest possible latency access for non-key items
- Frequently access most non-key attributes, Projecting those attrbutes or even the entier table into a global secondary index, up to double, maximum flexibility
- Rarely query but write or update frequently, Projecting keys only for the global secondary index, minimal, very fast write or updates for non-partition key items

## Dynamo DB Design Practices ##

- Sparse Indexes
- Replicas via Secondary Indexes (e.g. free tier customers, or high write capacity from data stream into primary table, but read from secondary table)

