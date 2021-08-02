# [Apache Ignite](https://github.com/apache/ignite)

## [Ignite Native Persistence](https://ignite.apache.org/docs/latest/persistence/native-persistence)

Due to the distributed nature of Ignite, "every server node persists a subset of the data that only includes the partitions that are assigned to that node" [\[ref\]](https://ignite.apache.org/docs/latest/persistence/native-persistence)

Persistency features are as follows:
* Storing partitions to disk
* Write-ahead logging: A file that stores all the operations when a **page** is updates in RAM. The update is written to WAl instead of the partition file.
    * FSYNC: Atomic Writes, everything persisted to disk. No loss of data in any circumstance. 
    * LOG_ONLY: Updates are flushed to OS buffer cache, or memory mapped file. survives **PROCESS** crashes.
    * BACKGROUND: Periodic flushes to disk. The data lost is everything from the last flush.
    * NONE: No guarantees on any kind of crash. Data is only persisted if the instance is shutdown gracefully.
* Checkpointing: "Checkpointing is the process of copying dirty pages from RAM to partition files on disk. A dirty page is a page that was updated in RAM but was not written to the respective partition file (the update, however, was appended to the WAL)". Checkpointing allows the removal of any previous WAL. The frequency of the checkpoints are defined by multiple parameters: 
  * The number of dirty pages
  * A timeout (Every N Seconds)
* OS Memory Swap: does not provide any strong guarantees 

---

[Cluster Snapshot](https://ignite.apache.org/docs/latest/persistence/snapshots):
Ignite can create full cluster snapshots on demand; a copy of cluster-wide data records
