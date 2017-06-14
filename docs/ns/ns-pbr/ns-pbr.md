#ns pbr

The following operations can be performed on "ns pbr":


[add](#add-ns-pbr) | [rm](#rm-ns-pbr) | [set](#set-ns-pbr) | [unset](#unset-ns-pbr) | [enable](#enable-ns-pbr) | [disable](#disable-ns-pbr) | [stat](#stat-ns-pbr) | [show](#show-ns-pbr)

##add ns pbr

Adds a policy based route (PBR) to the NetScaler appliance. To commit this operation, you must apply the PBRs.A PBR specifies criteria for selecting outgoing IPv4 packets and, typically, a next hop to which to send the selected packets. For example, you can configure the NetScaler appliance to route outgoing packets from a specific IP address or range to a particular next hop router.Note: The NetScaler appliance process PBRs before processing the RNAT rules.


##Synopsys

add ns pbr &lt;name> &lt;action> [-td &lt;positive_integer>] [-srcIP  [&lt;operator>]  &lt;srcIPVal>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIP  [&lt;operator>]  &lt;destIPVal>] [-destPort  [&lt;operator>]  &lt;destPortVal>] ((-nextHop  &lt;nextHopVal>) | (-ipTunnel  &lt;ipTunnelName>)) [-srcMac &lt;mac_addr>] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]] [-state ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the PBR. Must begin with an ASCII alphabetic or underscore \\(_\\) character, and must contain only ASCII alphanumeric, underscore, hash \\(\\#\\), period \\(.\\), space, colon \\(:\\), at \\(@\\), equals \\(=\\), and hyphen \\(-\\) characters. Can be changed after the PBR is created.

<b>action</b>
Action to perform on the outgoing IPv4 packets that match the PBR.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.
Possible values: ALLOW, DENY

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>srcIP</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>destIP</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv4 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>nextHop</b>
IP address of the next hop router or the name of the link load balancing virtual server to which to send matching packets if action is set to ALLOW.
If you specify a link load balancing (LLB) virtual server, which can provide a backup if a next hop link fails, first make sure that the next hops bound to the LLB virtual server are actually next hops that are directly connected to the NetScaler appliance. Otherwise, the NetScaler throws an error when you attempt to create the PBR.

<b>ipTunnel</b>
The Tunnel name.

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv4 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an outgoing IPv4 packet.
Possible values: ICMP, IGMP, TCP, EGP, IGP, ARGUS, UDP, RDP, RSVP, EIGRP, L2TP, ISIS

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an outgoing IPv4 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VXLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR only to the outgoing packets on the specified interface. If you do not specify any value, the appliance compares the PBR to the outgoing packets on all interfaces.

<b>priority</b>
Priority of the PBR, which determines the order in which it is evaluated relative to the other PBRs. If you do not specify priorities while creating PBRs, the PBRs are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 81920

<b>msr</b>
Monitor the route specified byte Next Hop parameter. This parameter is not applicable if you specify a link load balancing (LLB) virtual server name with the Next Hop parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>state</b>
Enable or disable the PBR. After you apply the PBRs, the NetScaler appliance compares outgoing packets to the enabled PBRs.
Possible values: ENABLED, DISABLED
Default value: XACLENABLED



##Example

add ns pbr a allow -srcip 10.102.37.252 -destip 10.10.10.2 -nexthop 11.11.11.2

##rm ns pbr

Removes a PBR from the NetScaler appliance. To commit this operation, you must apply the PBRs.


##Synopsys

rm ns pbr &lt;name> ...


##Arguments

<b>name</b>
Name of the PBR that you want to remove.



##Example

rm ns pbr a

##set ns pbr

Modifies the specified parameters of a PBR. To commit this operation, you must apply the PBRs.


##Synopsys

set ns pbr &lt;name> [-action ( ALLOW | DENY )] [-srcIP  [&lt;operator>]  &lt;srcIPVal>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIP  [&lt;operator>]  &lt;destIPVal>] [-destPort  [&lt;operator>]  &lt;destPortVal>] ((-nextHop  &lt;nextHopVal>) | (-ipTunnel  &lt;ipTunnelName>)) [-srcMac &lt;mac_addr>] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]]


##Arguments

<b>name</b>
Name of the PBR whose parameters you want to modify.

<b>action</b>
Action to perform on the outgoing IPv4 packets that match the PBR.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.
Possible values: ALLOW, DENY

<b>srcIP</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>destIP</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv4 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>nextHop</b>
IP address of the next hop router or the name of the link load balancing virtual server to which to send matching packets if action is set to ALLOW.
If you specify a link load balancing (LLB) virtual server, which can provide a backup if a next hop link fails, first make sure that the next hops bound to the LLB virtual server are actually next hops that are directly connected to the NetScaler appliance. Otherwise, the NetScaler throws an error when you attempt to create the PBR.

<b>ipTunnel</b>
The Tunnel name.

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv4 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an outgoing IPv4 packet.
Possible values: ICMP, IGMP, TCP, EGP, IGP, ARGUS, UDP, RDP, RSVP, EIGRP, L2TP, ISIS

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an outgoing IPv4 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VXLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR only to the outgoing packets on the specified interface. If you do not specify any value, the appliance compares the PBR to the outgoing packets on all interfaces.

<b>priority</b>
Priority of the PBR, which determines the order in which it is evaluated relative to the other PBRs. If you do not specify priorities while creating PBRs, the PBRs are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 81920

<b>msr</b>
Monitor the route specified byte Next Hop parameter. This parameter is not applicable if you specify a link load balancing (LLB) virtual server name with the Next Hop parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set ns pbr a -srcPort 50

##unset ns pbr

Resets the attributes of the specified PBR. Attributes for which a default value is available revert to their default values. Refer to the set ns pbr command for descriptions of the parameters..Refer to the set ns pbr command for meanings of the arguments.


##Synopsys

unset ns pbr &lt;name> [-srcIP] [-srcPort] [-destIP] [-destPort] [-nextHop] [-ipTunnel] [-srcMac] [-protocol] [-vlan] [-vxlan] [-interface] [-msr] [-monitor]


##Example

unset ns pbr rule1 -srcPort 

##enable ns pbr

Enables a PBR. To commit this operation, you must apply the PBRs. After you apply the PBRs, the NetScaler appliance compares outgoing packets to the enabled PBRs.


##Synopsys

enable ns pbr &lt;name> ...


##Arguments

<b>name</b>
Name of PBR that you want to enable.



##Example

enable ns pbr foo

##disable ns pbr

Disables a PBR. To commit this operation, you must apply the PBRs. After you apply the PBRs, the NetScaler appliance does not compare outgoing packets against the disabled PBRs


##Synopsys

disable ns pbr &lt;name> ...


##Arguments

<b>name</b>
Name of PBR that you want to disable.



##Example

disable ns pbr foo

##stat ns pbr

Displays statistics related to the PBRs. To display statistics of all the PBRs, run the command without any parameters. To display statistics of a particular PBR, specify the name of the PBR.


##Synopsys

stat ns pbr [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the PBR whose statistics you want the NetScaler appliance to display.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Allow PBR hits (PBRAllow)</b>
Total packets that matched the PBR (Policy-Based Routes) with action ALLOW

<b>Deny PBR hits (PBRDeny)</b>
Total packets that matched the PBR with action DENY

<b>PBR hits (PBRTotHits)</b>
Total packets that matched one of the configured PBR

<b>PBR misses (PBRMiss)</b>
Total packets that did not match any PBR

<b>Hits for this PBR (PBRHits)</b>
Number of times the pbr was hit



##Example

stat pbr

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



##show ns pbr

Displays settings related to the PBRs. To display settings of all the PBRs, run the command without any parameters. To display settings of a particular PBR, specify the name of the PBR.


##Synopsys

show ns pbr [&lt;name>] [-detail]


##Arguments

<b>name</b>
Name of the PBR whose details you want the NetScaler appliance to display.

<b>detail</b>
To get a detailed view.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>action</b>
Action to perform on the outgoing IPv4 packets that match the PBR.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv4 packet.

<b>protocol</b>
The protocol number in IP header or name.

<b>protocolNumber</b>
The protocol number in IP header or name.

<b>srcPortVal</b>
Port number or range of port numbers to match against the source port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>destPortVal</b>
Port number or range of port numbers to match against the destination port number of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>srcIPVal</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>destIPVal</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv4 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [10.102.29.30-10.102.29.189].

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VLANs.

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR only to the outgoing packets on the specified VXLAN. If you do not specify any interface ID, the appliance compares the PBR to the outgoing packets on all VXLANs.

<b>state</b>
If this route is UP/DOWN.

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR only to the outgoing packets on the specified interface. If you do not specify any value, the appliance compares the PBR to the outgoing packets on all interfaces.

<b>hits</b>
The hits of this PBR.

<b>priority</b>
Priority of the PBR, which determines the order in which it is evaluated relative to the other PBRs. If you do not specify priorities while creating PBRs, the PBRs are evaluated in the order in which they are created.

<b>operator</b>
Logical operator.

<b>kernelstate</b>
The commit status of the PBR.

<b>nextHopVal</b>
The Next Hop IP address or gateway name.

<b>ipTunnelName</b>
The iptunnel name where packets need to be forwarded upon.

<b>msr</b>
Whether Monitored Static Route(MSR) is enabled or disabled.

<b>monitor</b>
Name of the monitor, of type PING or ARP, configured on the NetScaler appliance to monitor the route specified by the Next Hop parameter. You must enable the MSR parameter before setting this parameter.

<b>totalprobes</b>
The total number of probes sent.

<b>totalfailedprobes</b>
The total number of failed probes.

<b>failedprobes</b>
Number of the current failed monitoring probes.

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>data</b>
Internal data of this route.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ns pbr a	Name: a                                Action: ALLOW    Hits: 0       srcIP = 10.102.37.252       destIP = 10.10.10.2       srcMac:                                Protocol:       Vlan:                                  Interface:       Active Status: ENABLED                 Applied Status: NOTAPPLIED       Priority: 10       NextHop: 11.11.11.2

