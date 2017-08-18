#vpn pcoipConnection

The following operations can be performed on "vpn pcoipConnection":


[show](#show-vpn-pcoipconnection) | [kill](#kill-vpn-pcoipconnection)

##show vpn pcoipConnection

Displays active PCOIP connections.


##Synopsys

show vpn pcoipConnection [-userName &lt;string>]


##Arguments

<b>userName</b>
User name for the PCOIP connections.



##Outputs

<b>srcIP</b>
The client IP address.

<b>srcPort</b>
The client port.

<b>destIP</b>
The VDA IP address.

<b>destPort</b>
The VDA server port.

<b>peId</b>
Core id of the session owner

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##kill vpn pcoipConnection

Terminates the specified connections.


##Synopsys

kill vpn pcoipConnection [-userName &lt;string>] [-all]


##Arguments

<b>userName</b>
User name for the PCOIP connections.

<b>all</b>
All active pcoip connections.



##Example

kill pcoipconnection -username joe

