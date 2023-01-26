## Concepts ##
# Data Persistence #
- Persistent Data Store

Data is durable and sticks around after reboots, restarts, or power cycles. E.G. Glacier RDS

- Transient Data Store

Data is just temporarily stored and passed along to another process or persistent store. E.G. SQS SNS

- Ephemeral Data Store

Data is lost when stopped

# IOPS vs. Throughput
- Input/Output Operations per Second (IOPS)

Measures khow fast we can read and write to a device (think fast car)

- Thoughput

Measure of how much data can be moved at a time (think dump truck)

# Consistency Models - ACID & BASE #
ACID
- Atomic.  Transactions are all or nothing.
- Consistent.  Transactions must be valid.
- Isolated.  Transactions can't mess with one another.
- Durable.  Completed transaction must stick around.

BASE
- Basic Availability.  Values availability even if stale.
- Soft-state.  Might not be instantly consistent across stores.
- Eventual Consistency. Will achieve consistency at some point.
