#rdp connections

The following operations can be performed on "rdp connections":


[show](#show-rdp-connections) | [kill](#kill-rdp-connections)

##show rdp connections

Displays active connections that use the RDP proxy.


##Synopsys

show rdp connections [-userName &lt;string>]


##Arguments

<b>userName</b>
User name for which to display connections.



##Outputs

<b>domain</b>
The domain name.

<b>srcIP</b>
The client IP address.

<b>srcPort</b>
The client port.

<b>destIP</b>
The Server IP address.

<b>destPort</b>
The Client IP address.

<b>peId</b>
Core id of the session owner

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##kill rdp connections

Terminates the specified rdp connections.


##Synopsys

kill rdp connections [-userName &lt;string>] [-all]


##Arguments

<b>userName</b>
User name for which rdp connections needs to be terminated.

<b>all</b>
Terminate all active rdpconnections.



##Example

kill rdpconnection -username joe

