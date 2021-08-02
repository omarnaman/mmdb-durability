# SolidDB

SolidDB mainly uses Hot-StandBy (HSB) cluster for availability and "durability"


[Logging](https://support.unicomsi.com/manuals/soliddb/100/index.html#page/High_Availability_Guide/1_Introduction.02.07.html) is done on row-level of changes on three modes:
* Strict (safe)
* Relaxed (fast) supported by HSB
* Adaptive (only with HSB primary): **Relaxed** if primary, strict otherwise 