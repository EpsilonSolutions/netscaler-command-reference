#ns memory

The following operations can be performed on "ns memory":


##stat ns memory

Displays memory statistics of NetScaler features.


##Synopsys

stat ns memory [&lt;pool>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>pool</b>
Feature name for which to display memory statistics.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Maximum Memory Available (MB) (MemTotAvail)</b>
Total system memory available for PE to grab from the system.

<b>Allocation failure (AllocF)</b>
Memory allocation failure for particular feature.

<b>Percentage of memory allocated (Alloc(%))</b>
Percentage of NetScaler memory used by the feature.

<b>Total memory Allocated (KB) (CurAlloc(KB))</b>
Total current NetScaler memory available for use by the feature, in kilobytes.



##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



