#vrID

The following operations can be performed on "vrID":


[add](#add-vrid) | [rm](#rm-vrid) | [set](#set-vrid) | [unset](#unset-vrid) | [bind](#bind-vrid) | [unbind](#unbind-vrid) | [show](#show-vrid)

##add vrID

Adds a VMAC address to the NetScaler appliance.A Virtual MAC address (VMAC) is a floating entity, shared by the nodes in an HA configuration.


##Synopsys

add vrID &lt;id> [-priority &lt;positive_integer>] [-preemption ( ENABLED | DISABLED )] [-sharing ( ENABLED | DISABLED )] [-tracking &lt;tracking>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>id</b>
Integer that uniquely identifies the VMAC address. The generic VMAC address is in the form of 00:00:5e:00:01:&lt;VRID&gt;. For example, if you add a VRID with a value of 60 and bind it to an interface, the resulting VMAC address is 00:00:5e:00:01:3c, where 3c is the hexadecimal representation of 60.
Minimum value: 1
Maximum value: 255

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.
Default value: 255
Minimum value: 1
Maximum value: 255

<b>preemption</b>
In an active-active mode configuration, make a backup VIP address the master if its priority becomes higher than that of a master VIP address bound to this VMAC address. 
If you disable pre-emption while a backup VIP address is the master, the backup VIP address remains master until the original master VIP's priority becomes higher than that of the current master.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sharing</b>
In an active-active mode configuration, enable the backup VIP address to process any traffic instead of dropping it.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>tracking</b>
The effective priority (EP) value, relative to the base priority (BP) value in an active-active mode configuration. When EP is set to a value other than None, it is EP, not BP, which determines the master VIP address.
Available settings function as follows:
* NONE - No tracking. EP = BP
* ALL -  If the status of all virtual servers is UP, EP = BP. Otherwise, EP = 0.
* ONE - If the status of at least one virtual server is UP, EP = BP. Otherwise, EP = 0.
* PROGRESSIVE - If the status of all virtual servers is UP, EP = BP. If the status of all virtual servers is DOWN, EP = 0. Otherwise EP = BP (1 - K/N), where N is the total number of virtual servers associated with the VIP address and K is the number of virtual servers for which the status is DOWN.
Default: NONE.
Possible values: NONE, ONE, ALL, PROGRESSIVE
Default value: TRACK_NONE

<b>ownerNode</b>
Assign a cluster node as the owner of this VMAC address. If no owner is configured, owner node is displayed as ALL and one node is dynamically elected as the owner.
Default value: VAL_NOT_SET
Maximum value: 31



##Example

add vrID 1

##rm vrID

Removes a specified VMAC entry or all VMAC entries from the NetScaler appliance.


##Synopsys

rm vrID (&lt;id> | -all)


##Arguments

<b>id</b>
Integer value that uniquely identifies the VMAC address.
Minimum value: 1
Maximum value: 255

<b>all</b>
Remove all the configured VMAC addresses from the NetScaler appliance.



##set vrID

Modifies parameters related to a VMAC address on the NetScaler appliance.


##Synopsys

set vrID &lt;id> [-priority &lt;positive_integer>] [-preemption ( ENABLED | DISABLED )] [-sharing ( ENABLED | DISABLED )] [-tracking &lt;tracking>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>id</b>
Integer value that uniquely identifies the VMAC address. The generic VMACaddressis in the form of 00:00:5e:00:01:&lt;VRID&gt;. For example, if you add a VRID with a value of 60 and bind it to an interface, the resulting VMAC address is 00:00:5e:00:01:3c, where 3c is the hexadecimal representation of 60.
Minimum value: 1
Maximum value: 255

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.
Default value: 255
Minimum value: 1
Maximum value: 255

<b>preemption</b>
In an active-active mode configuration, make a backup VIP address the master if its priority becomes higher than that of a master VIP address bound to this VMAC address. 
If you disable pre-emption while a backup VIP address is the master, the backup VIP address remains master until the original master VIP's priority becomes higher than that of the current master.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sharing</b>
In an active-active mode configuration, enable the backup VIP address to process any traffic instead of dropping it.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>tracking</b>
The effective priority (EP) value, relative to the base priority (BP) value in an active-active mode configuration. When EP is set to a value other than None, it is EP, not BP, which determines the master VIP address.
Available settings function as follows:
* NONE - No tracking. EP = BP
* ALL -  If the status of all virtual servers is UP, EP = BP. Otherwise, EP = 0.
* ONE - If the status of at least one virtual server is UP, EP = BP. Otherwise, EP = 0.
* PROGRESSIVE - If the status of all virtual servers is UP, EP = BP. If the status of all virtual servers is DOWN, EP = 0. Otherwise EP = BP (1 - K/N), where N is the total number of virtual servers associated with the VIP address and K is the number of virtual servers for which the status is DOWN.
Default: NONE.
Possible values: NONE, ONE, ALL, PROGRESSIVE
Default value: TRACK_NONE

<b>ownerNode</b>
Assign a cluster node as the owner of this VMAC address. If no owner is configured, owner node is displayed as ALL and one node is dynamically elected as the owner.
Default value: VAL_NOT_SET
Maximum value: 31



##Example

set vrID 1 -priority 100

##unset vrID

Use this command to remove  vrID settings.Refer to the set  vrID command for meanings of the arguments.


##Synopsys

unset vrID &lt;id> [-priority] [-preemption] [-sharing] [-tracking] [-ownerNode]


##bind vrID

Binds the specified interfaces to a VMAC configuration.


##Synopsys

bind vrID &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
Integer that uniquely identifies the VMAC address. The generic VMAC address is in the form of 00:00:5e:00:01:&lt;VRID&gt;. For example, if you add a VRID with a value of 60 and bind it to an interface, the resulting VMAC address is 00:00:5e:00:01:3c, where 3c is the hexadecimal representation of 60.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to bind to the VMAC, specified in (slot/port) notation (for example, 1/2).Use spaces to separate multiple entries.



##Example

add vrID 1

##unbind vrID

Unbinds specified interfaces from a VMAC configuration.


##Synopsys

unbind vrID &lt;id> -ifnum &lt;interface_name> ...


##Arguments

<b>id</b>
Integer value that uniquely identifies the VMAC address. The generic VMAC address is in the form of 00:00:5e:00:01:&lt;VRID&gt;. For example, if you add a VRID with a value of 60 and bind it to an interface, the resulting VMAC address is 00:00:5e:00:01:3c, where 3c is the hexadecimal representation of 60.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to unbind from the VMAC, specified in (slot/port) notation (for example, 1/2). Use spaces to separate multiple entries.



##show vrID

Displays the settings of all VRIDs configured on the NetScaler appliance, or of the specified VRID. To display the settings of all the VRIDs, run the command without any parameters. To display the settings of a particular VRID, specify the VRID.


##Synopsys

show vrID [&lt;id>]


##Arguments

<b>id</b>
Integer value that uniquely identifies the VMAC address.
Minimum value: 1
Maximum value: 255

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>ifaces</b>
Interfaces bound to this VRID.

<b>type</b>
Indicates whether this VRID entry was added manually or dynamically. When you manually add a VRID entry, the value for this parameter is STATIC. Otherwise, it is DYNAMIC.

<b>vlan</b>
The VLAN in which this VRID resides.

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.

<b>effectivePriority</b>
The effective priority of this VRID.

<b>preemption</b>
In an active-active mode configuration, make a backup VIP address the master if its priority becomes higher than that of a master VIP address bound to this VMAC address. 
If you disable pre-emption while a backup VIP address is the master, the backup VIP address remains master until the original master VIP's priority becomes higher than that of the current master.

<b>sharing</b>
In an active-active mode configuration, enable the backup VIP address to process any traffic instead of dropping it.

<b>tracking</b>
The effective priority (EP) value, relative to the base priority (BP) value in an active-active mode configuration. When EP is set to a value other than None, it is EP, not BP, which determines the master VIP address.
Available settings function as follows:
* NONE - No tracking. EP = BP
* ALL -  If the status of all virtual servers is UP, EP = BP. Otherwise, EP = 0.
* ONE - If the status of at least one virtual server is UP, EP = BP. Otherwise, EP = 0.
* PROGRESSIVE - If the status of all virtual servers is UP, EP = BP. If the status of all virtual servers is DOWN, EP = 0. Otherwise EP = BP (1 - K/N), where N is the total number of virtual servers associated with the VIP address and K is the number of virtual servers for which the status is DOWN.
Default: NONE.

<b>flags</b>
Flags.

<b>IPAddress</b>
The IP address bound to the VRID.

<b>state</b>
State of this VRID.

<b>stateflag</b>

<b>operationalOwnerNode</b>
Run time owner node of the vrid.

<b>ownerNode</b>
Assign a cluster node as the owner of this VMAC address. If no owner is configured, owner node is displayed as ALL and one node is dynamically elected as the owner.

<b>devno</b>

<b>count</b>



##Example

show vrid

