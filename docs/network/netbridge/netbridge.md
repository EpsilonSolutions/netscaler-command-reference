#netbridge

The following operations can be performed on "netbridge":


[add](#add-netbridge) | [set](#set-netbridge) | [unset](#unset-netbridge) | [rm](#rm-netbridge) | [show](#show-netbridge) | [bind](#bind-netbridge) | [unbind](#unbind-netbridge)

##add netbridge

Add a network bridge.


##Synopsys

add netbridge &lt;name> [-vxlanVlanMap &lt;string>]


##Arguments

<b>name</b>
The name of the network bridge.

<b>vxlanVlanMap</b>
The vlan to vxlan mapping to be applied to this netbridge.



##Example

add netbridge bridge1

##set netbridge

Set network bridge parameters.


##Synopsys

set netbridge &lt;name> [-vxlanVlanMap &lt;string>]


##Arguments

<b>name</b>
The name of the network bridge.

<b>vxlanVlanMap</b>
The vlan to vxlan mapping to be applied to this netbridge.



##Example

set netbridge bridge1 -vlanVxlanMap p1

##unset netbridge

Use this command to remove  netbridge settings.Refer to the set  netbridge command for meanings of the arguments.


##Synopsys

unset netbridge &lt;name> -vxlanVlanMap


##rm netbridge

Remove a network bridge.


##Synopsys

rm netbridge &lt;name>


##Arguments

<b>name</b>
The name of the network bridge.



##Example

remove netbridge bridge1

##show netbridge

Show configured network bridges.


##Synopsys

show netbridge [&lt;name>]


##Arguments

<b>name</b>
The name of the network bridge.



##Outputs

<b>vxlanVlanMap</b>
The vlan to vxlan mapping to be applied to this netbridge.

<b>tunnel</b>
The name of the tunnel that is a part of this bridge.

<b>vlan</b>
The VLAN that is extended by this network bridge.

<b>IPAddress</b>
The subnet that is extended by this network bridge.

<b>netmask</b>
The network mask for the subnet.

<b>stateflag</b>
Used internally for display.

<b>devno</b>

<b>count</b>



##bind netbridge

Bind a network bridge to its attributes.


##Synopsys

bind netbridge &lt;name> [-tunnel &lt;string> ...] [-vlan &lt;positive_integer> ...] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]]


##Arguments

<b>name</b>
The name of the network bridge.

<b>tunnel</b>
The name of the tunnel that needs to be a part of this network bridge.

<b>vlan</b>
The VLAN that needs to be extended.
Minimum value: 1
Maximum value: 4094

<b>IPAddress</b>
The subnet that needs to be extended.

<b>netmask</b>
Subnet mask in dotted-decimal format. For example: 255.255.255.0. This parameter is required for IPv4.



##Example

bind netbridge bridge1 -tunnel tun0

##unbind netbridge

Unbind a network bridge from its attributes.


##Synopsys

unbind netbridge &lt;name> [-tunnel &lt;string> ...] [-vlan &lt;positive_integer> ...] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]]


##Arguments

<b>name</b>
The name of the network bridge.

<b>tunnel</b>
The name of the tunnel that is part of this network bridge.

<b>vlan</b>
The vlan that is part of this network bridge.
Minimum value: 1
Maximum value: 4094

<b>IPAddress</b>
The subnet that is part of this network bridge.

<b>netmask</b>
Subnet mask in dotted-decimal format. For example: 255.255.255.0. This parameter is required for IPv4.



##Example

unbind netbridge bridge1 -tunnel tun0

