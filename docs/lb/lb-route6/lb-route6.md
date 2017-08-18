#lb route6

The following operations can be performed on "lb route6":


[add](#add-lb-route6) | [rm](#rm-lb-route6) | [show](#show-lb-route6)

##add lb route6

Bind the route VIP to the route structure.


##Synopsys

add lb route6 &lt;network> &lt;gatewayName> [-td &lt;positive_integer>]


##Arguments

<b>network</b>
The destination network.

<b>gatewayName</b>
The name of the route.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094



##rm lb route6

Remove the route VIP from the route structure.


##Synopsys

rm lb route6 &lt;network> [-td &lt;positive_integer>]


##Arguments

<b>network</b>
The IP address of the network to which the route VIP belongs.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094



##show lb route6

Display the names of the routes associated to the route structure using the ###add lb route6### command.


##Synopsys

show lb route6 [&lt;network>  [-td &lt;positive_integer>]]


##Arguments

<b>network</b>
The destination network or host.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094



##Outputs

<b>gatewayName</b>
The name of the route.

<b>flags</b>
State of the configured gateway.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



