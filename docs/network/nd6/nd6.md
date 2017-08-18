#nd6

The following operations can be performed on "nd6":


[add](#add-nd6) | [clear](#clear-nd6) | [rm](#rm-nd6) | [show](#show-nd6)

##add nd6

Adds a static entry to the ND6 table of the NetScaler appliance.


##Synopsys

add nd6 &lt;neighbor> &lt;mac> (&lt;ifnum> | -vxlan &lt;positive_integer>) [-vlan &lt;integer>] [-vtep &lt;ip_addr>] [-td &lt;positive_integer>]


##Arguments

<b>neighbor</b>
Link-local IPv6 address of the adjacent network device to add to the ND6 table.

<b>mac</b>
MAC address of the adjacent network device.

<b>ifnum</b>
Interface through which the adjacent network device is available, specified in slot/port notation (for example, 1/3). Use spaces to separate multiple entries.

<b>vlan</b>
Integer value that uniquely identifies the VLAN on which the adjacent network device exists.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN on which the IPv6 address of this ND6 entry is reachable.
Minimum value: 1
Maximum value: 16777215

<b>vtep</b>
IP address of the VXLAN tunnel endpoint (VTEP) through which the IPv6 address of this ND6 entry is reachable.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add nd6 2001::1 00:04:23:be:3c:06 5 1/1

##clear nd6

Removes all IPv6 neighbour discovery entries from the NetScaler appliance.


##Synopsys

clear nd6


##rm nd6

Remove a static IPv6 neighbor discovery entry from the NetScaler appliance's ND6 table.


##Synopsys

rm nd6 &lt;neighbor> [-vlan &lt;integer> | -vxlan &lt;positive_integer>] [-td &lt;positive_integer>]


##Arguments

<b>neighbor</b>
Link-local IPv6 address of the adjacent network device that you want to remove from the ND6 table.

<b>vlan</b>
Integer value that uniquely identifies the VLAN for the ND6 entry you want to remove.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
Integer value that uniquely identifies the VXLAN for the ND6 entry you want to remove.
Minimum value: 1
Maximum value: 16777215

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

rm nd6 2001::1 5 1/1

##show nd6

Display the neighbor discovery information.


##Synopsys

show nd6 [&lt;neighbor>  [-td &lt;positive_integer>]]


##Arguments

<b>neighbor</b>
Link-local IPv6 address of the adjacent network device to add to the ND6 table.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Outputs

<b>mac</b>
MAC address of the adjacent network device.

<b>state</b>
ND6 state

<b>timeout</b>
Time elapsed

<b>ifnum</b>
Interface through which the adjacent network device is available, specified in slot/port notation (for example, 1/3). Use spaces to separate multiple entries.

<b>vlan</b>
Integer value that uniquely identifies the VLAN on which the adjacent network device exists.

<b>vxlan</b>
ID of the VXLAN on which the IPv6 address of this ND6 entry is reachable.

<b>vtep</b>
IP address of the VXLAN tunnel endpoint (VTEP) through which the IPv6 address of this ND6 entry is reachable.

<b>flags</b>
flag for static/permanent entry.

<b>controlPlane</b>
This nd6 entry is populated by a control plane protocol

<b>channel</b>
The tunnel that is bound to a netbridge.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

Following is an example of the output for the show nd6 command: Neighbor           MAC-Address(Vlan, Interface)      State      TIME(hh:mm:ss) --------           ---------------------------       -----      -------------- 2001::1            00:04:23:be:3c:06(5, 1/1)         REACHABLE  00:00:24 FE80::123:1        00:04:23:be:3c:07(4, 1/2)         STALE      00:03:34

