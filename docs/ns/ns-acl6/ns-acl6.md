#ns acl6

The following operations can be performed on "ns acl6":


[add](#add-ns-acl6) | [rm](#rm-ns-acl6) | [set](#set-ns-acl6) | [unset](#unset-ns-acl6) | [enable](#enable-ns-acl6) | [disable](#disable-ns-acl6) | [stat](#stat-ns-acl6) | [rename](#rename-ns-acl6) | [show](#show-ns-acl6)

##add ns acl6

Adds an ACL6 rule to the NetScaler appliance. To commit this operation, you must apply the ACL6s. ACL6 rules filter data packets on the basis of various parameters, such as IP address, source port, action, and protocol.


##Synopsys

add ns acl6 &lt;acl6name> &lt;acl6action> [-td &lt;positive_integer>] [-srcIPv6  [&lt;operator>]  &lt;srcIPv6Val>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIPv6  [&lt;operator>]  &lt;destIPv6Val>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-TTL &lt;positive_integer>] [-srcMac &lt;mac_addr>] [(-protocol &lt;protocol>  [-established]) | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-icmpType &lt;positive_integer>  [-icmpCode &lt;positive_integer>]] [-priority &lt;positive_integer>] [-state ( ENABLED | DISABLED )]


##Arguments

<b>acl6name</b>
Name for the ACL6 rule. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the ACL6 rule is created.

<b>acl6action</b>
Action to perform on the incoming IPv6 packets that match the ACL6 rule.
Available settings function as follows:
* ALLOW - The NetScaler appliance processes the packet.
* BRIDGE - The NetScaler appliance bridges the packet to the destination without processing it.
* DENY - The NetScaler appliance drops the packet.
Possible values: BRIDGE, DENY, ALLOW

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>srcIPv6</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an incoming IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>destIPv6</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv6 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets. For example: [40-90].
Note: The destination port can be specified only for TCP and UDP protocols.

<b>TTL</b>
Time to expire this ACL6 (in seconds).
Minimum value: 1
Maximum value: 2147483647

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv6 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an incoming IPv6 packet.
Possible values: ICMPV6, TCP, UDP

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an incoming IPv6 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL6 rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL6 rule to the incoming packets from all interfaces.

<b>established</b>
Allow only incoming TCP packets that have the ACK or RST bit set if the action set for the ACL6 rule is ALLOW and these packets match the other conditions in the ACL6 rule.

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming IPv6 ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.
Maximum value: 65536

<b>icmpCode</b>
Code of a particular ICMP message type to match against the ICMP code of an incoming IPv6 ICMP packet.  For example, to block DESTINATION HOST UNREACHABLE messages, specify 3 as the ICMP type and 1 as the ICMP code.
If you set this parameter, you must set the ICMP Type parameter.
Maximum value: 65536

<b>priority</b>
Priority for the ACL6 rule, which determines the order in which it is evaluated relative to the other ACL6 rules. If you do not specify priorities while creating ACL6 rules, the ACL6 rules are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 80000

<b>state</b>
State of the ACL6.
Possible values: ENABLED, DISABLED
Default value: XACLENABLED



##Example

add ns acl6 rule1 DENY -srcport 45-1024 -destIPv6 2001::45 -protocol TCP

##Related Commands

<ul><li><a href="../../../s-/s-">clear ns acls6</a></li><li><a href="../../../s-/s-">apply ns acls6</a></li></ul>



##rm ns acl6

Removes an ACL6 rule from the NetScaler appliance. To commit this operation, you must apply the ACL6s.


##Synopsys

rm ns acl6 &lt;acl6name> ...


##Arguments

<b>acl6name</b>
Name of the ACL6 rule that you want to remove.



##Example

rm ns acl6 rule1

##Related Commands

<ul><li><a href="../../../s-/s-">apply ns acls6</a></li><li><a href="../../../s-/s-">clear ns acls6</a></li></ul>



##set ns acl6

Modifies the parameters of an ACL6 rule. To commit this operation, you must apply the ACL6s.


##Synopsys

set ns acl6 &lt;acl6name> [-aclaction &lt;aclaction>] [-srcIPv6  [&lt;operator>]  &lt;srcIPv6Val>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIPv6  [&lt;operator>]  &lt;destIPv6Val>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-srcMac &lt;mac_addr>] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-icmpType &lt;positive_integer>  [-icmpCode &lt;positive_integer>]] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-established]


##Arguments

<b>acl6name</b>
Name of the ACL6 rule whose parameters you want to modify.

<b>aclaction</b>
Action associated with the ACL6.
Possible values: BRIDGE, DENY, ALLOW

<b>srcIPv6</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv6 packet. In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>srcPort</b>
Source Port (range).

<b>destIPv6</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv6 packet.  In the command line interface, separate the range with a hyphen and enclose within brackets.

<b>destPort</b>
Destination Port (range).

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv6 packet.

<b>protocol</b>
Protocol, identified by protocol name, to match against the protocol of an incoming IPv6 packet.
Possible values: ICMPV6, TCP, UDP

<b>protocolNumber</b>
Protocol, identified by protocol number, to match against the protocol of an incoming IPv6 packet.
Minimum value: 1
Maximum value: 255

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming IPv6 ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.
Maximum value: 65536

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL6 rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL6 rule to the incoming packets from all interfaces.

<b>priority</b>
Priority for the ACL6 rule, which determines the order in which it is evaluated relative to the other ACL6 rules. If you do not specify priorities while creating ACL6 rules, the ACL6 rules are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 80000

<b>established</b>
Allow only incoming TCP packets that have the ACK or RST bit set if the action set for the ACL6 rule is ALLOW and these packets match the other conditions in the ACL6 rule.



##Example

set ns acl6 rule1 -srcPort 50

##Related Commands

<ul><li><a href="../../../s-/s-">clear ns acls6</a></li><li><a href="../../../s-/s-">apply ns acls6</a></li></ul>



##unset ns acl6

Resets the attributes of the specified ACL6 rule. To commit this operation, you must apply the ACL6s.Attributes for which a default value is available revert to their default values. Refer to the set ns acl6 command for descriptions of the parameters..Refer to the set ns acl6 command for meanings of the arguments.


##Synopsys

unset ns acl6 &lt;acl6name> [-srcIPv6] [-srcPort] [-destIPv6] [-destPort] [-srcMac] [-protocol] [-icmpType] [-icmpCode] [-vlan] [-vxlan] [-interface] [-established]


##Example

unset ns acl6 rule1 -srcPort 

##Related Commands

<ul><li><a href="../../../s-/s-">clear ns acls6</a></li><li><a href="../../../s-/s-">apply ns acls6</a></li></ul>



##enable ns acl6

Enables an ACL6 rule. To commit this operation, you must apply the ACL6s.After you apply the ACL6 rules, the NetScaler appliance compares incoming IPv6 packets to the enabled ACL6 rules.


##Synopsys

enable ns acl6 &lt;acl6name> ...


##Arguments

<b>acl6name</b>
Name of ACL6 rule that you want to enable.



##Example

enable ns acl6 rule1

##Related Commands

<ul><li><a href="../../../s-/s-">apply ns acls6</a></li><li><a href="../../../s-/s-">clear ns acls6</a></li></ul>



##disable ns acl6

Disables an ACL6 rule. To commit this operation, you must apply the ACL6s.After you apply the ACL6 rules, the NetScaler appliance does not compare incoming IPv6 packets to the disabled ACL6 rules.


##Synopsys

disable ns acl6 &lt;acl6name> ...


##Arguments

<b>acl6name</b>
Name of ACL6 rule that you want to disable.



##Example

disable ns acl6 rule1

##Related Commands

<ul><li><a href="../../../s-/s-">apply ns acls6</a></li><li><a href="../../../s-/s-">clear ns acls6</a></li></ul>



##stat ns acl6

Displays statistics related to the ACL6 rules. To display statistics of all the ACL6 rules, run the command without any parameters. To display statistics of a particular ACL6 rule, specify the name of the ACL6 rule.


##Synopsys

stat ns acl6 [&lt;acl6name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>acl6name</b>
Name of the ACL6 rule whose statistics you want the NetScaler appliance to display.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Bridge ACL6 hits (ACL6Bdg)</b>
Packets matching a bridge IPv6 ACL, which is in transparent mode and bypasses service processing.

<b>Deny ACL6 hits (ACL6Deny)</b>
Packets dropped because they match IPv6 ACLs with processing mode set to DENY.

<b>Allow ACL6 hits (ACL6Allow)</b>
Packets matching IPv6 ACLs with processing mode set to ALLOW. NetScaler processes these packets.

<b>NAT ACL6 hits (ACL6NAT)</b>
Packets matching a NAT ACL6, resulting in a NAT session.

<b>ACL6 hits (ACL6Hits)</b>
Packets matching an IPv6 ACL.

<b>ACL6 misses (ACL6Miss)</b>
Packets not matching any IPv6 ACL.

<b>NAT64 ACL6 hits (ACL6NAT64)</b>
Packets matching a NAT64 ACL6, resulting in a NAT64 translation.

<b>ACL6 Count (ACL6Count)</b>
Total number of ACL6 rules configured.

<b>Hits for this ACL6 (Hits)</b>
Number of times the acl6 was hit



##Example

stat acl6

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



##rename ns acl6

Renames an ACL6 rule. To commit this operation, you must apply the ACL6s.


##Synopsys

rename ns acl6 &lt;acl6name> &lt;newName>


##Arguments

<b>acl6name</b>
Name of the ACL6 rule that you want to rename.

<b>newName</b>
New name for the ACL6 rule. Must begin with an ASCII alphabetic or underscore \\(_\\) character, and must contain only ASCII alphanumeric, underscore, hash \\(\\#\\), period \\(.\\), space, colon \\(:\\), at \\(@\\), equals \\(=\\), and hyphen \\(-\\) characters.



##Example

rename acl6 rule rule-new

##show ns acl6

Displays settings related to the ACL6 rules. To display settings of all the ACL6 rules, run the command without any parameters. To display settings of a particular ACL6 rule, specify the name of the ACL6 rule.


##Synopsys

show ns acl6 [&lt;acl6name>]


##Arguments

<b>acl6name</b>
Name of the ACL6 rule whose details you want the NetScaler appliance to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>acl6action</b>
Action to perform on the incoming IPv6 packets that match the ACL6 rule.
Available settings function as follows:
* ALLOW - The NetScaler appliance processes the packet.
* BRIDGE - The NetScaler appliance bridges the packet to the destination without processing it.
* DENY - The NetScaler appliance drops the packet.

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv6 packet.

<b>stateflag</b>
ACL6 state flag.

<b>protocol</b>
Protocol number in IPv6 header or name.

<b>protocolNumber</b>
Protocol number in IPv6 header or name.

<b>srcPortVal</b>
Source port (range).

<b>destPortVal</b>
Destination port (range).

<b>srcIPv6Val</b>
Source IPv6 address (range).

<b>destIPv6Val</b>
Destination IPv6 address (range).

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VLANs.

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL6 rule only to the incoming packets on the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL6 rule to the incoming packets on all VXLANs.

<b>state</b>
State of the ACL6.

<b>kernelstate</b>
Commit status of the ACL6.

<b>TTL</b>
Time left to expire ACL6 (in seconds).

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming IPv6 ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.

<b>icmpCode</b>
Code of a particular ICMP message type to match against the ICMP code of an incoming IPv6 ICMP packet.  For example, to block DESTINATION HOST UNREACHABLE messages, specify 3 as the ICMP type and 1 as the ICMP code.
If you set this parameter, you must set the ICMP Type parameter.

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL6 rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL6 rule to the incoming packets from all interfaces.

<b>hits</b>
Number of hits of this ACL6.

<b>established</b>
This flag indicates that the ACL6 should be used for TCP response traffic only.

<b>priority</b>
Priority for the ACL6 rule, which determines the order in which it is evaluated relative to the other ACL6 rules. If you do not specify priorities while creating ACL6 rules, the ACL6 rules are evaluated in the order in which they are created.

<b>operator</b>
Logical operator.

<b>time</b>
Time when this acl is applied.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>devno</b>

<b>count</b>



##Example

show ns acl6 rule11)      Name: r1                           Action: DENY        srcIPv6 = 2001::1        destIPv6        srcMac:                            Protocol:        Vlan:                              Interface:        Active Status: ENABLED             Applied Status: NOTAPPLIED        Priority: 10                       Hits: 0        TTL:

