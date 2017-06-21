#router bgp

The following operations can be performed on "router bgp":


[add](#add-router-bgp) | [clear](#clear-router-bgp) | [rm](#rm-router-bgp) | [set](#set-router-bgp) | [unset](#unset-router-bgp) | [show](#show-router-bgp)

##add router bgp

 NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>autonomousSystem</b>
The BGP autonomous system.
Minimum value: 1

<b>routerID</b>
The router ID of the router.

<b>learnRoute</b>
The state of route learning from BGP.

<b>staticRedistribute</b>
The state of router in redistribution of static routes.

<b>staticRouteMap</b>
The route map to apply while redistributing static routes.

<b>kernelRedistribute</b>
The state of router in redistribution of kernel routes.

<b>kernelRouteMap</b>
The route map to apply while redistributing kernel routes.

<b>conRedistribute</b>
The state of router in redistribution of connected routes.

<b>connectedRouteMap</b>
The route map to apply while redistributing connected routes.

<b>neighbor</b>
Add a BGP neighbor.

<b>remoteAS</b>
The AS of the neighbor.
Minimum value: 0

<b>neighborRouteMap</b>
The route map to apply to the neighbor.

<b>network</b>
The neighbor to be advertised.

<b>netmask</b>
The netmask of the neighbor to be advertised.



##clear router bgp

 NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>autonomousSystem</b>
The autonomous system for BGP.
Minimum value: 1

<b>neighbor</b>
The neighbor associated with the connection that needs to be torn down.

<b>all</b>
Reset TCP connections to all neighbors.



##rm router bgp

 NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>autonomousSystem</b>
The autonomous system for BGP.
Minimum value: 1

<b>neighbor</b>
To remove a particular neighbor.



##set router bgp

 NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>autonomousSystem</b>
The autonomous system for BGP.
Minimum value: 1

<b>routerID</b>
The Router ID of this router.

<b>learnRoute</b>
The state of the router in learning routes from BGP. Use this option to enable route learning and installation from BGP.

<b>staticRedistribute</b>
The state of the router in redistributing static routes. Use this option to enable the redistribution of static routes.

<b>staticRouteMap</b>
The route map to apply while redistributing static routes.

<b>kernelRedistribute</b>
The state of the router in redistribution of kernel routes.

<b>kernelRouteMap</b>
The state of the router in redistributing kernel routes. The route map to apply while redistributing kernel routes.

<b>conRedistribute</b>
The state of the router in redistributing connected routes. Use this option to enable the redistribution of connected routes into the BGP domain.

<b>connectedRouteMap</b>
The route map to apply while redistributing connected routes.

<b>neighbor</b>
The IP address of a BGP peer for the router.

<b>remoteAS</b>
The autonomous system of the peer.
Minimum value: 0

<b>neighborRouteMap</b>
The route map to apply to the specified neighbor.

<b>network</b>
The network to be advertized.

<b>netmask</b>
The netmask of the advertised network.



##unset router bgp

Use this command to remove router bgp settings.Refer to the set router bgp command for meanings of the arguments.NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##show router bgp

 NOTE: This command is deprecated.All routing configurations have now been moved to vtysh


##Synopsys




##Arguments

<b>autonomousSystem</b>
The autonomous system for BGP.
Minimum value: 1

<b>bgpOptions</b>
option to show BGP command either neighbors or summary
Possible values: neighbors, summary

<b>routeMap</b>
The BGP route map.



##Outputs

<b>devno</b>

<b>count</b>

<b>stateflag</b>



