#lldp

The following operations can be performed on "lldp":


##stat lldp

DIsplay lldp statistics.


##Synopsys

stat lldp [&lt;ifnum>@] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>ifnum</b>
LLDP Statistics per interfaces

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

<b>LLDP received Packets (RxPkts)</b>
Total LLDP Packets received.

<b>LLDP bytes received (RxBytes)</b>
Total LLDP bytes received

<b>LLDP packets transmitted (TxPkts)</b>
Total LLDP Packets transmitted

<b>LLDP bytes transmitted (TxBytes)</b>
Total LLDP bytes transmitted.

<b>Errors in LLDP Packets (RxErrPkts)</b>
Total errors in LLDP packets.

<b>Discarded LLDP Packets (DiscardPkts)</b>
Total discarded LLDP packets.

<b>TLVs not Recognised (TlvNotRecognised)</b>
Total TLVs not Recognised.



