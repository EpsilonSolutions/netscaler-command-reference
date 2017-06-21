#bridgetable

The following operations can be performed on "bridgetable":


[set](#set-bridgetable) | [unset](#unset-bridgetable) | [show](#show-bridgetable) | [clear](#clear-bridgetable)

##set bridgetable

Sets global parameters of bridge table entries.


##Synopsys

set bridgetable -bridgeAge &lt;positive_integer>


##Arguments

<b>bridgeAge</b>
Time-out value for the bridge table entries, in seconds. The new value applies only to the entries that are dynamically learned after the new value is set. Previously existing bridge table entries expire after the previously configured time-out value.
Default value: 300
Minimum value: 60
Maximum value: 300



##Example

set bridgetable -bridgeAge 200

##unset bridgetable

Use this command to remove  bridgetable settings.Refer to the set  bridgetable command for meanings of the arguments.


##Synopsys

unset bridgetable -bridgeAge


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
The IP address of the VTEP

<b>flags</b>
Display flags,

<b>channel</b>
The Tunnel through which bridge entry is learned.

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



