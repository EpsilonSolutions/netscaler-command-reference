#tunnelip6

The following operations can be performed on "tunnelip6":


##stat tunnelip6

Display the statistics related to IP tunnel.


##Synopsys

stat tunnelip6 [&lt;tunnelip6>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>tunnelip6</b>
remote IPv6 address of the configured tunnel.

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

<b>Packets received on tunnel (tnlRxPkts)</b>
Total number of packets received on the tunnel.

<b>Packets transmitted on tunnel (tnlTxPkts)</b>
Total number of packets transmitted on the tunnel.

<b>Bytes received on tunnel (tnlRxBytes)</b>
Total number of bytes received on the tunnel.

<b>Bytes transmitted on tunnel (tnlTxBytes)</b>
Total number of bytes transmitted on the tunnel.



##Example

stat tunnelip6 2001::1

