# Amazon Elasticache #

- Fully managed implementations of two popular in-memory data stores - Redis and Memcahced
- Push-button scalability for memory, writes and reads
- In memory key/value store - not persistent in the traditional sense
- Billed by node size and hours of use

Use/Benefit
- Web session store.  In cases with load balanced web servers, store web session information in Redis so if a server is lost, the session info is not lost and another web server can pick up.
- Database Caching.  Use memcache in front of AWS RDS to cache popular queries to offload work from RDS and return results faster to users.
- Leaderboards.  Use Redis to provide a live leaderboard for millions of users of your mobile app.
- Streaming Data Dashboards.  Provide a landing spot for streaming sensor data on the factory floor, providing live real-time dashboard displays

## Memchached vs Redis ##

Memcached
- Simple, no-frills, straght forward
- You need to scale out and in as demand changes
- You need to run multiple CPU cores and threads
- You need to cache objects (like db queries)

Redis
- You need encryption
- You need HIPAA compliance
- Support for clustering
- You need complex data types
- Pub/sub capability
- Geospacial indexing
- Backup and restore

