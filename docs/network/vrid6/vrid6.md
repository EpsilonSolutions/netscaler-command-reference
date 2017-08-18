#vrID6

The following operations can be performed on "vrID6":


[add](#add-vrid6) | [rm](#rm-vrid6) | [set](#set-vrid6) | [unset](#unset-vrid6) | [bind](#bind-vrid6) | [unbind](#unbind-vrid6) | [show](#show-vrid6)

##add vrID6

Adds a VMAC6 address to the NetScaler appliance.A Virtual MAC address (VMAC6) is a floating entity, shared by the nodes in a high availability, or active-active, or cluster setup.


##Synopsys

add vrID6 &lt;id> [-priority &lt;positive_integer>] [-preemption ( ENABLED | DISABLED )] [-sharing ( ENABLED | DISABLED )] [-tracking &lt;tracking>] [-preemptiondelaytimer &lt;secs>] [-trackifNumPriority &lt;positive_integer>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.
Default value: 255
Minimum value: 0
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
Default value: NONE

<b>preemptiondelaytimer</b>
Preemption delay time in seconds, in an active-active configuration. If any high priority node will come in network, it will wait for these many seconds before becoming master.
Default value: 0
Minimum value: 1
Maximum value: 36000

<b>trackifNumPriority</b>
Priority by which the Effective priority will be reduced if any of the tracked interfaces goes down in an active-active configuration.
Default value: 0
Minimum value: 1
Maximum value: 255

<b>ownerNode</b>
In a cluster setup, assign a cluster node as the owner of this VMAC address for IP based VRRP configuration. If no owner is configured, ow ner node is displayed as ALL and one node is dynamically elected as the owner.
Default value: -1 
Minimum value: 0
Maximum value: 31



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



##set vrID6

Modifies parameters related to a VMAC address on the NetScaler appliance.


##Synopsys

set vrID6 &lt;id> [-priority &lt;positive_integer>] [-preemption ( ENABLED | DISABLED )] [-sharing ( ENABLED | DISABLED )] [-tracking &lt;tracking>] [-preemptiondelaytimer &lt;secs>] [-trackifNumPriority &lt;positive_integer>] [-ownerNode &lt;positive_integer>]


##Arguments

<b>id</b>
Integer value that uniquely identifies the VMAC address. The generic VMACaddress is in the form of 00:00:5e:00:01:&lt;VRID&gt;. For example, if you add a VRID with a value of 60 and bind it to an interface, the resulting VMAC address is 00:00:5e:00:01:3c, where 3c is the hexadecimal representation of 60.
Minimum value: 1
Maximum value: 255

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.
Default value: 255
Minimum value: 0
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
Default value: NONE

<b>preemptiondelaytimer</b>
Preemption delay time in seconds, in an active-active configuration. If any high priority node will come in network, it will wait for these many seconds before becoming master.
Default value: 0
Minimum value: 1
Maximum value: 36000

<b>trackifNumPriority</b>
Priority by which the Effective priority will be reduced if any of the tracked interfaces goes down in an active-active configuration.
Default value: 0
Minimum value: 1
Maximum value: 255

<b>ownerNode</b>
In a cluster setup, assign a cluster node as the owner of this VMAC address for IP based VRRP configuration. If no owner is configured, ow ner node is displayed as ALL and one node is dynamically elected as the owner.
Default value: -1 
Minimum value: 0
Maximum value: 31



##Example

set vrID6 1 -priority 100

##unset vrID6

Use this command to remove  vrID6 settings.Refer to the set  vrID6 command for meanings of the arguments.


##Synopsys

unset vrID6 &lt;id> [-priority] [-preemption] [-sharing] [-tracking] [-preemptiondelaytimer] [-trackifNumPriority] [-ownerNode]


##bind vrID6

Binds the specified interfaces to a VMAC6 configuration.


##Synopsys

bind vrID6 &lt;id> (-ifnum &lt;interface_name> ... | -trackifNum &lt;interface_name> ...)


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to bind to the VMAC. Use spaces to separate multiple entries.
For a NetScaler appliance, specify the interface in C/U notation (for example, 1/3).For a cluster setup for configuring interface based VRRP, specify the interface in N/C/U notation(for example, 2/1/3) . where C can take one of the following values:
		    * 0 - Indicates a mgmt port.
		    * 1 - Indicates a 1 Gbps port.
		    * 10 - Indicates a 10 Gbps port.
Note: Interface based VRRP is only applicable to a two-node cluster where one of node is in active state and the other in Spare. You must associate the VRID to the interfaces of both the nodes of the active-spare cluster setup. This is because unlike in a high availability setup, interface ID differs in a cluster setup.

<b>trackifNum</b>
Interfaces which need to be tracked for this vrID.



##Example

add vrID6 1

##unbind vrID6

Unbinds the specified interfaces from a VMAC6 configuration.


##Synopsys

unbind vrID6 &lt;id> (-ifnum &lt;interface_name> ... | -trackifNum &lt;interface_name> ...)


##Arguments

<b>id</b>
Integer value that uniquely identifies a VMAC6 address.
Minimum value: 1
Maximum value: 255

<b>ifnum</b>
Interfaces to unbind from the VMAC6, specified in (slot/port) notation (for example, 1/2). Use spaces to separate multiple entries.

<b>trackifNum</b>
Interfaces which need to be tracked for this vrID.



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
Interfaces to bind to the VMAC6, specified in (slot/port) notation (for example, 1/2).Use spaces to separate multiple entries.

<b>type</b>
Type (static or dynamic) of this VRID.

<b>vlan</b>
The VLAN in which this VRID resides.

<b>priority</b>
Base priority (BP), in an active-active mode configuration, which ordinarily determines the master VIP address.

<b>state</b>
State of this VRID.

<b>flags</b>
Flags.

<b>stateflag</b>

<b>IPAddress</b>
The IP address bound to the VRID6

<b>preemption</b>
In an active-active mode configuration, make a backup VIP address the master if its priority becomes higher than that of a master VIP address bound to this VMAC address.
             If you disable pre-emption while a backup VIP address is the master, the backup VIP address remains master until the original master VIP's priority becomes higher than that of the current master.

<b>sharing</b>
In an active-active mode configuration, enable the backup VIP address to process any traffic instead of dropping it.

<b>preemptiondelaytimer</b>
Preemption delay time in seconds, in an active-active configuration. If any high priority node will come in network, it will wait for these many seconds before becoming master.

<b>trackifNum</b>
Interfaces which need to be tracked for this vrID.

<b>trackifNumPriority</b>
Priority by which the Effective priority will be reduced if any of the tracked interfaces goes down in an active-active configuration.

<b>effectivePriority</b>
The effective priority of this VRID.

<b>tracking</b>
The effective priority (EP) value, relative to the base priority (BP) value in an active-active mode configuration. When EP is set to a value other than None, it is EP, not BP, which determines the master VIP address.
Available settings function as follows:
* NONE - No tracking. EP = BP
* ALL -  If the status of all virtual servers is UP, EP = BP. Otherwise, EP = 0.
* ONE - If the status of at least one virtual server is UP, EP = BP. Otherwise, EP = 0.
* PROGRESSIVE - If the status of all virtual servers is UP, EP = BP. If the status of all virtual servers is DOWN, EP = 0. Otherwise EP = BP (1 - K/N), where N is the total number of virtual servers associated with the VIP address and K is the number of virtual servers for which the status is DOWN.
Default: NONE.

<b>operationalOwnerNode</b>
Run time owner node of the vrid.

<b>ownerNode</b>
In a cluster setup, assign a cluster node as the owner of this VMAC address for IP based VRRP configuration. If no owner is configured, ow ner node is displayed as ALL and one node is dynamically elected as the owner.

<b>devno</b>

<b>count</b>



##Example

show vrid6

