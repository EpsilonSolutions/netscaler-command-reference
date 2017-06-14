#bridgegroup

The following operations can be performed on "bridgegroup":


[add](#add-bridgegroup) | [rm](#rm-bridgegroup) | [set](#set-bridgegroup) | [unset](#unset-bridgegroup) | [bind](#bind-bridgegroup) | [unbind](#unbind-bridgegroup) | [show](#show-bridgegroup)

##add bridgegroup

Create a Bridge group.


##Synopsys

add bridgegroup &lt;id> [-ipv6DynamicRouting ( ENABLED | DISABLED )]


##Arguments

<b>id</b>
An integer that uniquely identifies the bridge group.
Minimum value: 1
Maximum value: 1000

<b>ipv6DynamicRouting</b>
Enable all IPv6 dynamic routing protocols on all VLANs bound to this bridgegroup. Note: For the ENABLED setting to work, you must configure IPv6 dynamic routing protocols from the VTYSH command line.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add bridgegroup bg1

##rm bridgegroup

Remove the bridge group created by the add bridge group command.


##Synopsys

rm bridgegroup &lt;id>


##Arguments

<b>id</b>
An integer that uniquely identifies the bridge group that you want to remove from the NetScaler appliance.
Minimum value: 1
Maximum value: 1000



##set bridgegroup

Set Bridge group parameters.


##Synopsys

set bridgegroup &lt;id> -ipv6DynamicRouting ( ENABLED | DISABLED )


##Arguments

<b>id</b>
An integer value that uniquely identifies the bridge group. Minimum value: 1. Maximum value: 1000.
Minimum value: 1
Maximum value: 1000

<b>ipv6DynamicRouting</b>
Enable all IPv6 dynamic routing protocols on this bridge group. For this setting to work, you must configure IPv6 dynamic routing protocols from the VTYSH command line. For more information about configuring IPv6 dynamic routing protocols on the NetScaler appliance, see the Dynamic Routing chapter of the Citrix NetScaler Networking Guide.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set bridgegroup bg1 -dynamicRouting ENABLED

##unset bridgegroup

Use this command to remove  bridgegroup settings.Refer to the set  bridgegroup command for meanings of the arguments.


##Synopsys

unset bridgegroup &lt;id> -ipv6DynamicRouting


##bind bridgegroup

Bind a vlan or an ip address to a bridgegroup.


##Synopsys

bind bridgegroup &lt;id> [-vlan &lt;positive_integer>] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]  [-td &lt;positive_integer>]]


##Arguments

<b>id</b>
The integer that uniquely identifies the bridge group.
Minimum value: 1
Maximum value: 1000

<b>vlan</b>
An integer that uniquely identifies the VLAN that you want to bind to this bridge group.
Minimum value: 2
Maximum value: 4094

<b>IPAddress</b>
A network address or addresses to be associated with the bridge group. You must add entries for these network addresses in the routing table before running this command.



##Example

bind bridgegroup bg1 -vlan 2

##unbind bridgegroup

Unbinds the specified VLANs or IP addresses from a bridge group.


##Synopsys

unbind bridgegroup &lt;id> [-vlan &lt;positive_integer>] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]  [-td &lt;positive_integer>]]


##Arguments

<b>id</b>
Integer that uniquely identifies the bridge group.
Minimum value: 1
Maximum value: 1000

<b>vlan</b>
ID of the VLAN to unbind from this bridge group.
Minimum value: 2
Maximum value: 4094

<b>IPAddress</b>
Network address associated with the bridge group.



##show bridgegroup

Display the configured bridge group. If a name is specified, only that particular bridge group information is displayed. Otherwise, all configured bridge groups are displayed.


##Synopsys

show bridgegroup [&lt;id>]


##Arguments

<b>id</b>
The name of the bridge group.
Minimum value: 1
Maximum value: 1000

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>IPAddress</b>
The IP address assigned to the  bridge group.

<b>netmask</b>
The network mask for the subnet defined for the bridge group.

<b>flags</b>
Temporary flag used for internal purpose.

<b>portbitmap</b>
Member interfaces of this  bridge group.

<b>tagbitmap</b>
Tagged members of this  bridge group.

<b>ifaces</b>
Names of all member interfaces of this bridge group.

<b>tagIfaces</b>
Names of all tagged member interfaces of this bridge group.

<b>vlan</b>
Names of all member VLANs.

<b>ipv6DynamicRouting</b>
Whether dynamic routing is enabled or disabled.

<b>rnat</b>
Temporary flag used for internal purpose.

<b>flag</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

An example of the output of the show bridge group command is as follows:2 configured Bridge Group:1)      Bridge Group: 1        Member vlans : 2 3 4		IP: 10.102.33.27 MASK: 255.255.255.02)      Bridge Group: 2        Member vlans : 5 6

