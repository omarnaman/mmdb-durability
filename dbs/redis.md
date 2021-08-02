# Redis



# Different Persistence/Durability [Modes](https://redis.io/topics/persistence):
* RDB (Redis Database): Periodic in-time snapshots
* AOF (Append Only File) logs writes to a file to be replayed to reconstruct the original database. the file fsync has different modes: always, everysec and no fsync. The commands are then stored as the same format as the Redis protocol
* No Persistence
* EDB + AOF