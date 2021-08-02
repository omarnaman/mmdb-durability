# [VoltDB](https://github.com/VoltDB/voltdb)
"A horizontally scaling in-memory database"


## Notes
* Large data is not stored in-line, but as pointers to a sepatare storage area.


## [Durability](https://docs.voltdb.com/UsingVoltDB/ChapKSafety.php)
* Snapshots: "snapshots" of the data within the DB at a given point of time. These are taken periodically or on demand. [Ch13](https://docs.voltdb.com/UsingVoltDB/ChapSaveRestore.php)
* Command logging: a log of all stored procedures invoked. This log can be replayed on startup to reinstate the database contents. [Ch14](https://docs.voltdb.com/UsingVoltDB/ChapCmdLog.php)
* K-Safety: K-replication of database partitions
* Disaster Recovery: replication of the entire databsae 