#bridge

The following operations can be performed on "bridge":


##stat bridge

Display bridging statistics.


##Synopsys

stat bridge [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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



