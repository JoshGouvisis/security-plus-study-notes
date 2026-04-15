
# 3.4 Resilience and Recovery

Resilience ensures the system stays up (Availability); Recovery ensures it can be restored if it fails.

## Resilience Strategies
* **High Availability (HA):** Using redundancy (load balancers, clusters) to ensure services remain accessible.
* **Snapshots:** Instant backups of a system state; used for fast recovery in virtualized environments.
* **Replication:** Real-time synchronization of data across multiple locations.

## Power & Physical Resiliency
* **UPS:** Short-term battery power to handle surges or blackouts.
* **Generators:** Long-term power backup for entire facilities.
* **RAID:** Redundancy at the disk level (e.g., RAID 1 for mirroring, RAID 5 for striping with parity).
