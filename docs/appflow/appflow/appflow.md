#appflow

The following operations can be performed on "appflow":


##stat appflow

Display AppFlow statistics.


##Synopsys

stat appflow [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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



