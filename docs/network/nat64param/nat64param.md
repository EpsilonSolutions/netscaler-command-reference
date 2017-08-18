#nat64param

The following operations can be performed on "nat64param":


[set](#set-nat64param) | [unset](#unset-nat64param) | [show](#show-nat64param)

##set nat64param

Set the nat64 parameter


##Synopsys

set nat64param [-td &lt;positive_integer>] [-nat64IgnoreTOS ( YES | NO )] [-nat64ZeroCheckSum ( ENABLED | DISABLED )] [-nat64v6Mtu &lt;positive_integer>] [-nat64FragHeader ( ENABLED | DISABLED )]


##Arguments

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>nat64IgnoreTOS</b>
Ignore TOS.
Possible values: YES, NO
Default value: NO

<b>nat64ZeroCheckSum</b>
Calculate checksum for UDP packets with zero checksum
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>nat64v6Mtu</b>
MTU setting for the IPv6 side. If the incoming IPv4 packet greater than this, either fragment or send icmp need fragmentation error.
Default value: 1280
Minimum value: 1280
Maximum value: 9216

<b>nat64FragHeader</b>
When disabled, translator will not insert IPv6 fragmentation header for non fragmented IPv4 packets
Possible values: ENABLED, DISABLED
Default value: ENABLED



##Example

set nat64param -nat64ignoretos YES

##unset nat64param

Use this command to remove  nat64param settings.Refer to the set  nat64param command for meanings of the arguments.


##Synopsys

unset nat64param [-td &lt;positive_integer>] [-nat64IgnoreTOS] [-nat64ZeroCheckSum] [-nat64v6Mtu] [-nat64FragHeader]


##show nat64param

Show the nat64 parameters.


##Synopsys

show nat64param [-td &lt;positive_integer>]


##Arguments

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##Outputs

<b>nat64IgnoreTOS</b>
Ignore TOS.

<b>nat64ZeroCheckSum</b>
Calculate checksum for UDP packets with zero checksum

<b>nat64v6Mtu</b>
MTU setting for the IPv6 side. If the incoming IPv4 packet greater than this, either fragment or send icmp need fragmentation error.

<b>nat64FragHeader</b>
When disabled, translator will not insert IPv6 fragmentation header for non fragmented IPv4 packets

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show nat64param

