#system memory

The following operations can be performed on "system memory":


##stat system memory

Displays system-memory statistics.


##Synopsys

stat system memory [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Shared Memory InUse (%) (shMemAllocpcnt)</b>
Shared memory insue percent.

<b>Shared Memory InUse (MB) (shMemAllocMB)</b>
Shared memory insue, in megabytes.

<b>Total Shared Memory (MB) (shMemtotMB)</b>
Total shared memory allowed to allocate, in megabytes.

<b>Free Memory (MB) (MemTotFree)</b>
Total Free PE Memory in the System.

<b>InUse Memory (%) (MemUsage)</b>
Percentage of memory utilization on NetScaler.

<b>InUse Memory (MB) (MemTotUseMB)</b>
Total NetScaler Memory in use, in megabytes.

<b>Memory Allocated (%) (MemTotAlloc(%))</b>
Currently allocated memory in percent.

<b>Memory Allocated (MB) (MemTotAlloc)</b>
Currently allocated memory, in megabytes.

<b>Memory Currently Available (MB) (MemTotMB)</b>
Total memory available (grabbed) for use by packet engine (PE), in megabytes.

<b>Maximum Memory Available (MB) (MemTotAvail)</b>
Total system memory available for PE to grab from the system.



##Example

stat system memory

##Related Commands

<ul><li><a href="../../../s/s">stat system</a></li><li><a href="../../../at-syst/at-syst">stat system bw</a></li><li><a href="../../../tat-syste/tat-syste">stat system cpu</a></li></ul>



