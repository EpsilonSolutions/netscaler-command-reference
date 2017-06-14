#ipTunnel

The following operations can be performed on "ipTunnel":


[add](#add-iptunnel) | [rm](#rm-iptunnel) | [show](#show-iptunnel)

##add ipTunnel

Creates an IPv4 tunnel. An IP tunnel is a communication channel, using encapsulation technologies, between two networks that do not have a routing path. Every IP packet that is shared between the two networks is encapsulated within another packet and then sent through the tunnel.


##Synopsys

add ipTunnel &lt;name> &lt;remote> &lt;remoteSubnetMask> &lt;local> [-protocol &lt;protocol>  [-vlan &lt;positive_integer>]] [-ipsecProfileName &lt;string>]


##Arguments

<b>name</b>
Name for the IP tunnel. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).

<b>remote</b>
Public IPv4 address, of the remote device, used to set up the tunnel. For this parameter, you can alternatively specify a network address.

<b>remoteSubnetMask</b>
Subnet mask of the remote IP address of the tunnel.

<b>local</b>
Type ofNetScaler owned public IPv4 address, configured on the local NetScaler appliance and used to set up the tunnel.

<b>protocol</b>
Name of the protocol to be used on this tunnel.
Possible values: IPIP, GRE, IPSEC, VXLAN
Default value: TNL_IPIP

<b>ipsecProfileName</b>
Name of IPSec profile to be associated.
Default value: "ns_ipsec_default_profile"

<b>vlan</b>
The vlan for mulicast packets
Minimum value: 1
Maximum value: 4094



##Example

add iptunnel tunnel1 10.100.20.0 255.255.255.0 *

##rm ipTunnel

Removes an IP tunnel configuration from the NetScaler appliance.


##Synopsys

rm ipTunnel &lt;name>


##Arguments

<b>name</b>
Name of the IP Tunnel.



##Example

rm iptunnel tunnel1

##show ipTunnel

Display the configured IP tunnels.


##Synopsys

show ipTunnel [(&lt;remote>  &lt;remoteSubnetMask>) | &lt;name>]


##Arguments

<b>remote</b>
Public IPv4 address, of the remote device, used to set up the tunnel. For this parameter, you can alternatively specify a network address.

<b>name</b>
Name for the IP tunnel. Leading character must be a number or letter. Other characters allowed, after the first character, are @ _ - . (period) : (colon) # and space ( ).

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>name</b>
Name for the PBR

<b>local</b>
Type ofNetScaler owned public IPv4 address, configured on the local NetScaler appliance and used to set up the tunnel.

<b>protocol</b>
Name of the protocol to be used on this tunnel.

<b>type</b>
The type of this tunnel.

<b>encapIp</b>
The effective local IP address of the tunnel. Used as the source of the encapsulated packets.

<b>channel</b>
The tunnel that is bound to a netbridge.

<b>ipsecProfileName</b>
Name of IPSec profile to be associated.

<b>vlan</b>
The vlan for mulicast packets

<b>tunnelType</b>
Indicates that a tunnel is User-Configured, Internal or DELETE-IN-PROGRESS.

<b>ipsecTunnelStatus</b>
Whether the ipsec on this tunnel is up or down.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

1)  Name.........:  t1    Remote.......:     10.102.33.0   Mask......:   255.255.255.0    Local........:               *   Encap.....:         0.0.0.0    Protocol.....:            IPIP   Type......:               C2)  Name.........:  tunnel1    Remote.......:     10.100.20.0   Mask......:   255.255.255.0    Local........:               *   Encap.....:         0.0.0.0    Protocol.....:            IPIP   Type......:               C3)  Name.........:    Remote.......:   10.102.33.190   Mask......: 255.255.255.255    Local........:               *   Encap.....:    10.102.33.85    Protocol.....:            IPIP   Type......:               I

