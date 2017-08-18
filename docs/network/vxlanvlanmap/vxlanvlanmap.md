#vxlanVlanMap

The following operations can be performed on "vxlanVlanMap":


[add](#add-vxlanvlanmap) | [rm](#rm-vxlanvlanmap) | [bind](#bind-vxlanvlanmap) | [unbind](#unbind-vxlanvlanmap) | [show](#show-vxlanvlanmap)

##add vxlanVlanMap

Add a table that gives a vlan to vxlan mapping.


##Synopsys

add vxlanVlanMap &lt;name>


##Arguments

<b>name</b>
Name of the mapping table.



##Example

add vxlanVlanMap table1

##rm vxlanVlanMap

Delete the vlan to vxlan mapping table.


##Synopsys

rm vxlanVlanMap &lt;name>


##Arguments

<b>name</b>
Name of the mapping table.



##Example

rm vxlanVlanMap table1

##bind vxlanVlanMap

Specify vlan to vxlan mappings.


##Synopsys

bind vxlanVlanMap &lt;name> [-vxlan &lt;positive_integer>  -vlan &lt;int[-int]> ...]


##Arguments

<b>name</b>
Name of the mapping table.

<b>vxlan</b>
The VXLAN assigned to the vlan inside the cloud.
Minimum value: 1
Maximum value: 16777215

<b>vlan</b>
The vlan id or the range of vlan ids in the on-premise network.
Minimum value: 1
Maximum value: 4094



##Example

bind vxlanVlanMap tab1 -vxlan 7000 -vlan 7 9 100-800

##unbind vxlanVlanMap

Remove a vlan to vxlan mappings.


##Synopsys

unbind vxlanVlanMap &lt;name> -vxlan &lt;positive_integer>


##Arguments

<b>name</b>
Name of the mapping table.

<b>vxlan</b>
The VXLAN assigned to the vlan inside the cloud.
Minimum value: 1
Maximum value: 16777215



##Example

unbind vxlanVlanMap table1 -vxlan 3000

##show vxlanVlanMap

Retrieve vlan to vxlan mappings.


##Synopsys

show vxlanVlanMap [&lt;name>]


##Arguments

<b>name</b>
Name of the mapping table.



##Outputs

<b>stateflag</b>
Internal flag for display

<b>vxlan</b>
The VXLAN assigned to the vlan inside the cloud.

<b>vlan</b>
The vlan id or the range of vlan ids in the on-premise network.

<b>devno</b>

<b>count</b>



##Example

show vxlanVlanMap

