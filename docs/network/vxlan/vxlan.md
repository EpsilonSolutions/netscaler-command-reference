#vxlan

The following operations can be performed on "vxlan":


[add](#add-vxlan) | [rm](#rm-vxlan) | [set](#set-vxlan) | [unset](#unset-vxlan) | [bind](#bind-vxlan) | [unbind](#unbind-vxlan) | [show](#show-vxlan) | [stat](#stat-vxlan)

##add vxlan

Adds a VXLAN to the NetScaler appliance.


##Synopsys

add vxlan &lt;id> [-vlan &lt;positive_integer>] [-port &lt;port>]


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215

<b>vlan</b>
ID of VLANs whose traffic is allowed over this VXLAN. If you do not specify any VLAN IDs, the NetScaler allows traffic of all VLANs that are not part of any other VXLANs.
Minimum value: 1
Maximum value: 4094

<b>port</b>
Specifies UDP destination port for VXLAN packets.
Default value: 4789
Minimum value: 1
Maximum value: 65534



##Example

add vxlan 20000 -vlan 4

##rm vxlan

Removes a VXLAN from the NetScaler appliance


##Synopsys

rm vxlan &lt;id>


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215



##Example

rm vxlan 20000

##set vxlan

Modify VXLAN parameters


##Synopsys

set vxlan &lt;id> [-vlan &lt;positive_integer>] [-port &lt;port>]


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215

<b>vlan</b>
ID of VLANs whose traffic is allowed over this VXLAN. If you do not specify any VLAN IDs, the NetScaler allows traffic of all VLANs that are not part of any other VXLANs.
Minimum value: 1
Maximum value: 4094

<b>port</b>
Specifies UDP destination port for VXLAN packets.
Default value: 4789
Minimum value: 1
Maximum value: 65534



##Example

set vxlan 20000 -vlan 4

##unset vxlan

Use this command to remove  vxlan settings.Refer to the set  vxlan command for meanings of the arguments.


##Synopsys

unset vxlan &lt;id> [-vlan] [-port]


##bind vxlan

Binds tunnels or IP addresses to the VXLAN


##Synopsys

bind vxlan &lt;id> (-tunnel &lt;string> | (-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]))


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215

<b>tunnel</b>
Specifies the name of the configured tunnel to be associated with this VXLAN.

<b>IPAddress</b>
Network address to be associated with the VXLAN. Should exist on the appliance before you associate it with the VXLAN.



##Example

bind vxlan 20000 -tunnel t1

##unbind vxlan

Unbinds tunnels and IP addresses from the VXLAN


##Synopsys

unbind vxlan &lt;id> (-tunnel &lt;string> | (-IPAddress &lt;ip_addr|ipv6_addr|*>  [&lt;netmask>]))


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215

<b>tunnel</b>
Specifies the name of the configured tunnel to be associated with this VXLAN.

<b>IPAddress</b>
The IP Address associated with the VXLAN configuration.



##Example

unbind vxlan 20000 -tunnel t1

##show vxlan

Display all the VXLANs on the Netscaler appliance


##Synopsys

show vxlan [&lt;id>]


##Arguments

<b>id</b>
A positive integer, which is also called VXLAN Network Identifier (VNI), that uniquely identifies a VXLAN.
Minimum value: 1
Maximum value: 16777215

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>vlan</b>
ID of VLANs whose traffic is allowed over this VXLAN. If you do not specify any VLAN IDs, the NetScaler allows traffic of all VLANs that are not part of any other VXLANs.

<b>port</b>
Specifies UDP destination port for VXLAN packets.

<b>tunnel</b>
Specifies the name of the configured tunnel to be associated with this VXLAN.

<b>IPAddress</b>
The IP address assigned to the VXLAN.

<b>netmask</b>
Subnet mask for the network address defined for this VXLAN.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>stateflag</b>
Internal flag for display

<b>devno</b>

<b>count</b>



##stat vxlan

Display statistics for VXLAN(s).


##Synopsys

stat vxlan [&lt;id>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>id</b>
An integer specifying the VXLAN identification number (VNID).
Minimum value: 1
Maximum value: 16777215

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Packets received (RxPkts)</b>
Packets received on the VXLAN.

<b>Bytes received (RxBytes)</b>
Bytes of data received on the VXLAN.

<b>Packets sent (TxPkts)</b>
Packets transmitted on the VXLAN.

<b>Bytes sent (TxBytes)</b>
Bytes of data transmitted on the VXLAN.



##Example

stat vxlan 10000

