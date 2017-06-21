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
Minimum value: 0
Maximum value: 65534

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

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



