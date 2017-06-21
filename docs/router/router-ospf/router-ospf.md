#router ospf

The following operations can be performed on "router ospf":


[set](#set-router-ospf) | [unset](#unset-router-ospf) | [show](#show-router-ospf)

##set router ospf

Configure different OSPF parameters. NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>routerID</b>
The router ID.

<b>passiveInterface</b>
The mode of the Interface. Use this option to change the mode of the interface to listen only.

<b>staticRedistribute</b>
The state of the router in redistributing static routes. Use this option to enable the redistribution of static routes.

<b>staticMetricType</b>
The metric type for static routes.
Default value: 2
Minimum value: 1
Maximum value: 2

<b>kernelRedistribute</b>
The state of the router in redistributing kernel routes. Use this option to enable the redistribution of kernel routes.

<b>kernelMetricType</b>
The metric type for kernel routes.
Default value: 2
Minimum value: 1
Maximum value: 2

<b>conRedistribute</b>
The state of the router in redistributing connected routes. Use this option to enable the redistribution of connected routes.

<b>conMetricType</b>
The metric type for connected routes.
Default value: 2
Minimum value: 1
Maximum value: 2

<b>learnRoute</b>
The state of the router in learning routes from OSPF. Use this option to enable route learning from OSPF.

<b>network</b>
The broadcast network on which OSPF is to be run.

<b>netmask</b>
The netmask for the broadcast network.

<b>area</b>
The area ID of the area in which OSPF is running.
Default value: -1

<b>host</b>
The stub link.

<b>cost</b>
The cost of the hostroute.



##Example

set ospf -routerID 1.2.3.4

##unset router ospf

Unset the OSPF parameters that were configured using the ###set ospf### command..Refer to the set router ospf command for meanings of the arguments.NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Example

unset ospf -router-id

##show router ospf

Display the state of the OSPF daemon. NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>ospfoptions</b>
The Router OSPF option. Use this option to display one of border-routers, database, interface, neighbor, route, and virtual-links.
Possible values: border-routers, database, interface, neighbor, route, virtual-links



##Outputs

<b>network</b>
The network on which OSPF is running.

<b>netmask</b>
Netmask of the network on which OSPF is running



##Example

show ospf neighbor

