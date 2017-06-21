#vpn icaConnection

The following operations can be performed on "vpn icaConnection":


[show](#show-vpn-icaconnection) | [kill](#kill-vpn-icaconnection)

##show vpn icaConnection

Displays active connections that use the ICA proxy.


##Synopsys

show vpn icaConnection [-userName &lt;string>]


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
The CPS server IP address.

<b>destPort</b>
The CPS server port.

<b>peId</b>
Core id of the session owner

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##kill vpn icaConnection

Terminates the specified ica connections.


##Synopsys

kill vpn icaConnection [-userName &lt;string>] [-all]


##Arguments

<b>userName</b>
User name for which ica connections needs to be terminated.

<b>all</b>
Terminate all active icaconnections.



##Example

kill icaconnection -username joe

