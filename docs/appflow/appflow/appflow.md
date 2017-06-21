#appflow

The following operations can be performed on "appflow":


##stat appflow

Display AppFlow statistics.


##Synopsys

stat appflow [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>AppFlow octets transmitted (aflwOcts)</b>
The total number of AppFlow (IPFIX) octets that the NetScaler has transmitted.

<b>AppFlow flows transmitted (aflwFlws)</b>
The total number of AppFlow (IPFIX) flows that the NetScaler has transmitted.

<b>AppFlow messages transmitted (aflwMsgs)</b>
The total number of AppFlow (IPFIX) messages that the NetScaler has transmitted.

<b>Octets ignored for AppFlow (aflwIgnOct)</b>
The total number of octets that the NetScaler has ignored for AppFlow (IPFIX).

<b>Packets ignored for AppFlow (aflwIgnPkts)</b>
The total number of packets that the NetScaler has ignored for AppFlow (IPFIX).

<b>AppFlow octets not transmitted (aflwNoTxOcts)</b>
The total number of AppFlow (IPFIX) octets that the NetScaler has not transmitted.

<b>AppFlow flows not transmitted (aflwNoTxFlows)</b>
The total number of AppFlow (IPFIX) flows that the NetScaler has not transmitted.

<b>AppFlow packets not transmitted (aflwNoTxPkts)</b>
The total number of AppFlow (IPFIX) packets that the NetScaler has not transmitted.



