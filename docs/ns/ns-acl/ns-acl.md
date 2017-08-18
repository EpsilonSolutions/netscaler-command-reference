#ns acl

The following operations can be performed on "ns acl":


[add](#add-ns-acl) | [rm](#rm-ns-acl) | [set](#set-ns-acl) | [unset](#unset-ns-acl) | [enable](#enable-ns-acl) | [disable](#disable-ns-acl) | [stat](#stat-ns-acl) | [rename](#rename-ns-acl) | [show](#show-ns-acl)

##add ns acl

Adds an extended ACL rule to the NetScaler appliance. To commit this operation, you must apply the extended ACLs. Extended ACL rules filter data packets on the basis of various parameters, such as IP address, source port, action, and protocol.


##Synopsys

add ns acl &lt;aclname> &lt;aclaction> [-td &lt;positive_integer>] [-srcIP  [&lt;operator>]  &lt;srcIPVal>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIP  [&lt;operator>]  &lt;destIPVal>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-TTL &lt;positive_integer>] [-srcMac &lt;mac_addr>  [-srcMacMask &lt;string>]] [(-protocol &lt;protocol>  [-established]) | -protocolNumber &lt;positive_integer>] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-icmpType &lt;positive_integer>  [-icmpCode &lt;positive_integer>]] [-priority &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-logstate ( ENABLED | DISABLED )  [-ratelimit &lt;positive_integer>]]


##Arguments

<b>aclname</b>
Name for the extended ACL rule. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>aclaction</b>
Action to perform on incoming IPv4 packets that match the extended ACL rule.
Available settings function as follows:
* ALLOW - The NetScaler appliance processes the packet.
* BRIDGE - The NetScaler appliance bridges the packet to the destination without processing it.
* DENY - The NetScaler appliance drops the packet.
Possible values: BRIDGE, DENY, ALLOW

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>srcIP</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>operator</b>
Either the equals (=) or does not equal (!=) logical operator.
Possible values: =, !=, EQ, NEQ

<b>srcIPVal</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example:10.102.29.30-10.102.29.189.

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.

<b>srcPortVal</b>
Port number or range of port numbers to match against the source port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Maximum value: 65535

<b>destIP</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv4 packet.  In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>destIPVal</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv4 packet.  In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Note: The destination port can be specified only for TCP and UDP protocols.

<b>destPortVal</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Note: The destination port can be specified only for TCP and UDP protocols.
Maximum value: 65535

<b>TTL</b>
Number of seconds, in multiples of four, after which the extended ACL rule expires. If you do not want the extended ACL rule to expire, do not specify a TTL value.
Minimum value: 1
Maximum value: 2147483647

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv4 packet.

<b>srcMacMask</b>
Used to define range of Source MAC address. It takes string of 0 and 1, 0s are for exact match and 1s for wildcard. For matching first 3 bytes of MAC address, srcMacMask value "000000111111". 
Default value: "000000000000"

<b>protocol</b>
Protocol to match against the protocol of an incoming IPv4 packet.
Possible values: ICMP, IGMP, TCP, EGP, IGP, ARGUS, UDP, RDP, RSVP, EIGRP, L2TP, ISIS

<b>protocolNumber</b>
Protocol to match against the protocol of an incoming IPv4 packet.
Minimum value: 1
Maximum value: 255

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL rule to the incoming packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL rule to the incoming packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL rule to the incoming packets of all interfaces.

<b>established</b>
Allow only incoming TCP packets that have the ACK or RST bit set, if the action set for the ACL rule is ALLOW and these packets match the other conditions in the ACL rule.

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.
Minimum value: 0
Maximum value: 65536

<b>icmpCode</b>
Code of a particular ICMP message type to match against the ICMP code of an incoming ICMP packet.  For example, to block DESTINATION HOST UNREACHABLE messages, specify 3 as the ICMP type and 1 as the ICMP code.
If you set this parameter, you must set the ICMP Type parameter.
Minimum value: 0
Maximum value: 65536

<b>priority</b>
Priority for the extended ACL rule that determines the order in which it is evaluated relative to the other extended ACL rules. If you do not specify priorities while creating extended ACL rules, the ACL rules are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 100000

<b>state</b>
Enable or disable the extended ACL rule. After you apply the extended ACL rules, the NetScaler appliance compares incoming packets against the enabled extended ACL rules.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>logstate</b>
Enable or disable logging of events related to the extended ACL rule. The log messages are stored in the configured syslog or auditlog server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ratelimit</b>
Maximum number of log messages to be generated per second. If you set this parameter, you must enable the Log State parameter.
Default value: 100
Minimum value: 1
Maximum value: 10000



##Example

add ns acl restrict DENY -srcport 45-1024 -destIP 192.168.1.1 -protocol TCP

##rm ns acl

Removes an extended ACL rule from the NetScaler appliance. To commit this operation, you must apply the extended ACLs.


##Synopsys

rm ns acl &lt;aclname> ...


##Arguments

<b>aclname</b>
Name of the extended ACL rule that you want to remove.



##Example

rm ns acl restrict

##set ns acl

Modifies the parameters of an ACL rule. To commit this operation, you must apply the extended ACLs.


##Synopsys

set ns acl &lt;aclname> [-aclaction &lt;aclaction>] [-srcIP  [&lt;operator>]  &lt;srcIPVal>] [-srcPort  [&lt;operator>]  &lt;srcPortVal>] [-destIP  [&lt;operator>]  &lt;destIPVal>] [-destPort  [&lt;operator>]  &lt;destPortVal>] [-srcMac &lt;mac_addr>  [-srcMacMask &lt;string>]] [-protocol &lt;protocol> | -protocolNumber &lt;positive_integer>] [-icmpType &lt;positive_integer>  [-icmpCode &lt;positive_integer>]] [-vlan &lt;positive_integer> | -vxlan &lt;positive_integer>] [-interface &lt;interface_name>] [-priority &lt;positive_integer>] [-logstate ( ENABLED | DISABLED )] [-ratelimit &lt;positive_integer>] [-established]


##Arguments

<b>aclname</b>
Name of the ACL rule whose parameters you want to modify.

<b>aclaction</b>
Action to perform on incoming IPv4 packets that match the extended ACL rule.
Available settings function as follows:
* ALLOW - The NetScaler appliance processes the packet.
* BRIDGE - The NetScaler appliance bridges the packet to the destination without processing it.
* DENY - The NetScaler appliance drops the packet.
Possible values: BRIDGE, DENY, ALLOW

<b>srcIP</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>operator</b>
Either the equals (=) or does not equal (!=) logical operator.
Possible values: =, !=, EQ, NEQ

<b>srcIPVal</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example:10.102.29.30-10.102.29.189.

<b>srcPort</b>
Port number or range of port numbers to match against the source port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.

<b>srcPortVal</b>
Port number or range of port numbers to match against the source port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Maximum value: 65535

<b>destIP</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv4 packet.  In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>destIPVal</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv4 packet.  In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>destPort</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Note: The destination port can be specified only for TCP and UDP protocols.

<b>destPortVal</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Note: The destination port can be specified only for TCP and UDP protocols.
Maximum value: 65535

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv4 packet.

<b>srcMacMask</b>
Used to define range of Source MAC address. It takes string of 0 and 1, 0s are for exact match and 1s for wildcard. For matching first 3 bytes of MAC address, srcMacMask value "000000111111". 
Default value: "000000000000"

<b>protocol</b>
Protocol to match against the protocol of an incoming IPv4 packet.
Possible values: ICMP, IGMP, TCP, EGP, IGP, ARGUS, UDP, RDP, RSVP, EIGRP, L2TP, ISIS

<b>protocolNumber</b>
Protocol to match against the protocol of an incoming IPv4 packet.
Minimum value: 1
Maximum value: 255

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.
Minimum value: 0
Maximum value: 65536

<b>icmpCode</b>
Code of a particular ICMP message type to match against the ICMP code of an incoming ICMP packet.  For example, to block DESTINATION HOST UNREACHABLE messages, specify 3 as the ICMP type and 1 as the ICMP code.
If you set this parameter, you must set the ICMP Type parameter.
Minimum value: 0
Maximum value: 65536

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL rule to the incoming packets on all VLANs.
Minimum value: 1
Maximum value: 4094

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL rule to the incoming packets on all VXLANs.
Minimum value: 1
Maximum value: 16777215

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL rule to the incoming packets of all interfaces.

<b>priority</b>
Priority for the extended ACL rule that determines the order in which it is evaluated relative to the other extended ACL rules. If you do not specify priorities while creating extended ACL rules, the ACL rules are evaluated in the order in which they are created.
Minimum value: 1
Maximum value: 100000

<b>logstate</b>
Enable or disable logging of events related to the extended ACL rule. The log messages are stored in the configured syslog or auditlog server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>ratelimit</b>
Maximum number of log messages to be generated per second. If you set this parameter, you must enable the Log State parameter.
Default value: 100
Minimum value: 1
Maximum value: 10000

<b>established</b>
Allow only incoming TCP packets that have the ACK or RST bit set, if the action set for the ACL rule is ALLOW and these packets match the other conditions in the ACL rule.



##Example

set ns acl restrict -srcPort 50

##unset ns acl

Resets the attributes of the specified extended ACL rule. Attributes for which a default value is available revert to their default values. Refer to the set ns acl command for a description of the parameters..Refer to the set ns acl command for meanings of the arguments.


##Synopsys

unset ns acl &lt;aclname> [-srcIP] [-srcPort] [-destIP] [-destPort] [-srcMac] [-srcMacMask] [-protocol] [-icmpType] [-icmpCode] [-vlan] [-vxlan] [-interface] [-logstate] [-ratelimit] [-established]


##Example

unset ns acl rule1 -srcPort 

##enable ns acl

Enables an extended ACL rule. To commit this operation, you must apply the extended ACLs. After you apply the extended ACL rules, the NetScaler appliance compares incoming packets against the enabled extended ACL rules.


##Synopsys

enable ns acl &lt;aclname> ...


##Arguments

<b>aclname</b>
Name of the extended ACL rule that you want to enable.



##Example

enable ns acl foo

##disable ns acl

Disables an extended ACL rule. To commit this operation, you must apply the extended ACLs. After you apply the ACL rules, the NetScaler appliance does not compare incoming packets against the disabled extended ACL rules.


##Synopsys

disable ns acl &lt;aclname> ...


##Arguments

<b>aclname</b>
Name of the extended ACL rule that you want to disable.



##Example

disable ns acl foo

##stat ns acl

Displays statistics related to the extended ACL rules. To display statistics of all the extended ACL rules, run the command without any parameters. To display statistics of a particular extended ACL rule, specify the name of the extended ACL rule.


##Synopsys

stat ns acl [&lt;aclname>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>aclname</b>
Name of the extended ACL rule whose statistics you want the NetScaler appliance to display.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Bridge ACL hits (ACLBdg)</b>
Packets matching a bridge ACL, which is in transparent mode and bypasses service processing.

<b>Deny ACL hits (ACLDeny)</b>
Packets dropped because they match ACLs with processing mode set to DENY.

<b>Allow ACL hits (ACLAllow)</b>
Packets matching ACLs with processing mode set to ALLOW. NetScaler processes these packets.

<b>NAT ACL hits (ACLNAT)</b>
Packets matching a NAT ACL, resulting in a NAT session.

<b>ACL hits (ACLHits)</b>
Packets matching an ACL.

<b>ACL misses (ACLMiss)</b>
Packets not matching any ACL.

<b>ACL Count (ACLCount)</b>
Total number of ACL rules configured.

<b>Hits for this ACL (Hits)</b>
Number of times the acl was hit



##Example

stat acl

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li><li><a href="../../../t-ns-part/t-ns-part">stat ns partition</a></li></ul>



##rename ns acl

Renames an extended ACL rule.


##Synopsys

rename ns acl &lt;aclname> &lt;newName>


##Arguments

<b>aclname</b>
Name of the extended ACL rule that you want to rename.

<b>newName</b>
New name for the extended ACL rule. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rename acl rule rule-new

##show ns acl

Displays settings related to the extended ACL rules. To display settings of all the extended ACL rules, run the command without any parameters. To display settings of a particular extended ACL rule, specify the name of the extended ACL rule.


##Synopsys

show ns acl [&lt;aclname>]


##Arguments

<b>aclname</b>
Name of the extended ACL rule whose details you want the NetScaler appliance to display.



##Outputs

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>aclaction</b>
Action to perform on incoming IPv4 packets that match the extended ACL rule.
Available settings function as follows:
* ALLOW - The NetScaler appliance processes the packet.
* BRIDGE - The NetScaler appliance bridges the packet to the destination without processing it.
* DENY - The NetScaler appliance drops the packet.

<b>srcMac</b>
MAC address to match against the source MAC address of an incoming IPv4 packet.

<b>srcMacMask</b>
Used to define range of Source MAC address. It takes string of 0 and 1, 0s are for exact match and 1s for wildcard. For matching first 3 bytes of MAC address, srcMacMask value "000000111111".

<b>stateflag</b>
ACL state flag.

<b>protocol</b>
The protocol number in IP header or name.

<b>protocolNumber</b>
The protocol number in IP header or name.

<b>srcPortVal</b>
Port number or range of port numbers to match against the source port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.

<b>operator</b>
Either the equals (=) or does not equal (!=) logical operator.

<b>destPortVal</b>
Port number or range of port numbers to match against the destination port number of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example: 40-90.
Note: The destination port can be specified only for TCP and UDP protocols.

<b>srcIPVal</b>
IP address or range of IP addresses to match against the source IP address of an incoming IPv4 packet. In the command line interface, separate the range with a hyphen. For example:10.102.29.30-10.102.29.189.

<b>destIPVal</b>
IP address or range of IP addresses to match against the destination IP address of an incoming IPv4 packet.  In the command line interface, separate the range with a hyphen. For example: 10.102.29.30-10.102.29.189.

<b>vlan</b>
ID of the VLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VLAN. If you do not specify a VLAN ID, the appliance applies the ACL rule to the incoming packets on all VLANs.

<b>vxlan</b>
ID of the VXLAN. The NetScaler appliance applies the ACL rule only to the incoming packets of the specified VXLAN. If you do not specify a VXLAN ID, the appliance applies the ACL rule to the incoming packets on all VXLANs.

<b>state</b>
Enable or disable the extended ACL rule. After you apply the extended ACL rules, the NetScaler appliance compares incoming packets against the enabled extended ACL rules.

<b>TTL</b>
Number of seconds, in multiples of four, after which the extended ACL rule expires. If you do not want the extended ACL rule to expire, do not specify a TTL value.

<b>icmpType</b>
ICMP Message type to match against the message type of an incoming ICMP packet. For example, to block DESTINATION UNREACHABLE messages, you must specify 3 as the ICMP type.
Note: This parameter can be specified only for the ICMP protocol.

<b>icmpCode</b>
Code of a particular ICMP message type to match against the ICMP code of an incoming ICMP packet.  For example, to block DESTINATION HOST UNREACHABLE messages, specify 3 as the ICMP type and 1 as the ICMP code.
If you set this parameter, you must set the ICMP Type parameter.

<b>interface</b>
ID of an interface. The NetScaler appliance applies the ACL rule only to the incoming packets from the specified interface. If you do not specify any value, the appliance applies the ACL rule to the incoming packets of all interfaces.

<b>hits</b>
The hits of this ACL.

<b>established</b>
This flag indicates that the ACL should be used for TCP response traffic only.

<b>priority</b>
Priority for the extended ACL rule that determines the order in which it is evaluated relative to the other extended ACL rules. If you do not specify priorities while creating extended ACL rules, the ACL rules are evaluated in the order in which they are created.

<b>kernelstate</b>
The commit status of the ACL.

<b>logstate</b>
Enable or disable logging of events related to the extended ACL rule. The log messages are stored in the configured syslog or auditlog server.

<b>ratelimit</b>
Packet rate limit for acl logging

<b>time</b>
Time when this acl is applied.

<b>aclassociate</b>
ACL linked

<b>devno</b>

<b>count</b>



##Example

sh acl foo    Name: foo                               Action: ALLOW    Hits: 0    srcIP = 10.102.1.150    destIP = 202.54.12.47    srcMac:                               srcMacMask:	Protocol: TCP    srcPort                                destPort = 110    Vlan:                                   Interface:    Active Status: ENABLED                   Applied Status: NOTAPPLIED    Priority: 1027

