#vrIDParam

The following operations can be performed on "vrIDParam":


[set](#set-vridparam) | [unset](#unset-vridparam) | [show](#show-vridparam)

##set vrIDParam

Sets global parameters of VMACs on the NetScaler appliance.


##Synopsys

set vrIDParam -sendToMaster ( ENABLED | DISABLED )


##Arguments

<b>sendToMaster</b>
Forward packets to the master node, in an active-active mode configuration, if the virtual server is in the backup state and sharing is disabled.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set vrIDParam -sendToMaster ENABLED

##unset vrIDParam

Use this command to remove  vrIDParam settings.Refer to the set  vrIDParam command for meanings of the arguments.


##Synopsys

unset vrIDParam -sendToMaster


##show vrIDParam

Displays the VRID global settings on the NetScaler appliance.


##Synopsys

show vrIDParam


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>sendToMaster</b>
Forward packets to the master node, in an active-active mode configuration, if the virtual server is in the backup state and sharing is disabled.



