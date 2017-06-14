#tunnelip6

The following operations can be performed on "tunnelip6":


##stat tunnelip6

Display the statistics related to IP tunnel.


##Synopsys

stat tunnelip6 [&lt;tunnelip6>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>tunnelip6</b>
remote IPv6 address of the configured tunnel.

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

