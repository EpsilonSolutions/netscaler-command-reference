#rnatip

The following operations can be performed on "rnatip":


##stat rnatip

Display statistics for RNAT sessions.


##Synopsys

stat rnatip [&lt;rnatip>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>rnatip</b>
Specifies the NAT IP address of the configured RNAT entry for which you want to see the statistics. If you do not specify an IP address, this displays the statistics for all the configured RNAT entries.

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

