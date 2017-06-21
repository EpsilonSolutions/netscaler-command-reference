#ip6TunnelParam

The following operations can be performed on "ip6TunnelParam":


[set](#set-ip6tunnelparam) | [unset](#unset-ip6tunnelparam) | [show](#show-ip6tunnelparam)

##set ip6TunnelParam

Sets global parameters of IPv6 tunnels on the NetScaler appliance.


##Synopsys

set ip6TunnelParam [-srcIP &lt;ipv6_addr|null>] [-dropFrag ( YES | NO )] [-dropFragCpuThreshold &lt;positive_integer>] [-srcIPRoundRobin ( YES | NO )]


##Arguments

<b>srcIP</b>
Common source IPv6 address for all IPv6 tunnels. Must be a SNIP6 or VIP6 address.

<b>dropFrag</b>
Drop any packet that requires fragmentation.
Possible values: YES, NO
Default value: NO

<b>dropFragCpuThreshold</b>
Threshold value, as a percentage of CPU usage, at which to drop packets that require fragmentation. Applies only if dropFragparameter is set to NO.
Minimum value: 1
Maximum value: 100

<b>srcIPRoundRobin</b>
Use a different source IPv6 address for each new session through a particular IPv6 tunnel, as determined by round robin selection of one of the SNIP6 addresses. This setting is ignored if a common global source IPv6 address has been specified for all the IPv6 tunnels. This setting does not apply to a tunnel for which a source IPv6 address has been specified.
Possible values: YES, NO
Default value: NO



##Example

set ip6TunnelParam -srcIP 9901::100 -dropFrag YES -dropFragCpuThreshold 95

##unset ip6TunnelParam

Resets the specified global parameters of IPv6 tunnels to their default settings. Refer to the set ip6TunnelParam command for parameter descriptions..Refer to the set  ip6TunnelParam command for meanings of the arguments.


##Synopsys

unset ip6TunnelParam [-srcIP] [-dropFrag] [-dropFragCpuThreshold] [-srcIPRoundRobin]


##Example

unset ip6TunnelParam -srcIP -dropFrag -dropFragCpuThreshold

##show ip6TunnelParam

Displays the global settings of IPv6 tunnels on the NetScaler appliance.


##Synopsys

show ip6TunnelParam


##Outputs

<b>srcIP</b>
Common source IPv6 address for all IPv6 tunnels. Must be a SNIP6 or VIP6 address.

<b>dropFrag</b>
Drop any packet that requires fragmentation.

<b>dropFragCpuThreshold</b>
Threshold value, as a percentage of CPU usage, at which to drop packets that require fragmentation. Applies only if dropFragparameter is set to NO.

<b>srcIPRoundRobin</b>
Use a different source IPv6 address for each new session through a particular IPv6 tunnel, as determined by round robin selection of one of the SNIP6 addresses. This setting is ignored if a common global source IPv6 address has been specified for all the IPv6 tunnels. This setting does not apply to a tunnel for which a source IPv6 address has been specified.



##Example

Tunnel Source IP: 9901::100Drop if Fragmentation Needed: YESCPU usage threshold to avoid fragmentation: 95

