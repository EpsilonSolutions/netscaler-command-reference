#route6

The following operations can be performed on "route6":


[add](#add-route6) | [clear](#clear-route6) | [rm](#rm-route6) | [set](#set-route6) | [unset](#unset-route6) | [show](#show-route6)

##add route6

Adds an IPv6 static route to the routing table of the NetScaler appliance.


##Synopsys

add route6 &lt;network> [&lt;gateway>] [-vlan &lt;positive_integer>] [-weight &lt;positive_integer>] [-distance &lt;positive_integer>] [-cost &lt;positive_integer>] [-advertise ( DISABLED | ENABLED )] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]] [-td &lt;positive_integer>]


##Arguments

<b>network</b>
IPv6 network address for which to add a route entry to the routing table of the NetScaler appliance.

<b>gateway</b>
The gateway for this route. The value for this parameter is either an IPv6 address or null.
Default value: 0

<b>vlan</b>
Integer value that uniquely identifies a VLAN through which the NetScaler appliance forwards the packets for this route.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>weight</b>
Positive integer used by the routing algorithms to determine preference for this route over others of equal cost. The lower the weight, the higher the preference.
Default value: 1
Minimum value: 1
Maximum value: 65535

<b>distance</b>
Administrative distance of this route from the appliance.
Default value: 1
Minimum value: 1
Maximum value: 254

<b>cost</b>
Positive integer used by the routing algorithms to determine preference for this route. The lower the cost, the higher the preference.
Default value: 1
Maximum value: 65535

<b>advertise</b>
Advertise this route.
Possible values: DISABLED, ENABLED

<b>msr</b>
Monitor this route witha monitor of type ND6 or PING.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

add route6 ::/0 2004::1  add route6 ::/0 FE80::67 -vlan 5

##clear route6

Removes IPv6 routes of the specified type (protocol) from the routing table of the NetScaler appliance.


##Synopsys

clear route6 &lt;routeType>


##Arguments

<b>routeType</b>
Type of IPv6 routes to remove from the routing table of the NetScaler appliance.



##rm route6

Removes a static IPv6 route from the NetScaler appliance.


##Synopsys

rm route6 &lt;network> [&lt;gateway>] [-vlan &lt;positive_integer>] [-td &lt;positive_integer>]


##Arguments

<b>network</b>
The network of the route to be removed.

<b>gateway</b>
The gateway address of the route to be removed.
Default value: 0

<b>vlan</b>
Integer that uniquely identifies the VLAN defined for this route.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

rm route6 ::/0 2004::1rm route6 ::/0 FE80::67 -vlan 5

##set route6

Modifies parameters of an IPv6 static route.


##Synopsys

set route6 &lt;network> [&lt;gateway>] [-vlan &lt;positive_integer>] [-weight &lt;positive_integer>] [-distance &lt;positive_integer>] [-cost &lt;positive_integer>] [-advertise ( DISABLED | ENABLED )] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]] [-td &lt;positive_integer>]


##Arguments

<b>network</b>
IPv6 network address of the route entry to be modified.

<b>gateway</b>
The gateway for the route's destination network.
Default value: 0

<b>vlan</b>
Integer value that uniquely identifies a VLAN through which the NetScaler appliance forwards the packets for this route.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>weight</b>
Positive integer used by the routing algorithms to determine preference for this route over others of equal cost. The lower the weight, the higher the preference.
Default value: 1
Minimum value: 1
Maximum value: 65535

<b>distance</b>
Administrative distance of this route from the appliance.
Default value: 1
Minimum value: 1
Maximum value: 254

<b>cost</b>
Positive integer used by the routing algorithms to determine preference for this route. The lower the cost, the higher the preference.
Default value: 1
Maximum value: 65535

<b>advertise</b>
Advertise this route.
Possible values: DISABLED, ENABLED

<b>msr</b>
Monitor this route witha monitor of type ND6 or PING.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Example

set route6 1::1/100 2000::1 -advertise enable

##unset route6

Unset the attributes of a route that were added by the add/set route command..Refer to the set  route6 command for meanings of the arguments.


##Synopsys

unset route6 &lt;network> [&lt;gateway>] [-vlan &lt;positive_integer>] [-td &lt;positive_integer>] [-weight] [-distance] [-cost] [-advertise] [-msr] [-monitor]


##Example

unset route6 2000::1/100 3000::1 -advertise enable

##show route6

Displays configuration and state information of all IPv6 routes in the NetScaler appliance's routing table, or of the specified IPv6 route.


##Synopsys

show route6 [&lt;network>  [&lt;gateway>]  [-vlan &lt;positive_integer>]  [-td &lt;positive_integer>]] [&lt;routeType>] [-detail]


##Arguments

<b>network</b>
IPv6 network address of the route entry for which to display details.

<b>routeType</b>
The type of IPv6 routes to be to be displayed.

<b>detail</b>
To get a detailed view.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>gatewayName</b>
The name of the gateway for this route.

<b>advertise</b>
Any gateway of the route entry for which the details are to be displayed.

<b>type</b>
State of the RNAT.

<b>stateflag</b>

<b>dynamic</b>
Whether this route is dynamically learned or not.

<b>weight</b>
Weight of this route.

<b>distance</b>
Administrative distance of this route from the appliance.

<b>cost</b>
Positive integer used by the routing algorithms to determine preference for this route. The lower the cost, the higher the preference.

<b>data</b>
Internal data of this route.NOTE: This attribute is deprecated.This option is deprecated in favour of NSA_DATA1

<b>flags</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>msr</b>
Whether MSR is enabled or disabled.

<b>monitor</b>
Name of the monitor, of type ND6 or PING, configured on the NetScaler appliance to monitor this route.

<b>state</b>
Whether this route is UP or DOWN.

<b>totalprobes</b>
The total number of probes sent.

<b>totalfailedprobes</b>
The total number of failed probes.

<b>failedprobes</b>
Current number of failed monitoring probes.

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>data1</b>
Internal data of this route.

<b>routeOwners</b>
Use this option with -dynamic and in a cluster only to specify the set of nodes from which this dynamic route has been learnt.

<b>retain</b>

<b>STATIC</b>
Static route.

<b>PERMANENT</b>
Permanent Route.

<b>connected</b>
Connected Route.

<b>OSPFV3</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>ISIS</b>
If this route is dynamic then which routing protocol was it learnt from.

<b>active</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>BGP</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>RIP</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>raRoute</b>
For a dynamic route, the routing protocol from which the route was learned.

<b>devno</b>

<b>count</b>



##Example

Following is an example of the output of the show route6 command:     Flags: Static(S), Dynamic(D), Active(A)     ---------------------------------------     Network       Gateway(vlan)   Flags     -------       -----------     -----     0::0/0        2001::1            S(A)     0::0/0        FE80::90(4)        D(A)

