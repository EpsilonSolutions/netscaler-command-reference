#vlan

The following operations can be performed on "vlan":


[add](#add-vlan) | [rm](#rm-vlan) | [set](#set-vlan) | [unset](#unset-vlan) | [bind](#bind-vlan) | [unbind](#unbind-vlan) | [show](#show-vlan) | [stat](#stat-vlan)

##add vlan

Adds a VLAN to the NetScaler appliance.The newVLAN is not active unless interfaces are bound to it.


##Synopsys

add vlan &lt;id> [-aliasName &lt;string>] [-ipv6DynamicRouting ( ENABLED | DISABLED )] [-mtu &lt;positive_integer>]


##Arguments

<b>id</b>
A positive integer that uniquely identifies a VLAN.
Minimum value: 1
Maximum value: 4094

<b>aliasName</b>
A name for the VLAN. Must begin with a letter, a number, or the underscore symbol, and can consist of from 1 to 31 letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a name that helps identify the VLAN. However, you cannot perform any VLAN operation by specifying this name instead of the VLAN ID.

<b>ipv6DynamicRouting</b>
Enable all IPv6 dynamic routing protocols on this VLAN. Note: For the ENABLED setting to work, you must configure IPv6 dynamic routing protocols from the VTYSH command line.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mtu</b>
Specifies the maximum transmission unit (MTU), in bytes. The MTU is the largest packet size, excluding 14 bytes of ethernet header and 4 bytes of crc, that can be transmitted and received over this VLAN.
Default value: 0
Minimum value: 500
Maximum value: 9216



##rm vlan

Removes a VLAN from the NetScaler appliance. When the VLAN is removed, its interfaces are bound to VLAN 1. Note: VLAN 1 cannot be removed by any command.


##Synopsys

rm vlan &lt;id>


##Arguments

<b>id</b>
Integer that uniquely identifies the VLAN to be removed from the NetScaler appliance. When the VLAN is removed, its interfaces become members of VLAN 1.
Minimum value: 2
Maximum value: 4094



##set vlan

Modifies parameters of a VLAN on the NetScaler appliance.


##Synopsys

set vlan &lt;id> [-aliasName &lt;string>] [-ipv6DynamicRouting ( ENABLED | DISABLED )] [-mtu &lt;positive_integer>]


##Arguments

<b>id</b>
A positive integer that uniquely identifies a VLAN.
Minimum value: 1
Maximum value: 4094

<b>aliasName</b>
A name for the VLAN. Must begin with a letter, a number, or the underscore symbol, and can consist of from 1 to 31 letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a name that helps identify the VLAN. However, you cannot perform any VLAN operation by specifying this name instead of the VLAN ID.

<b>ipv6DynamicRouting</b>
Enable all IPv6 dynamic routing protocols on this bridge group. Note: For the ENABLED setting to work, you must configure IPv6 dynamic routing protocols from the VTYSH command line.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mtu</b>
Specifies the maximum transmission unit (MTU), in bytes. The MTU is the largest packet size, excluding 14 bytes of ethernet header and 4 bytes of crc, that can be transmitted and received over this VLAN.
Default value: 0
Minimum value: 500
Maximum value: 9216



##Example

set vlan 2 -dynamicRouting ENABLED

##unset vlan

Use this command to remove  vlan settings.Refer to the set  vlan command for meanings of the arguments.


##Synopsys

unset vlan &lt;id> [-aliasName] [-ipv6DynamicRouting] [-mtu]


##bind vlan

Binds the specified interfaces or IP addresses to a VLAN. An interface can be bound to a VLAN as a tagged or an untagged member. Adding an interface as an untagged member removes it from its current native VLAN and adds it to the new VLAN. If an interface is added as a tagged member to a VLAN, it still remains a member of its native VLAN.


##Synopsys

bind vlan &lt;id> [-ifnum &lt;interface_name> ...  [-tagged]] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]  [-td &lt;positive_integer>]]


##Arguments

<b>id</b>
Specifies the virtual LAN ID.
Minimum value: 1
Maximum value: 4094

<b>ifnum</b>
Interface to be bound to the VLAN, specified in slot/port notation (for example, 1/3).
Minimum value: 1

<b>IPAddress</b>
Network address to be associated with the VLAN. Should exist on the appliance before you associate it with the VLAN. To enable IP forwarding among VLANs, the specified address can be used as the default gateway by the hosts in the network.



##unbind vlan

Unbinds the specified interfaces or IP addresses from a VLAN. If any of the interfaces are untagged members of the VLAN, they are automatically bound to VLAN 1.


##Synopsys

unbind vlan &lt;id> [-ifnum &lt;interface_name> ...  [-tagged]] [-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]  [-td &lt;positive_integer>]]


##Arguments

<b>id</b>
The virtual LAN (VLAN) id.
Minimum value: 1
Maximum value: 4094

<b>ifnum</b>
Interface to unbind from the VLAN, specified in slot/port notation (for example, 1/3).
Minimum value: 1

<b>IPAddress</b>
The IP Address associated with the VLAN configuration.



##show vlan

Displays the settings of all VLANs configured on the NetScaler appliance, or of the specified VLAN. To display the settings of all the VLANs, run the command without any parameters. To display the settings of a particular VLAN, specify the ID of the VLAN.


##Synopsys

show vlan [&lt;id>]show vlan stats - alias for 'stat vlan'


##Arguments

<b>id</b>
Integer that uniquely identifies the VLAN for which the details are to be displayed.
Minimum value: 1
Maximum value: 4094

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>aliasName</b>
A name for the VLAN. Must begin with a letter, a number, or the underscore symbol, and can consist of from 1 to 31 letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a name that helps identify the VLAN. However, you cannot perform any VLAN operation by specifying this name instead of the VLAN ID.

<b>IPAddress</b>
The IP address assigned to the VLAN.

<b>netmask</b>
Subnet mask for the network address defined for this VLAN.

<b>linklocalIPv6Addr</b>
The link-local IP address assigned to the VLAN.

<b>rnat</b>
Temporary flag used for internal purpose.

<b>stateflag</b>
state flag

<b>portbitmap</b>
Member interfaces of this vlan.

<b>lsbitmap</b>
Member linksets of this vlan.

<b>tagbitmap</b>
Tagged members of this vlan.

<b>lstagbitmap</b>
Tagged linksets of this vlan.

<b>ifaces</b>
Names of all member interfaces of this vlan.

<b>tagIfaces</b>
Names of all tagged member interfaces of this vlan.

<b>ipv6DynamicRouting</b>
Whether dynamic routing is enabled or disabled.

<b>flag</b>

<b>ifnum</b>
The interface to be bound to the VLAN, specified in slot/port notation (for example, 1/3).

<b>tagged</b>
Make the interface an 802.1q tagged interface. Packets sent on this interface on this VLAN have an additional 4-byte 802.1q tag, which identifies the VLAN. To use 802.1q tagging, you must also configure the switch connected to the appliance's interfaces.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>vlantd</b>
Traffic domain associated with vlan.

<b>sdxVlan</b>
SDX vlan.

<b>mtu</b>
Specifies the maximum transmission unit (MTU), in bytes. The MTU is the largest packet size, excluding 14 bytes of ethernet header and 4 bytes of crc, that can be transmitted and received over this VLAN.

<b>vxlan</b>
The VXLAN that extends this vlan.

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show vlan command is as follows:1)      VLAN ID: 5      VLAN Alias Name:        Interfaces : 1/7        IPs : 		10.102.169.36       Mask: 255.255.255.02)      VLAN ID: 3      VLAN Alias Name:        Interfaces : 1/5(T)        Channels : LA/2 Done*(T) - Tagged

##stat vlan

Display statistics for VLAN(s).


##Synopsys

stat vlan [&lt;id>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>id</b>
An integer specifying the VLAN identification number (VID). Possible values: 1 through 4094.
Minimum value: 1
Maximum value: 4094

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Packets received (RxPkts)</b>
Packets received on the VLAN.

<b>Bytes received (RxBytes)</b>
Bytes of data received on the VLAN.

<b>Packets sent (TxPkts)</b>
Packets transmitted on the VLAN.

<b>Bytes sent (TxBytes)</b>
Bytes of data transmitted on the VLAN.

<b>Packets dropped (DropPkts)</b>
Inbound packets dropped by the VLAN upon reception.

<b>Broadcast pkts sent & received (BcastPkt)</b>
Broadcast packets sent and received on the VLAN.



##Example

stat vlan 1

