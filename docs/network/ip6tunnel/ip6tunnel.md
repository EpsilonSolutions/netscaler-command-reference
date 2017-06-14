#ip6Tunnel

The following operations can be performed on "ip6Tunnel":


[add](#add-ip6tunnel) | [rm](#rm-ip6tunnel) | [show](#show-ip6tunnel)

##add ip6Tunnel

Creates an IPv6 tunnel. An IP tunnel is a communication channel, using encapsulation technologies, between two networks that do not have a routing path. Every IP packet that is shared between the two networks is encapsulated within another packet and then sent through the tunnel.


##Synopsys

add ip6Tunnel &lt;name> &lt;remote> &lt;local>


##Arguments

<b>name</b>
Name for the IPv6 Tunnel. Cannot be changed after the service group is created. Must begin with a number or letter, and can consist of letters, numbers, and the @ _ - . (period) : (colon) # and space ( ) characters.

<b>remote</b>
An IPv6 address of the remote NetScaler appliance used to set up the tunnel.

<b>local</b>
An IPv6 address of the local NetScaler appliance used to set up the tunnel.



##Example

add ip6tunnel tun6 9901::200/64 *

##rm ip6Tunnel

Removes an IPv6 tunnel from the NetScaler appliance.


##Synopsys

rm ip6Tunnel &lt;name>


##Arguments

<b>name</b>
Name of the IPv6 tunnel to be removed.



##Example

rm ip6tunnel tun6

##show ip6Tunnel

Displays the settings of all IPv6 tunnels configured on the NetScaler appliance, or of the specified IPv6 tunnel.


##Synopsys

show ip6Tunnel [&lt;name> | &lt;remote>]


##Arguments

<b>name</b>
Name of the IPv6 tunnel whose details you want to display.

<b>remote</b>
The IPv6 address at which the remote NetScaler appliance connects to the tunnel.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>remoteIP</b>
The remote IP address or subnet of the tunnel.

<b>local</b>
An IPv6 address of the local NetScaler appliance used to set up the tunnel.

<b>type</b>
The type of this tunnel.

<b>encapIp</b>
The effective local IP address of the tunnel. Used as the source of the encapsulated packets.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

1)  Name.........:  tun61    Remote.......:     9901::200/64  Local........:            *    Encap.....:        ::0/128       Type......:               C2)  Name.........:  tun62    Remote.......:     9903::400/84  Local........:    9903::100    Encap.....:        ::0/128       Type......:               C3)  Name.........:    Remote.......:   9902::300/90    Local........:            *    Encap.....:      9902::100       Type......:               I

