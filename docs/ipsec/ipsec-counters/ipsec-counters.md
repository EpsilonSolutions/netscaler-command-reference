#ipsec counters

The following operations can be performed on "ipsec counters":


##stat ipsec counters

Display statistics for secure tunnel sessions.


##Synopsys

stat ipsec counters [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

