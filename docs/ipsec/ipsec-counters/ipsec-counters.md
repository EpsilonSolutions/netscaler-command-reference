#ipsec counters

The following operations can be performed on "ipsec counters":


##stat ipsec counters

Display statistics for secure tunnel sessions.


##Synopsys

stat ipsec counters [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>Bytes Received (ipsecRxBytes)</b>
Bytes received during IPsec sessions.

<b>Bytes Sent (ipsecTxBytes)</b>
Bytes sent during IPsec sessions.

<b>Packets Received (ipsecRxPkts)</b>
Packets received during IPsec sessions.

<b>Packets Sent (ipsecTxPkts)</b>
Packets sent during IPsec sessions.



##Example

stat ipsec

