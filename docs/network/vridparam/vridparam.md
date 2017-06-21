#vrIDParam

The following operations can be performed on "vrIDParam":


[set](#set-vridparam) | [unset](#unset-vridparam) | [show](#show-vridparam)

##set vrIDParam

Sets global parameters of VMACs on the NetScaler appliance.


##Synopsys

set vrIDParam [-sendToMaster ( ENABLED | DISABLED )] [-helloInterval &lt;msecs>] [-deadInterval &lt;secs>]


##Arguments

<b>sendToMaster</b>
Forward packets to the master node, in an active-active mode configuration, if the virtual server is in the backup state and sharing is disabled.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>helloInterval</b>
Interval, in milliseconds, between vrrp advertisement messages sent to the peer node in active-active mode.
Default value: 1000
Minimum value: 200
Maximum value: 1000

<b>deadInterval</b>
Number of seconds after which a peer node in active-active mode is marked down if vrrp advertisements are not received from the peer node.
Default value: 3
Minimum value: 1
Maximum value: 3



##Example

set vrIDParam -sendToMaster ENABLED

##unset vrIDParam

Use this command to remove  vrIDParam settings.Refer to the set  vrIDParam command for meanings of the arguments.


##Synopsys

unset vrIDParam [-sendToMaster] [-helloInterval] [-deadInterval]


##show vrIDParam

Displays the VRID global settings on the NetScaler appliance.


##Synopsys

show vrIDParam


##Outputs

<b>sendToMaster</b>
Forward packets to the master node, in an active-active mode configuration, if the virtual server is in the backup state and sharing is disabled.

<b>helloInterval</b>
Interval, in milliseconds, between vrrp advertisement messages sent to the peer node in active-active mode.

<b>deadInterval</b>
Number of seconds after which a peer node in active-active mode is marked down if vrrp advertisements are not received from the peer node.



