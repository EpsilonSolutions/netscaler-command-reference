#nd6RAvariables

The following operations can be performed on "nd6RAvariables":


[set](#set-nd6ravariables) | [unset](#unset-nd6ravariables) | [show](#show-nd6ravariables) | [bind](#bind-nd6ravariables) | [unbind](#unbind-nd6ravariables)

##set nd6RAvariables

Set vlan specific Router Advertisment parameters in NetScaler.


##Synopsys

set nd6RAvariables -vlan &lt;positive_integer> [-ceaseRouterAdv ( YES | NO )] [-sendRouterAdv ( YES | NO )] [-srcLinkLayerAddrOption ( YES | NO )] [-onlyUnicastRtAdvResponse ( YES | NO )] [-managedAddrConfig ( YES | NO )] [-otherAddrConfig ( YES | NO )] [-currHopLimit &lt;positive_integer>] [-maxRtAdvInterval &lt;positive_integer>] [-minRtAdvInterval &lt;positive_integer>] [-linkMTU &lt;positive_integer>] [-reachableTime &lt;positive_integer>] [-retransTime &lt;positive_integer>] [-defaultLifeTime &lt;integer>]


##Arguments

<b>vlan</b>
The VLAN number.
Minimum value: 0
Maximum value: 4094

<b>ceaseRouterAdv</b>
Cease router advertisements on this vlan.
Possible values: YES, NO
Default value: NO

<b>sendRouterAdv</b>
whether the router sends periodic RAs and responds to Router Solicitations.
Possible values: YES, NO
Default value: NO

<b>srcLinkLayerAddrOption</b>
Include source link layer address option in RA messages.
Possible values: YES, NO
Default value: YES

<b>onlyUnicastRtAdvResponse</b>
Send only Unicast Router Advertisements in respond to Router Solicitations.
Possible values: YES, NO
Default value: NO

<b>managedAddrConfig</b>
Value to be placed in the Managed address configuration flag field.
Possible values: YES, NO
Default value: NO

<b>otherAddrConfig</b>
Value to be placed in the Other configuration flag field.
Possible values: YES, NO
Default value: NO

<b>currHopLimit</b>
Current Hop limit.
Default value: 64
Minimum value: 0
Maximum value: 255

<b>maxRtAdvInterval</b>
Maximum time allowed between unsolicited multicast RAs, in seconds.
Default value: 600
Minimum value: 4
Maximum value: 1800

<b>minRtAdvInterval</b>
Minimum time interval between RA messages, in seconds.
Default value: 198
Minimum value: 3
Maximum value: 1350

<b>linkMTU</b>
The Link MTU.
Default value: 0
Minimum value: 0
Maximum value: 1500

<b>reachableTime</b>
Reachable time, in milliseconds.
Default value: 0
Minimum value: 0
Maximum value: 3600000

<b>retransTime</b>
Retransmission time, in milliseconds.
Default value: 0
Minimum value: 0

<b>defaultLifeTime</b>
Default life time, in seconds.
Default value: 1800
Minimum value: 0
Maximum value: 9000



##Example

set nd6RAvariables -vlan 2 -maxRtAdvInterval 600

##unset nd6RAvariables

Use this command to remove  nd6RAvariables settings.Refer to the set  nd6RAvariables command for meanings of the arguments.


##Synopsys

unset nd6RAvariables -vlan &lt;positive_integer> [-ceaseRouterAdv] [-sendRouterAdv] [-srcLinkLayerAddrOption] [-onlyUnicastRtAdvResponse] [-managedAddrConfig] [-otherAddrConfig] [-currHopLimit] [-maxRtAdvInterval] [-minRtAdvInterval] [-linkMTU] [-reachableTime] [-retransTime] [-defaultLifeTime]


##show nd6RAvariables

Display Router Advertisement configuration variables.


##Synopsys

show nd6RAvariables [-vlan &lt;positive_integer>]


##Arguments

<b>vlan</b>
The VLAN number.
Minimum value: 0
Maximum value: 4094



##Outputs

<b>ceaseRouterAdv</b>
Cease router advertisements on this vlan.

<b>sendRouterAdv</b>
whether the router sends periodic RAs and responds to Router Solicitations.

<b>srcLinkLayerAddrOption</b>
Include source link layer address option in RA messages.

<b>onlyUnicastRtAdvResponse</b>
Send only Unicast Router Advertisements in respond to Router Solicitations.

<b>managedAddrConfig</b>
Value to be placed in the Managed address configuration flag field.

<b>otherAddrConfig</b>
Value to be placed in the Other configuration flag field.

<b>currHopLimit</b>
Current Hop limit.

<b>maxRtAdvInterval</b>
Maximum time allowed between unsolicited multicast RAs, in seconds.

<b>minRtAdvInterval</b>
Minimum time interval between RA messages, in seconds.

<b>linkMTU</b>
The Link MTU.

<b>reachableTime</b>
Reachable time, in milliseconds.

<b>retransTime</b>
Retransmission time, in milliseconds.

<b>defaultLifeTime</b>
Default life time, in seconds.

<b>stateflag</b>
RA Param state flags.

<b>lastRtAdvTime</b>
Last RA sent timestamp.

<b>nextRtAdvDelay</b>
Next RA delay.

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.

<b>devno</b>

<b>count</b>



##bind nd6RAvariables

Bind on-link global prefixes to Router Advertisments variables.


##Synopsys

bind nd6RAvariables -vlan &lt;positive_integer> -ipv6Prefix &lt;ipv6_addr|*>


##Arguments

<b>vlan</b>
The VLAN number.
Minimum value: 0
Maximum value: 4094

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.



##Example

bind nd6RAvariables -vlan 2 -ipv6Prefix 8000::/64

##unbind nd6RAvariables

Unbind prefix from Router Advertisment parameters in NetScaler


##Synopsys

unbind nd6RAvariables -vlan &lt;positive_integer> -ipv6Prefix &lt;ipv6_addr|*>


##Arguments

<b>vlan</b>
The VLAN number.
Minimum value: 0
Maximum value: 4094

<b>ipv6Prefix</b>
Onlink prefixes for RA messages.



##Example

unbind nd6RAvariables -vlan 2 -ipv6Prefix 8000::/64

