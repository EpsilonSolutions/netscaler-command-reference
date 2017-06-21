#vrID6

The following operations can be performed on "vrID6":


[add](#add-vrid6) | [rm](#rm-vrid6) | [bind](#bind-vrid6) | [unbind](#unbind-vrid6) | [show](#show-vrid6)

##add vrID6

Adds a VMAC6 address to the NetScaler appliance.A Virtual MAC address (VMAC6) is a floating entity, shared by the nodes in an HA configuration.


##Synopsys

add vrID6 &lt;id>


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255



##Example

add vrID6 1

##rm vrID6

Removes a specified VMAC6 entry or all VMAC6 entries from the NetScaler appliance.


##Synopsys

rm vrID6 (&lt;id> | -all)


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>all</b>
Remove all configured VMAC6 addresses from the NetScaler appliance.



##bind vrID6

Binds the specified interfaces to a VMAC6 configuration.


##Synopsys

bind vrID6 &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to bind tothe VMAC6, specified in (slot/port) notation (for example, 1/2).Use spaces to separate multiple entries.



##Example

add vrID6 1

##unbind vrID6

Unbinds the specified interfaces from a VMAC6 configuration.


##Synopsys

unbind vrID6 &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to unbind from the VMAC6, specified in (slot/port) notation (for example, 1/2). Use spaces to separate multiple entries.



##show vrID6

Displays the settings of all VRID6s configured on the NetScaler appliance, or of the specified VRID6. To display the settings of all the VRID6s, run the command without any parameters. To display the settings of a particular VRID6, specify the VRID6.


##Synopsys

show vrID6 [&lt;id>]


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255



##Outputs

<b>ifaces</b>
Interfaces bound to this VRID.

<b>ifnum</b>
Interfaces bound to this VRID.

<b>type</b>
Type (static or dynamic) of this VRID.

<b>vlan</b>
The VLAN in which this VRID resides.

<b>priority</b>
The priority of this VRID.

<b>state</b>
State of this VRID.

<b>flags</b>
Flags.

<b>stateflag</b>

<b>IPAddress</b>
The IP address bound to the VRID6

<b>devno</b>

<b>count</b>



##Example

show vrid6

