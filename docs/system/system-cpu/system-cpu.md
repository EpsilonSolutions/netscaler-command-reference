#system cpu

The following operations can be performed on "system cpu":


##stat system cpu

Displays statistics of all CPUs available on the appliance, or statistics of the specified CPU.


##Synopsys

stat system cpu [&lt;id>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>id</b>
ID of the CPU for which to display statistics.
Default value: 65535
Maximum value: 65534

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>CPU Usage (Usage)</b>
CPU utilization percentage.



##Related Commands

<ul><li><a href="../../../s/s">stat system</a></li><li><a href="../../../at-syst/at-syst">stat system bw</a></li><li><a href="../../../l#stat-system-m/l#stat-system-m">stat system memory</a></li></ul>



