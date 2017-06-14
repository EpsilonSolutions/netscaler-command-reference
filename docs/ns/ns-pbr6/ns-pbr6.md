#ns pbr6

The following operations can be performed on "ns pbr6":


[add](#add-ns-pbr6) | [renumber](#renumber-ns-pbr6) | [rm](#rm-ns-pbr6) | [set](#set-ns-pbr6) | [unset](#unset-ns-pbr6) | [enable](#enable-ns-pbr6) | [disable](#disable-ns-pbr6) | [stat](#stat-ns-pbr6) | [show](#show-ns-pbr6) | [clear](#clear-ns-pbr6) | [apply](#apply-ns-pbr6)

##add ns pbr6

Adds an IPv6 policy based route (PBR6) to the NetScaler appliance. To commit this operation, you must apply the PBR6s.A PBR6 specifies criteria for selecting outgoing IPv6 packets and, typically, a next hop to which to send the selected packets. For example, you can configure the NetScaler appliance to route outgoing packets from a specific IP address or range to a particular next hop router.Note: The NetScaler appliance process PBR6s before processing the RNAT rules.


##Synopsys

add ns pbr6 &lt;name> [-td &lt;positive_integer>] &lt;action> [-srcIPv6  [&lt;operator>]  &lt;srcIPv6Val>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIPv6  [&lt;operator>]  &lt;destIPv6Val>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-srcMac &lt;mac_addr>] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]] [-nextHop  &lt;nextHopVal>] [-nextHopVlan &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the PBR6. Must begin with an ASCII alphabetic or underscore \\(_\\) character, and must contain only ASCII alphanumeric, underscore, hash \\(\\#\\), period \\(.\\), space, colon \\(:\\), at \\(@\\), equals \\(=\\), and hyphen \\(-\\) characters. Can be changed after the PBR6 is created.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>action</b>
Action to perform on the outgoing IPv6 packets that match the PBR6.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.
Possible values: ALLOW, DENY

<b>srcIPv6</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].

<b>destIPv6</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv6 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv6 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an outgoing IPv6 packet.
Possible values: ICMPV6, TCP, UDP

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an outgoing IPv6 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VXLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified interface. If you do not specify a value, the appliance compares the PBR6 to the outgoing packets on all interfaces.

<b>priority</b>
Priority of the PBR6, which determines the order in which it is evaluated relative to the other PBR6s. If you do not specify priorities while creating PBR6s, the PBR6s are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 80000

<b>state</b>
Enable or disable the PBR6. After you apply the PBR6s, the NetScaler appliance compares outgoing packets to the enabled PBR6s.
Possible values: ENABLED, DISABLED
Default value: XACLENABLED

<b>msr</b>
Monitor the route specified by the Next Hop parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nextHop</b>
IP address of the next hop router to which to send matching packets if action is set to ALLOW. This next hop should be directly reachable from the appliance.

<b>nextHopVlan</b>
VLAN number to be used for link local nexthop .
Minimum value: 1
Maximum value: 4094



##Example

add ns pbr6 rule1 ALLOW -srcport 45-1024 -destIPv6 2001::45 -nexthop 2001::49

##renumber ns pbr6

Renumbers the priorities of PBR6s to multiples of 10.To commit this operation, you must apply the PBR6s.Enables you to assign a new PBR6 a priority that is between two existing, consecutively numbered priorities. For example, if two PBR6s, PBR6-1 and PBR6-2, have priorities 2 and 3 renumbering changes those priorities to 20 and 30. You can then add PBR6-3 with priority 25.


##Synopsys

renumber ns pbr6


##Example

renumber pbr6

##rm ns pbr6

Removes a PBR6 from the NetScaler appliance. To commit this operation, you must apply the PBR6s.


##Synopsys

rm ns pbr6 &lt;name> ...


##Arguments

<b>name</b>
Name of the PBR6 that you want to remove.



##Example

rm ns pbr6 rule1

##set ns pbr6

Modifies the specified parameters of a PBR6.To commit this operation, you must apply the PBR6s.


##Synopsys

set ns pbr6 &lt;name> [-action ( ALLOW | DENY )] [-srcIPv6  [&lt;operator>]  &lt;srcIPv6Val>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIPv6  [&lt;operator>]  &lt;destIPv6Val>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-srcMac &lt;mac_addr>] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-msr ( ENABLED | DISABLED )  [-monitor &lt;string>]] [-nextHop  &lt;nextHopVal>] [-nextHopVlan &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the PBR6 whose parameters you want to modify.

<b>action</b>
Action to perform on the outgoing IPv6 packets that match the PBR6.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.
Possible values: ALLOW, DENY

<b>srcIPv6</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>srcPort</b>
Source Port (range).

<b>destIPv6</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv6 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>destPort</b>
Destination Port (range).

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv6 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an outgoing IPv6 packet.
Possible values: ICMPV6, TCP, UDP

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an outgoing IPv6 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VXLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified interface. If you do not specify a value, the appliance compares the PBR6 to the outgoing packets on all interfaces.

<b>priority</b>
Priority of the PBR6, which determines the order in which it is evaluated relative to the other PBR6s. If you do not specify priorities while creating PBR6s, the PBR6s are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 80000

<b>msr</b>
Monitor the route specified by the Next Hop parameter.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nextHop</b>
IP address of the next hop router to which to send matching packets if action is set to ALLOW. This next hop should be directly reachable from the appliance.

<b>nextHopVlan</b>
VLAN number to be used for link local nexthop .
Minimum value: 1
Maximum value: 4094



##Example

set ns pbr6 rule1 -srcPort 50

##unset ns pbr6

Resets the attributes of the specified PBR6. Attributes for which a default value is available revert to their default values. Refer to the set ns pbr6 command for descriptions of the parameters..Refer to the set ns pbr6 command for meanings of the arguments.


##Synopsys

unset ns pbr6 &lt;name> [-srcIPv6] [-srcPort] [-destIPv6] [-destPort] [-srcMac] [-protocol] [-interface] [-vlan] [-vxlan] [-msr] [-monitor] [-nextHop] [-nextHopVlan]


##Example

unset ns pbr6 rule1 -srcPort 

##enable ns pbr6

Enables a PBR6. To commit this operation, you must apply the PBR6s.After you apply the PBR6s, the NetScaler appliance compares outgoing packets to the enabled PBR6.


##Synopsys

enable ns pbr6 &lt;name> ...


##Arguments

<b>name</b>
Name of PBR6 that you want to enable.



##Example

enable ns pbr6 rule1

##disable ns pbr6

Disables a PBR6. To commit this operation, you must apply the PBR6s.After you apply the PBR6s, the NetScaler appliance does not compare outgoing packets to the disabled PBR6s.


##Synopsys

disable ns pbr6 &lt;name> ...


##Arguments

<b>name</b>
Name of PBR6 that you want to disable.



##Example

disable ns pbr6 rule1

##stat ns pbr6

Displays statistics related to the PBR6s. To display statistics of all the PBR6s, run the command without any parameters. To display statistics of a particular PBR6, specify the name of the PBR6.


##Synopsys

stat ns pbr6 [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the PBR6 whose statistics you want the NetScaler appliance to display.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Allow PBR6 hits (PBR6Allow)</b>
Total packets that matched the PBR6 with action ALLOW

<b>Deny PBR6 hits (PBR6Deny)</b>
Total packets that matched PBR6 with action DENY

<b>PBR6 hits (PBR6TotHits)</b>
Total packets that matched one of the configured PBR6

<b>PBR6 misses (PBR6Miss)</b>
Total packets that did not match any PBR6

<b>Hits for this PBR6 (PBR6Hits)</b>
Number of times the pbr6 was hit



##Example

stat pbr6

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



##show ns pbr6

Displays settings related to the PBR6s. To display settings of all the PBR6s, run the command without any parameters. To display settings of a particular PBR6, specify the name of the PBR6.


##Synopsys

show ns pbr6 [&lt;name>] [-detail]


##Arguments

<b>name</b>
Name of the PBR6 whose settings you want the NetScaler appliance to display.

<b>detail</b>
To get a detailed view.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>action</b>
Action to perform on the outgoing IPv6 packets that match the PBR6.
Available settings function as follows:
* ALLOW - The NetScaler appliance sends the packet to the designated next-hop router.
* DENY - The NetScaler appliance applies the routing table for normal destination-based routing.

<b>srcMac</b>
MAC address to match against the source MAC address of an outgoing IPv6 packet.

<b>stateflag</b>
PBR6 state flag.

<b>protocol</b>
Protocol number in IPv6 header or name.

<b>protocolNumber</b>
Protocol number in IPv6 header or name.

<b>srcPortVal</b>
Port number or range of port numbers to match against the source port number of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].

<b>destPortVal</b>
Port number or range of port numbers to match against the destination port number of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>srcIPv6Val</b>
IP address or range of IP addresses to match against the source IP address of an outgoing IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>destIPv6Val</b>
IP address or range of IP addresses to match against the destination IP address of an outgoing IPv6 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>vlan</b>
ID of the VLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VLANs.

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified VXLAN. If you do not specify an interface ID, the appliance compares the PBR6 to the outgoing packets on all VXLANs.

<b>state</b>
If this route is UP/DOWN.

<b>kernelstate</b>
Commit status of the PBR6.

<b>interface</b>
ID of an interface. The NetScaler appliance compares the PBR6 only to the outgoing packets on the specified interface. If you do not specify a value, the appliance compares the PBR6 to the outgoing packets on all interfaces.

<b>hits</b>
Number of hits of this PBR6.

<b>priority</b>
Priority of the PBR6, which determines the order in which it is evaluated relative to the other PBR6s. If you do not specify priorities while creating PBR6s, the PBR6s are evaluated in the order in which they are created.

<b>operator</b>
Logical operator.

<b>msr</b>
Whether Monitored Static Route(MSR) is enabled or disabled.

<b>monitor</b>
Name of the monitor, of type PING6 or ARP, configured on the NetScaler appliance to monitor the route specified by the Next Hop parameter. You must enable the MSR parameter before setting the Monitor parameter.

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

<b>nextHopVal</b>
ID of the VLAN, if you have specified a link local address for the Next Hop parameter.

<b>nextHopVlan</b>
VLAN number to be used for link local nexthop .

<b>data</b>
Internal data of this route.

<b>devno</b>

<b>count</b>



##Example

show ns pbr6 rule11)      Name: r1                           Action: DENY        srcIPv6 = 2001::1        destIPv6        srcMac:                            Protocol:        Vlan:                              Interface:        Active Status: ENABLED             Applied Status: NOTAPPLIED        Priority: 10                       Hits: 0		Nexthop:

##clear ns pbr6

Removes all PBR6s from the NetScaler appliance. This operation does not require an explicit apply.


##Synopsys

clear ns pbr6


##Example

clear ns pbr6

##apply ns pbr6

Updates the PBR6's memory tree (lookup table), adding any new PBR6 and applying any modifications to the existing PBR6s. The lookup table includes the configuration of all the extended PBR6s on the NetScaler appliance. The NetScaler appliance uses the lookup table (not the configuration file) to filter the outgoing IPv6 packets.


##Synopsys

apply ns pbr6


##Example

apply ns pbr6

