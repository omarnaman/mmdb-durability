# MongoDB

Highly configurable durability guarantees

## Durability configurations [(journaling)](https://docs.mongodb.com/manual/core/journaling/)
* MongoDB uses a *journal* that contains the location and bytes changes for each write.
* One journal per client initiated write,"The journal record includes any internal write operations caused by the initial write".
* the journals are compressed to save space unless the record is less than 128 bytes. The maximum record size is 100MB, if the file exceeds 100MB, a new journal is created.

## [In-memory Engine](https://docs.mongodb.com/manual/core/inmemory/)
* The fully in-memory version of MongoDB. This engine does not guarantee any durability to the data, and journaling does not exist