#router rip

The following operations can be performed on "router rip":


[set](#set-router-rip) | [unset](#unset-router-rip) | [show](#show-router-rip)

##set router rip

Configure the RIP daemon. NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>defaultMetric</b>
The default metrics when advertising routes.
Default value: 1
Minimum value: 1
Maximum value: 16

<b>passiveInterface</b>
The mode of the interface to listen only.

<b>learnRoute</b>
The state of Route learning. Use this option to enable route learning and installation in the kernel.

<b>staticRedistribute</b>
The state of redistributing static routes.

<b>kernelRedistribute</b>
The state of redistributing kernel routes.

<b>network</b>
The broadcast network on which RIP must run.

<b>netmask</b>
The netmask for the network on which RIP must run.



##Example

set router rip -kernelRedistribute

##unset router rip

Unset the RIP parameters..Refer to the set router rip command for meanings of the arguments.NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Example

unset rip -default-metric

##show router rip

Display the RIP configuration. NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>ripOptions</b>
RIP option in show command, one of database or interface.
Possible values: database, interface



##Outputs

<b>network</b>
The broadcast network on which RIP must run.

<b>netmask</b>



##Example

show rip interface

