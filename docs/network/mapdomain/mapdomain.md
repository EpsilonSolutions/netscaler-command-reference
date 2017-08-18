#MapDomain

The following operations can be performed on "MapDomain":


[add](#add-mapdomain) | [rm](#rm-mapdomain) | [show](#show-mapdomain) | [stat](#stat-mapdomain) | [bind](#bind-mapdomain) | [unbind](#unbind-mapdomain)

##add MapDomain

Add MAP Domain.


##Synopsys

add MapDomain &lt;name> -MapDmrName &lt;string>


##Arguments

<b>name</b>
Name for the MAP Domain. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Domain is created . The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDomain map1").

<b>MapDmrName</b>
Default Mapping rule name.



##Example

add network MapDomain map1 -MapBmrName dmr1

##rm MapDomain

Remove MAP Domain.


##Synopsys

rm MapDomain &lt;name>


##Arguments

<b>name</b>
Name for the MAP Domain. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Domain is created . The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDomain map1").



##Example

rm network MapDomain map1

##show MapDomain

Display MAP Domain.


##Synopsys

show MapDomain [&lt;name>]


##Arguments

<b>name</b>
Name for the MAP Domain. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Domain is created . The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDomain map1").



##Outputs

<b>MapDmrName</b>
Default Mapping rule name.

<b>MapBmrName</b>
Basic Mapping rule name.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show network MapDomain map1

##stat MapDomain

Display MAP Domain statistics.


##Synopsys

stat MapDomain [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
An integer specifying the VLAN identification number (VID). Possible values: 1 through 4094.

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

<b>MAP-T IPv6 TCP Rx packets (v6rxPktsTcp)</b>
Total number of MAP-T IPv6 TCP Recieved packets.

<b>MAP-T IPv6 TCP Tx packets (v6txPktsTcp)</b>
Total number of MAP-T IPv6 TCP Transmitted packets.

<b>MAP-T IPv6 TCP Rx Bytes (v6rxBytesTcp)</b>
Total number of MAP-T IPv6 TCP Recieved Bytes.

<b>MAP-T IPv6 TCP Tx Bytes (v6txBytesTcp)</b>
Total number of MAP-T IPv6 TCP Transmitted Bytes.

<b>MAP-T IPv4 TCP Rx packets (v4rxPktsTcp)</b>
Total number of MAP-T IPv4 TCP Recieved packets.

<b>MAP-T IPv4 TCP Tx packets (v4txPktsTcp)</b>
Total number of MAP-T IPv4 TCP Transmitted packets.

<b>MAP-T IPv4 TCP Rx Bytes (v4rxBytesTcp)</b>
Total number of MAP-T IPv4 TCP Recieved Bytes.

<b>MAP-T IPv4 TCP Tx Bytes (v4txBytesTcp)</b>
Total number of MAP-T IPv4 TCP Transmitted Bytes.

<b>MAP-T IPv6 UDP Rx packets (v6rxPktsUdp)</b>
Total number of MAP-T IPv6 UDP Recieved packets.

<b>MAP-T IPv6 UDP Tx packets (v6txPktsUdp)</b>
Total number of MAP-T IPv6 UDP Transmitted packets.

<b>MAP-T IPv6 UDP Rx Bytes (v6rxBytesUdp)</b>
Total number of MAP-T IPv6 UDP Recieved Bytes.

<b>MAP-T IPv6 UDP Tx Bytes (v6txBytesUdp)</b>
Total number of MAP-T IPv6 UDP Transmitted Bytes.

<b>MAP-T IPv4 UDP Rx packets (v4rxPktsUdp)</b>
Total number of MAP-T IPv4 UDP Recieved packets.

<b>MAP-T IPv4 UDP Tx packets (v4txPktsUdp)</b>
Total number of MAP-T IPv4 UDP Transmitted packets.

<b>MAP-T IPv4 UDP Rx Bytes (v4rxBytesUdp)</b>
Total number of MAP-T IPv4 UDP Recieved Bytes.

<b>MAP-T IPv4 UDP Tx Bytes (v4txBytesUdp)</b>
Total number of MAP-T IPv4 UDP Transmitted Bytes.

<b>MAP-T IPv6 ICMP Rx packets (v6rxPktsIcmp)</b>
Total number of MAP-T IPv6 ICMP Recieved packets.

<b>MAP-T IPv6 ICMP Tx packets (v6txPktsIcmp)</b>
Total number of MAP-T IPv6 ICMP Transmitted packets.

<b>MAP-T IPv6 ICMP Rx Bytes (v6rxBytesIcmp)</b>
Total number of MAP-T IPv6 ICMP Recieved Bytes.

<b>MAP-T IPv6 ICMP Tx Bytes (v6txBytesIcmp)</b>
Total number of MAP-T IPv6 ICMP Transmitted Bytes.

<b>MAP-T IPv4 ICMP Rx packets (v4rxPktsIcmp)</b>
Total number of MAP-T IPv4 ICMP Recieved packets.

<b>MAP-T IPv4 ICMP Tx packets (v4txPktsIcmp)</b>
Total number of MAP-T IPv4 ICMP Transmitted packets.

<b>MAP-T IPv4 ICMP Rx Bytes (v4rxBytesIcmp)</b>
Total number of MAP-T IPv4 ICMP Recieved Bytes.

<b>MAP-T IPv4 ICMP Tx Bytes (v4txBytesIcmp)</b>
Total number of MAP-T IPv4 ICMP Transmitted Bytes.

<b>MAP-T Total V6 Recieved packets (v6rxPkts)</b>
Total number of MAP-T V6 Recieved packets.

<b>MAP-T Total V6 Transmitted packets (v6txPkts)</b>
Total number of MAP-T V6 Transmitted packets.

<b>MAP-T Total V4 Recieved packets (v4rxPkts)</b>
Total number of MAP-T V4 Recieved packets.

<b>MAP-T Total V4 Transmitted packets (v4txPkts)</b>
Total number of MAP-T V4 Transmitted packets.



##Example

stat mapdomain

##bind MapDomain

Bind MAP domain with BMR rule.


##Synopsys

bind MapDomain &lt;name> -MapBmrName &lt;string>


##Arguments

<b>name</b>
Name for the MAP Domain. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Domain is created . The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDomain map1").

<b>MapBmrName</b>
Basic Mapping rule name.



##Example

bind network MapDomain map1 -MapBmrName bmr1

##unbind MapDomain

unbind MAP Domain from BMR rule.


##Synopsys

unbind MapDomain &lt;name> -MapBmrName &lt;string>


##Arguments

<b>name</b>
Name for the MAP Domain. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Domain is created . The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDomain map1").

<b>MapBmrName</b>
Basic Mapping rule name.



##Example

unbind network MapDomain map1 -MapBmrName bmr1

