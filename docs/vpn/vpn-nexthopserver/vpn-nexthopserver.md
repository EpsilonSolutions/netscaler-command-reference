#vpn nextHopServer

The following operations can be performed on "vpn nextHopServer":


[add](#add-vpn-nexthopserver) | [rm](#rm-vpn-nexthopserver) | [show](#show-vpn-nexthopserver)

##add vpn nextHopServer

Enables a NetScaler Gateway appliance in the first DMZ to communicate with one or more NetScaler Gateway appliances in the second DMZ.


##Synopsys

add vpn nextHopServer &lt;name> &lt;nextHopIP> &lt;nextHopPort> [-secure ( ON | OFF )]


##Arguments

<b>name</b>
Name for the NetScaler Gateway appliance in the first DMZ.
Maximum value: 32

<b>nextHopIP</b>
IP address or FQDN of the NetScaler Gateway proxy in the second DMZ.

<b>nextHopPort</b>
Port number of the NetScaler Gateway proxy in the second DMZ.
Minimum value: 1
Maximum value: 65535

<b>secure</b>
Use of a secure port, such as 443, for the double-hop configuration.
Possible values: ON, OFF
Default value: OFF



##Example

add vpn nexthopserver dh1 10.1.1.1 80 -secure OFF

##rm vpn nextHopServer

Removes a configured next hop server.


##Synopsys

rm vpn nextHopServer &lt;name>


##Arguments

<b>name</b>
Name of the next hop server to remove.
Maximum value: 32



##Example

rm vpn nexthopserver dh1

##show vpn nextHopServer

Displays information about all the configured next NetScaler Gateway hop servers, or detailed information about the specified NetScaler Gateway next hop server.


##Synopsys

show vpn nextHopServer [&lt;name>]


##Arguments

<b>name</b>
Name of the NetScaler Gateway next hop server for which to display detailed information.
Maximum value: 32

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>nextHopIP</b>
Next hop IP address.

<b>nextHopPort</b>
Next hop port number.

<b>secure</b>
Next hop over secure connection.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

show vpn nexthopserver dh1

