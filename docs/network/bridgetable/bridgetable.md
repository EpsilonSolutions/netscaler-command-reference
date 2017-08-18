#bridgetable

The following operations can be performed on "bridgetable":


[add](#add-bridgetable) | [rm](#rm-bridgetable) | [set](#set-bridgetable) | [unset](#unset-bridgetable) | [show](#show-bridgetable) | [clear](#clear-bridgetable)

##add bridgetable

Add static mac-vtep mappings per vxlan


##Synopsys

add bridgetable -mac &lt;mac_addr> -vxlan &lt;positive_integer> -vtep &lt;ip_addr> [-vni &lt;positive_integer>] [-deviceVlan &lt;positive_integer>]


##Arguments

<b>mac</b>
The MAC address of the target.

<b>vxlan</b>
The VXLAN to which this address is associated.
Minimum value: 1
Maximum value: 16777215

<b>vtep</b>
The IP address of the destination VXLAN tunnel endpoint where the Ethernet MAC ADDRESS resides.

<b>vni</b>
The VXLAN VNI Network Identifier (or VXLAN Segment ID) to use to connect to the remote VXLAN tunnel endpoint.  If omitted the value specified as vxlan will be used.
Minimum value: 1
Maximum value: 16777215

<b>deviceVlan</b>
The vlan on which to send multicast packets when the VXLAN tunnel endpoint is a muticast group address.
Minimum value: 1
Maximum value: 4094



##Example

add bridgetable -mac 52:f2:46:e6:ed:67 -vxlan 100 -vtep 172.16.1.24add bridgetable -mac c2:76:29:4a:fe:9e -vxlan 100 -vtep 192.168.7.1 -vni 200add bridgetable -mac 00:00:00:00:00:00 -vxlan 100 -vtep 172.16.1.24add bridgetable -mac 00:00:00:00:00:00 -vxlan 100 -vtep 239.0.0.1 -deviceVlan 23add bridgetable -mac 00:00:00:00:00:00 -vxlan 100 -vtep 239.0.0.1 -deviceVlan 24

##rm bridgetable

Delete static mac-vtep mapping


##Synopsys

rm bridgetable -mac &lt;mac_addr> -vxlan &lt;positive_integer> [-vtep &lt;ip_addr>] [-deviceVlan &lt;positive_integer>]


##Arguments

<b>mac</b>
The MAC address of the target.

<b>vxlan</b>
The VXLAN to which this address is associated.
Minimum value: 1
Maximum value: 16777215

<b>vtep</b>
The IP address of the destination VXLAN tunnel endpoint where the Ethernet MAC ADDRESS resides.

<b>deviceVlan</b>
The vlan on which to send multicast packets when the VXLAN tunnel endpoint is a muticast group address.
Minimum value: 1
Maximum value: 4094



##Example

rm bridgetable -mac 52:f2:46:e6:ed:67 -vxlan 100rm bridgetable -mac 00:00:00:00:00:00 -vxlan 100 -vtep 172.16.1.24rm bridgetable -mac 00:00:00:00:00:00 -vxlan 100 -vtep 239.0.0.1 -deviceVlan 23

##set bridgetable

Sets global parameters of bridge table entries. The bridgeAge attribute is deprecated. Use "set l2param -bridgeAgeTimeout" instead.


##Synopsys

set bridgetable


##Example

set bridgetable -bridgeAge 200

##unset bridgetable

Use this command to remove  bridgetable settings.Refer to the set  bridgetable command for meanings of the arguments.


##Synopsys

unset bridgetable


##show bridgetable

Displays the bridge table entries and the configured time-out values for these entries.


##Synopsys

show bridgetable


##Outputs

<b>bridgeAge</b>
Time-out value for the bridge table entries, in seconds. The new value applies only to the entries that are dynamically learned after the new value is set. Previously existing bridge table entries expire after the previously configured time-out value.

<b>mac</b>
The MAC address of the target.

<b>ifnum</b>
The interface on which the address was learned.

<b>vlan</b>
The VLAN in which this MAC address resides.

<b>vxlan</b>
The VXLAN in which this MAC address resides.

<b>vtep</b>
The IP address of the destination VXLAN tunnel endpoint where the Ethernet MAC ADDRESS resides.

<b>vni</b>
The VXLAN VNI Network Identifier (or VXLAN Segment ID) to use to connect to the remote VXLAN tunnel endpoint.  If omitted the value specified as vxlan will be used.

<b>deviceVlan</b>
The vlan on which to send multicast packets when the VXLAN tunnel endpoint is a muticast group address.

<b>flags</b>
Display flags,

<b>type</b>
Whether static or dynamic

<b>channel</b>
The Tunnel through which bridge entry is learned.

<b>controlPlane</b>
This bridge table entry is populated by a control plane protocol

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show bridgetable

##clear bridgetable

Remove entries from bridge table


##Synopsys

clear bridgetable [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-ifnum &lt;interface_name>]


##Arguments

<b>vlan</b>
VLAN  whose entries are to be removed.
Minimum value: 1
Maximum value: 4094

<b>ifnum</b>
INTERFACE  whose entries are to be removed.

<b>vxlan</b>
VXLAN  whose entries are to be removed.
Minimum value: 1
Maximum value: 16777215



