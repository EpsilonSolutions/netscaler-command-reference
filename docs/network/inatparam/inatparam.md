#inatparam

The following operations can be performed on "inatparam":


[set](#set-inatparam) | [unset](#unset-inatparam) | [show](#show-inatparam)

##set inatparam

Set the inat parameter


##Synopsys

set inatparam [-nat46v6Prefix &lt;ipv6_addr|*>  [-td &lt;positive_integer>]] [-nat46IgnoreTOS ( YES | NO )] [-nat46ZeroCheckSum ( ENABLED | DISABLED )] [-nat46v6Mtu &lt;positive_integer>] [-nat46FragHeader ( ENABLED | DISABLED )]


##Arguments

<b>nat46v6Prefix</b>
The prefix used for translating packets received from private IPv6 servers into IPv4 packets. This prefix has a length of 96 bits (128-32 = 96). The IPv6 servers embed the destination IP address of the IPv4 servers or hosts in the last 32 bits of the destination IP address field of the IPv6 packets. The first 96 bits of the destination IP address field are set as the IPv6 NAT prefix. IPv6 packets addressed to this prefix have to be routed to the NetScaler appliance to ensure that the IPv6-IPv4 translation is done by the appliance.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>nat46IgnoreTOS</b>
Ignore TOS.
Possible values: YES, NO
Default value: NO

<b>nat46ZeroCheckSum</b>
Calculate checksum for UDP packets with zero checksum
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>nat46v6Mtu</b>
MTU setting for the IPv6 side. If the incoming IPv4 packet greater than this, either fragment or send icmp need fragmentation error.
Default value: 1280
Minimum value: 1280
Maximum value: 9216

<b>nat46FragHeader</b>
When disabled, translator will not insert IPv6 fragmentation header for non fragmented IPv4 packets
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set inat parameter -nat46ignoretos YES

##unset inatparam

Unset the inat parameter.Refer to the set  inatparam command for meanings of the arguments.


##Synopsys

unset inatparam [-nat46v6Prefix  [-td &lt;positive_integer>]]


##Example

unset inatparam -nat46v6Prefix -td 1

##show inatparam

Show the inat parameters.


##Synopsys

show inatparam [-td &lt;positive_integer>]


##Arguments

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Outputs

<b>nat46v6Prefix</b>
The prefix used for translating packets received from private IPv6 servers into IPv4 packets. This prefix has a length of 96 bits (128-32 = 96). The IPv6 servers embed the destination IP address of the IPv4 servers or hosts in the last 32 bits of the destination IP address field of the IPv6 packets. The first 96 bits of the destination IP address field are set as the IPv6 NAT prefix. IPv6 packets addressed to this prefix have to be routed to the NetScaler appliance to ensure that the IPv6-IPv4 translation is done by the appliance.

<b>nat46IgnoreTOS</b>
Ignore TOS.

<b>nat46ZeroCheckSum</b>
Calculate checksum for UDP packets with zero checksum

<b>nat46v6Mtu</b>
MTU setting for the IPv6 side. If the incoming IPv4 packet greater than this, either fragment or send icmp need fragmentation error.

<b>nat46FragHeader</b>
When disabled, translator will not insert IPv6 fragmentation header for non fragmented IPv4 packets

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show inat params

