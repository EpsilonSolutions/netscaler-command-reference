#route

The following operations can be performed on "route":


[add](#add-route) | [clear](#clear-route) | [rm](#rm-route) | [set](#set-route) | [unset](#unset-route) | [show](#show-route)

##add route

Adds an IPv4 static route to the routing table of the NetScaler appliance.


##Synopsys

add route &lt;network> &lt;netmask> &lt;gateway> [-td &lt;positive_integer>] [-distance &lt;positive_integer>] [-cost &lt;positive_integer>] [-weight &lt;positive_integer>] [-advertise ( DISABLED | ENABLED )] [-protocol &lt;protocol> ...] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]]


##Arguments

<b>network</b>
IPv4 network address for which to add a route entry in the routing table of the NetScaler appliance.

<b>netmask</b>
The subnet mask associated with the network address.

<b>gateway</b>
IP address of the gateway for this route. Can be either the IP address of the gateway, or can be null to specify a null interface route.

<b>cost</b>
The cost of a route is used to compare routes of the same type. The route having the lowest cost is the most preferred route. Possible values: 0 through 65535. Default: 0.
Maximum value: 65535

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>distance</b>
Administrative distance of this route, which determines the preference of this route over other routes, with same destination, from different routing protocols. A lower value is preferred.
Default value: STATIC_ROUTE_DEFAULT_DISTANCE
Maximum value: 255

<b>weight</b>
Positive integer used by the routing algorithms to determine preference for this route over others of equal cost. The lower the weight, the higher the preference.
Default value: ROUTE_DEFAULT_WEIGHT
Minimum value: 1
Maximum value: 65535

<b>advertise</b>
Advertise this route.
Possible values: DISABLED, ENABLED

<b>protocol</b>
Routing protocol used for advertising this route.
Default value: ADV_ROUTE_FLAGS

<b>msr</b>
Monitor this route using a monitor of type ARP or PING.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add route 10.10.10.0 255.255.255.0 10.10.10.1

##clear route

Removes routes of the specifiedtype(protocol) from the routing table of the NetScaler appliance.


##Synopsys

clear route &lt;routeType>


##Arguments

<b>routeType</b>
Protocol used by routes that you want to remove from the routing table of the NetScaler appliance.



##rm route

Removes a static route from the NetScaler appliance. Note: You cannot use this command to remove routes that are part of a VLAN configuration. Use the rmvlan or clear vlan command instead.


##Synopsys

rm route &lt;network> &lt;netmask> &lt;gateway> [-td &lt;positive_integer>]


##Arguments

<b>network</b>
Network address specified in the route entry that you want to remove from the routing table of the NetScaler appliance.

<b>netmask</b>
Subnet mask associated with the network address.

<b>gateway</b>
IP address of the gateway for this route.

<b>td</b>
The Traffic Domain Id of the route to be removed.
Minimum value: 0
Maximum value: 4094



##set route

Modifies parameters of an IPv4 static route.


##Synopsys

set route &lt;network> &lt;netmask> &lt;gateway> [-td &lt;positive_integer>] [-distance &lt;positive_integer>] [-cost &lt;positive_integer>] [-weight &lt;positive_integer>] [-advertise ( DISABLED | ENABLED )] [-protocol &lt;protocol> ...] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]]


##Arguments

<b>network</b>
Network address in the route entry that you want to modify.

<b>netmask</b>
Subnet mask associated with the network address.

<b>gateway</b>
IP address of the gateway for this route. Can be either the IP address of the gateway, or can be null to specify a null interface route.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>distance</b>
Administrative distance of this route, which determines the preference of this route over other routes, with same destination, from different routing protocols. A lower value is preferred.
Default value: STATIC_ROUTE_DEFAULT_DISTANCE
Maximum value: 255

<b>cost</b>
The cost of a route is used to compare routes of the same type. The route having the lowest cost is the most preferred route. Possible values: 0 through 65535. Default: 0.
Maximum value: 65535

<b>weight</b>
Positive integer used by the routing algorithms to determine preference for this route over others of equal cost. The lower the weight, the higher the preference.
Default value: ROUTE_DEFAULT_WEIGHT
Minimum value: 1
Maximum value: 65535

<b>advertise</b>
Advertise this route.
Possible values: DISABLED, ENABLED

<b>protocol</b>
Routing protocol used for advertising this route.
Default value: ADV_ROUTE_FLAGS

<b>msr</b>
Monitor this route using a monitor of type ARP or PING.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set route 10.10.10.0 255.255.255.0 10.10.10.1 -advertise enable

##unset route

Unset the attributes of a route that were added by the add/set route command..Refer to the set  route command for meanings of the arguments.


##Synopsys

unset route &lt;network> &lt;netmask> &lt;gateway> [-td &lt;positive_integer>] [-advertise] [-distance] [-cost] [-weight] [-protocol] [-msr] [-monitor]


##Example

unset route 10.10.10.0 255.255.255.0 10.10.10.1 -advertise enable

##show route

Display the configured routing information.


##Synopsys

show route [&lt;network>  &lt;netmask>  [&lt;gateway>]  [-td &lt;positive_integer>]] [&lt;routeType>] [-detail]


##Arguments

<b>network</b>
The destination network or host.

<b>routeType</b>
The type of routes to be shown.

<b>detail</b>
Display a detailed view.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>gatewayName</b>
The name of the gateway for this route. For a route other than a link load balancing (LLB) route, this value is null.

<b>advertise</b>
Enable advertisement.

<b>type</b>
State of the RNAT.

<b>stateflag</b>

<b>dynamic</b>
State of the route.

<b>STATIC</b>

<b>PERMANENT</b>

<b>DIRECT</b>

<b>NAT</b>

<b>LBROUTE</b>

<b>ADV</b>

<b>TUNNEL</b>
Show whether it is a tunnel route or not.

<b>cost</b>
The cost of a route is used to compare routes of the same type. The route having the lowest cost is the most preferred route. Possible values: 0 through 65535. Default: 0.

<b>distance</b>
Administrative distance of this route, which determines the preference of this route over other routes, with same destination, from different routing protocols. A lower value is preferred.

<b>weight</b>
The weight of this route.

<b>protocol</b>
Routing protocol used for advertising this route.

<b>data</b>
Internal data of this route.

<b>data0</b>
Internal route type is stored, used for get.

<b>flags</b>
If this route is dynamic, the name of the routing protocol from which it was learned.

<b>routeOwners</b>
Use this option with -dynamic and in a cluster only to specify the set of nodes from which this dynamic route has been learnt.

<b>retain</b>

<b>OSPF</b>
OSPF protocol.

<b>ISIS</b>
ISIS protocol.

<b>RIP</b>
RIP protocol.

<b>BGP</b>
BGP protocol.

<b>DHCP</b>

<b>advOSPF</b>
Advertised through OSPF protocol.NOTE: This attribute is deprecated.This argument is deprecated.Use protocol parameter to read advertise properties of route

<b>advISIS</b>
Advertised through ISIS protocol.NOTE: This attribute is deprecated.This argument is deprecated.Use protocol parameter to read advertise properties of route

<b>advRIP</b>
Advertised through RIP protocol.NOTE: This attribute is deprecated.This argument is deprecated.Use protocol parameter to read advertise properties of route

<b>advBGP</b>
Advertised through BGP protocol.NOTE: This attribute is deprecated.This argument is deprecated.Use protocol parameter to read advertise properties of route

<b>msr</b>
Whether MSR is enabled or disabled.

<b>monitor</b>
Name of the monitor, of type ARP or PING, configured on the NetScaler appliance to monitor this route.

<b>state</b>
The state of the static route. Possible values: UP, DOWN.

<b>peFlags</b>
PE flags.

<b>totalprobes</b>
The total number of probes sent.

<b>totalfailedprobes</b>
The total number of failed probes.

<b>failedprobes</b>
Number of the current failed monitoring probes.

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter used with the message code.

<b>monStatParam2</b>
Second parameter used with the message code.

<b>monStatParam3</b>
Third parameter used with the message code.

<b>devno</b>

<b>count</b>



##Example

An example of the output of the show route command is as follows:3 configured routes:    Network        Netmask        Gateway/OwnedIP     Type    -------        -------        ---------------     ----1)  0.0.0.0        0.0.0.0        10.11.0.254         STATIC2)  127.0.0.0      255.0.0.0      127.0.0.1           PERMANENT3)  10.251.0.0     255.255.0.0    10.251.0.254        NAT

