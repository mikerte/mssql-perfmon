# mssql-perfmon

1. Extensive Performance Counters List
CPU-Related Counters
These counters provide insights into how SQL Server uses the CPU resources, which is vital for identifying CPU bottlenecks.

Processor(_Total)\% Processor Time – Overall CPU utilization.
Processor(_Total)\% Privileged Time – Time spent executing system code (important for I/O-intensive workloads).
Processor(_Total)\% User Time – Time spent executing user-mode processes (helps identify application CPU usage).
Processor(_Total)\Interrupts/sec – Number of interrupts received, which can indicate hardware issues.
System\Processor Queue Length – Number of threads waiting for processor time (indicates CPU pressure).
SQLServer: SQL Statistics\Batch Requests/sec – Number of SQL Server batches received (correlates SQL Server load with CPU performance).
SQLServer: SQL Statistics\SQL Compilations/sec – Number of SQL Server compilations (high values indicate plan cache inefficiency).

Memory-Related Counters
SQL Server relies heavily on memory, and these counters help to monitor how the OS manages memory.

Memory\Available MBytes – Free memory available to the system.
Memory\Pages/sec – Pages read from or written to disk due to memory pressure (indicates paging).
Memory\Page Faults/sec – Frequency of page faults, important when investigating memory pressure.
Memory\Cache Faults/sec – Cache faults can indicate issues with memory optimization.
SQLServer: Buffer Manager\Page Life Expectancy – Indicates how long a page remains in memory (should be high).
SQLServer: Buffer Manager\Buffer Cache Hit Ratio – Percentage of SQL Server requests that are found in memory (should be high).
SQLServer: Memory Manager\Memory Grants Pending – SQL Server queries waiting for memory (indicates memory pressure).
SQLServer: Memory Manager\Total Server Memory (KB) – Memory currently allocated by SQL Server.

Disk I/O-Related Counters
Disk I/O is critical for SQL Server performance, particularly for databases and transaction logs.

PhysicalDisk(_Total)\Avg. Disk sec/Read – Time to read data from disk (indicates storage performance).
PhysicalDisk(_Total)\Avg. Disk sec/Write – Time to write data to disk.
PhysicalDisk(_Total)\Disk Transfers/sec – Overall I/O activity (read and write operations per second).
PhysicalDisk(_Total)\Current Disk Queue Length – Number of I/O operations waiting to be processed (should be low).
SQLServer: Databases\Transactions/sec – Number of transactions, helps correlate I/O activity to SQL Server load.
SQLServer: Databases\Log Bytes Flushed/sec – Transaction log write activity.
SQLServer: Databases\Log Flush Waits/sec – Indicates how often the transaction log waits for I/O operations.

Network-Related Counters
Network counters are important for SQL Server environments where data is transmitted between different servers, clients, or replicas.

Network Interface(_Total)\Bytes Received/sec – Network data received per second (useful in distributed systems like Always On Availability Groups).
Network Interface(_Total)\Bytes Sent/sec – Network data sent per second.
Network Interface(_Total)\Packets Outbound Errors – Number of errors when sending packets.
Network Interface(_Total)\Packets Received Errors – Number of errors in received packets.

SQL Server-Specific OS-Level Counters
SQL Server exposes performance counters that are vital for its health and performance, which you can capture at the OS level.

SQLServer: SQL Statistics\Auto-Param Attempts/sec – Attempts to automatically parameterize SQL statements (can indicate query performance issues).
SQLServer: Locks\Lock Waits/sec – Lock contention within SQL Server.
SQLServer: Locks\Deadlocks/sec – Number of deadlocks (serious performance issue).
SQLServer: General Statistics\User Connections – Current user connections to the SQL Server.
SQLServer: Plan Cache\Cache Hit Ratio – Effectiveness of SQL Server’s plan cache (should be high).
SQLServer: Plan Cache\Cache Pages – Number of pages used by the SQL Server plan cache.
SQLServer: Buffer Manager\Checkpoint Pages/sec – Pages flushed during a checkpoint.

Cluster and Availability Group Specific Counters (If Relevant)
If you’re using SQL Server clusters or Availability Groups (AGs), it’s critical to capture these counters as well.

Cluster Service\Cluster Network Traffic – Measures network traffic within the cluster.
Cluster Service\Cluster API Calls/sec – Calls made to the cluster API.
SQLServer: Availability Replica\Bytes Sent to Replica/sec – Data sent to other replicas.
SQLServer: Availability Replica\Bytes Received from Replica/sec – Data received from replicas.
SQLServer: Database Replica\Log Send Queue KB – Size of the unsent transaction log.
SQLServer: Database Replica\Redo Queue KB – Amount of log waiting to be applied on a secondary replica.
