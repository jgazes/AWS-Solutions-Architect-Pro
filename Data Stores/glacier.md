# Amazon Glacier #
- Cheap, slow to respond, seldom accessed
- "Cold Storage"
- Used by AWS Storage Gateway Virtual Tape Library
- Integrated with AWS S3 via Lifecycle Management
- Faster retrieval speed options if you pay more
- Glacier Vault similar to s3 bucket, Glacier archive similar to and s3 object. Zip, tar, files max size 40TB, immutable
- Glacier vault lock handles policies.  Different than vault access policy, enforces rules like no deletes or MFA, Immutable 
- Immable means you cant change it, you can delete or override but cannot change 
- Vault locks, initiate vault lock and have a 24 hour timeline to decide whther to abort or complete the lock.


