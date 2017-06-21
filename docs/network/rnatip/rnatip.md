#rnatip

The following operations can be performed on "rnatip":


##stat rnatip

Display statistics for RNAT sessions.


##Synopsys

stat rnatip [&lt;rnatip>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>rnatip</b>
Specifies the NAT IP address of the configured RNAT entry for which you want to see the statistics. If you do not specify an IP address, this displays the statistics for all the configured RNAT entries.

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

<b>Traffic domain (td)</b>
Traffic domain for ipaddr.

<b>Bytes Received (rxBytes)</b>
Bytes received on this IP address during RNAT sessions.

<b>Bytes Sent (txBytes)</b>
Bytes sent from this IP address during RNAT sessions.

<b>Packets Received (rxPkts)</b>
Packets received on this IP address during RNAT sessions.

<b>Packets Sent (txPkts)</b>
Packets sent from this IP address during RNAT sessions.

<b>Syn Sent (txSyn)</b>
Requests for connections sent from this IP address during RNAT sessions.

<b>Current RNAT sessions (sessions)</b>
Currently active RNAT sessions started from this IP address.



##Example

stat rnatip 1.1.1.1

