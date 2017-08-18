#L3Param

The following operations can be performed on "L3Param":


[set](#set-l3param) | [unset](#unset-l3param) | [show](#show-l3param)

##set L3Param

Set Layer 3 related global settings on the NetScaler


##Synopsys

set L3Param [-srcnat ( ENABLED | DISABLED )] [-icmpGenRateThreshold &lt;positive_integer>] [-overrideRnat ( ENABLED | DISABLED )] [-dropDFFlag ( ENABLED | DISABLED )] [-mipRoundRobin ( ENABLED | DISABLED )] [-externalLoopBack ( ENABLED | DISABLED )] [-tnlPmtuWoConn ( ENABLED | DISABLED )] [-usipServerStrayPkt ( ENABLED | DISABLED )] [-forwardICMPFragments ( ENABLED | DISABLED )] [-dropIPFragments ( ENABLED | DISABLED )] [-AclLogTime &lt;positive_integer>] [-implicitACLAllow ( ENABLED | DISABLED )] [-dynamicRouting ( ENABLED | DISABLED )] [-ipv6DynamicRouting ( ENABLED | DISABLED )]


##Arguments

<b>srcnat</b>
Perform NAT if only the source is in the private network
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>icmpGenRateThreshold</b>
NS generated ICMP pkts per 10ms rate threshold
Default value: 100
Minimum value: 0

<b>overrideRnat</b>
USNIP/USIP settings override RNAT settings for configured
              service/virtual server traffic.. 
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dropDFFlag</b>
Enable dropping the IP DF flag.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>mipRoundRobin</b>
Enable round robin usage of mapped IPs.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>externalLoopBack</b>
Enable external loopback.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>tnlPmtuWoConn</b>
Enable/Disable learning PMTU of IP tunnel when ICMP error does not contain connection information.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>usipServerStrayPkt</b>
Enable detection of stray server side pkts in USIP mode.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>forwardICMPFragments</b>
Enable forwarding of ICMP fragments.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dropIPFragments</b>
Enable dropping of IP fragments.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>AclLogTime</b>
Parameter to tune acl logging time
Default value: 5000
Minimum value: 0

<b>implicitACLAllow</b>
Do not apply ACLs for internal ports
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>dynamicRouting</b>
Enable/Disable Dynamic routing on partition
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ipv6DynamicRouting</b>
Enable/Disable IPv6 Dynamic routing on partition
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset L3Param

Use this command to remove  L3Param settings.Refer to the set  L3Param command for meanings of the arguments.


##Synopsys

unset L3Param [-srcnat] [-icmpGenRateThreshold] [-overrideRnat] [-dropDFFlag] [-mipRoundRobin] [-externalLoopBack] [-tnlPmtuWoConn] [-usipServerStrayPkt] [-forwardICMPFragments] [-dropIPFragments] [-AclLogTime] [-implicitACLAllow] [-dynamicRouting] [-ipv6DynamicRouting]


##show L3Param

Displays the settings of global Layer 3 parameters.


##Synopsys

show L3Param


##Outputs

<b>srcnat</b>
Perform NAT if only the source is in the private network

<b>icmpGenRateThreshold</b>
NS generated ICMP pkts per 10ms rate threshold

<b>overrideRnat</b>
USNIP/USIP settings override RNAT settings for configured
              service/virtual server traffic..

<b>dropDFFlag</b>
Enable dropping the IP DF flag.

<b>mipRoundRobin</b>
Enable round robin usage of mapped IPs.

<b>externalLoopBack</b>
Enable external loopback.

<b>tnlPmtuWoConn</b>
Enable/Disable learning PMTU of IP tunnel when ICMP error does not contain connection information.

<b>usipServerStrayPkt</b>
Enable detection of stray server side pkts in USIP mode.

<b>forwardICMPFragments</b>
Enable forwarding of ICMP fragments.

<b>dropIPFragments</b>
Enable dropping of IP fragments.

<b>AclLogTime</b>
Parameter to tune acl logging time

<b>implicitACLAllow</b>
Do not apply ACLs for internal ports

<b>dynamicRouting</b>
Enable/Disable Dynamic routing on partition

<b>ipv6DynamicRouting</b>
Enable/Disable IPv6 Dynamic routing on partition



