# [TimesTen](http://csci6442.org/papers/IEEE.pdf#page=8)

Everything is heavily affected by the parallelization of the system.

* "TimesTen uses check-pointing with write-ahead logging for durability"
* The log is split into multiple partitions to enable parallel processing; so the generation is not serialized. But the logs are serialized when the state is restored from the logs. (Check Mechanism)
* TimesTen offers a high-performance logging mode called "delayed-durability": where the log updates are flushed to disk periodically (100ms) instead of after every update.
* TimesTen Generates to checkpoint files, where the checkpoint process switches between files when the process is completed. This insures that at least one of the checkpoint files is always complete.