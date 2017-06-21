#bridge

The following operations can be performed on "bridge":


##stat bridge

Display bridging statistics.


##Synopsys

stat bridge [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

<b>Loops</b>
The number of times bridging registered MAC moved

<b>Collisions (Collisns)</b>
The number of bridging table collisions

<b>Interface muted (Mutes)</b>
The number of bridging related interface mutes

<b>Total bridged packets (Tot_pkts)</b>
The total number of bridged packets

<b>Total bridged Mbits (Tot_Mbits)</b>
The total number of bridged Mbits



