Types: lock-based and timestamp-based CC mechanisms

Conflict resolution depends on the algorithms: Some algorithms choose to let the rejected transactions wait until the lock is released, while some algorithms choose to abort one of the conflicting transactions.

In timestamp-based mechanisms, each transaction in transaction system will be assigned a unique timestamp. 

Advantages: MVCC could have better performance than single-version based CC due to its high concurrency and low rejection rate of data access.

MVCC tends to perform better than 2PL in read-intensive scenarios by reducing read-write conflicts and allowing more concurrent access to data. However, it might incur overhead due to maintaining multiple versions of data items and the need for garbage collection of old versions.

2PL might perform better in write-heavy environments or in scenarios where strict serializability is required, but it can suffer from higher locking overhead and potential deadlock scenarios.


[Text Source](https://www.diva-portal.org/smash/get/diva2:934461/FULLTEXT01.pdf)

This [source](https://www.dpss.inesc-id.pt/~romanop/files/papers/mascots08.pdf) shows that MVCC is efficient in read-intensive applications. 

https://stormatics.tech/alis-planet-postgresql/database-concurrency-two-phase-locking-2pl-to-mvcc-part-2

https://www.alibabacloud.com/blog/a-deep-dive-into-database-concurrency-control_596779

