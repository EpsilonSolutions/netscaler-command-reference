#ipsecalg counters

The following operations can be performed on "ipsecalg counters":


##stat ipsecalg counters

Display statistics for ipsec alg.


##Synopsys

stat ipsecalg counters [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of IPSec ALG Profile.

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

<b>Total Sessions (Total)</b>
Total session for IPSec ALG.

<b>Dropped Sessions (Dropped)</b>
Total Dropped IPsec ALG sessions.

<b>Active Sessions (Active)</b>
Currently active IPsec ALG sessions.

<b>Blocked Sessions (Blocked)</b>
Currently blocked sessions on ESP Gate.

<b>Packets Received (RxPkts)</b>
Total Packets received during IPsec ALG sessions.

<b>Packets Sent (TxPkts)</b>
Total Packets sent during IPsec ALG sessions.



##Example

stat ipsecalg counters

