#ipv6

The following operations can be performed on "ipv6":


[set](#set-ipv6) | [unset](#unset-ipv6) | [show](#show-ipv6)

##set ipv6

Sets the IPv6-related parameters.


##Synopsys

set ipv6 [-ralearning ( ENABLED | DISABLED )] [-routerRedirection ( ENABLED | DISABLED )] [-ndBasereachTime &lt;positive_integer>] [-ndRetransmissionTime &lt;positive_integer>] [-natprefix &lt;ipv6_addr|*>  [-td &lt;positive_integer>]] [-doDAD ( ENABLED | DISABLED )]


##Arguments

<b>ralearning</b>
Enable the NetScaler appliance to learn about various routes from Router Advertisement (RA) and Router Solicitation (RS) messages sent by the routers.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>routerRedirection</b>
Enable the NetScaler appliance to do Router Redirection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ndBasereachTime</b>
Base reachable time of the Neighbor Discovery (ND6) protocol. The time, in milliseconds, that the NetScaler appliance assumes an adjacent device is reachable after receiving a reachability confirmation.
Default value: 30000
Minimum value: 1

<b>ndRetransmissionTime</b>
Retransmission time of the Neighbor Discovery (ND6) protocol. The time, in milliseconds, between retransmitted Neighbor Solicitation (NS) messages, to an adjacent device.
Default value: 1000
Minimum value: 1

<b>natprefix</b>
Prefix used for translating packets from private IPv6 servers to IPv4 packets. This prefix has a length of 96 bits (128-32 = 96). The IPv6 servers embed the destination IP address of the IPv4 servers or hosts in the last 32 bits of the destination IP address field of the IPv6 packets. The first 96 bits of the destination IP address field are set as the IPv6 NAT prefix. IPv6 packets addressed to this prefix have to be routed to the NetScaler appliance to ensure that the IPv6-IPv4 translation is done by the appliance.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>doDAD</b>
Enable the NetScaler appliance to do Duplicate Address
Detection (DAD) for all the NetScaler owned IPv6 addresses regardless of whether they are obtained through stateless auto configuration, DHCPv6, or manual configuration.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set ipv6 -natprefix 2000::/96

##unset ipv6

Unset the IPv6-related parameters: RA Learning and IPv6 NAT Prefix..Refer to the set  ipv6 command for meanings of the arguments.


##Synopsys

unset ipv6 [-ralearning] [-routerRedirection] [-ndBasereachTime] [-ndRetransmissionTime] [-natprefix  [-td &lt;positive_integer>]] [-doDAD]


##Example

unset ipv6 -natprefix -td 1

##show ipv6

Display IPv6 settings


##Synopsys

show ipv6 [-td &lt;positive_integer>]


##Arguments

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094



##Outputs

<b>ralearning</b>
Enable the NetScaler appliance to learn about various routes from Router Advertisement (RA) and Router Solicitation (RS) messages sent by the routers.

<b>routerRedirection</b>
Enable the NetScaler appliance to do Router Redirection.

<b>basereachtime</b>
ND6 base reachable time (ms)

<b>ndBasereachTime</b>
Base reachable time of the Neighbor Discovery (ND6) protocol. The time, in milliseconds, that the NetScaler appliance assumes an adjacent device is reachable after receiving a reachability confirmation.

<b>reachtime</b>
ND6 computed reachable time (ms)

<b>ndreachtime</b>
ND6 computed reachable time (ms)

<b>retransmissiontime</b>
ND6 retransmission time (ms)

<b>ndRetransmissionTime</b>
Retransmission time of the Neighbor Discovery (ND6) protocol. The time, in milliseconds, between retransmitted Neighbor Solicitation (NS) messages, to an adjacent device.

<b>natprefix</b>
Prefix used for translating packets from private IPv6 servers to IPv4 packets. This prefix has a length of 96 bits (128-32 = 96). The IPv6 servers embed the destination IP address of the IPv4 servers or hosts in the last 32 bits of the destination IP address field of the IPv6 packets. The first 96 bits of the destination IP address field are set as the IPv6 NAT prefix. IPv6 packets addressed to this prefix have to be routed to the NetScaler appliance to ensure that the IPv6-IPv4 translation is done by the appliance.

<b>doDAD</b>
Enable the NetScaler appliance to do Duplicate Address
Detection (DAD) for all the NetScaler owned IPv6 addresses regardless of whether they are obtained through stateless auto configuration, DHCPv6, or manual configuration.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ipv6

