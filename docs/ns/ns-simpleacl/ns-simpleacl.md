#ns simpleacl

The following operations can be performed on "ns simpleacl":


[add](#add-ns-simpleacl) | [clear](#clear-ns-simpleacl) | [rm](#rm-ns-simpleacl) | [flush](#flush-ns-simpleacl) | [show](#show-ns-simpleacl) | [stat](#stat-ns-simpleacl)

##add ns simpleacl

Adds a simple ACL rule to the NetScaler appliance. Simple ACL rules filter IPv4 packets on the basis of their source IP addresses and, optionally, the destination port and/or protocol. Any packet with the characteristics specified in the simple ACL rule is dropped.


##Synopsys

add ns simpleacl &lt;aclname> &lt;aclaction> [-td &lt;positive_integer>] -srcIP &lt;ip_addr> [-destPort &lt;port>  -protocol ( TCP | UDP )] [-TTL &lt;positive_integer>]


##Arguments

<b>aclname</b>
Name for the simple ACL rule. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the simple ACL rule is created.

<b>aclaction</b>
Drop incoming IPv4 packets that match the simple ACL rule.
Possible values: DENY

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>srcIP</b>
IP address to match against the source IP address of an incoming IPv4 packet.

<b>destPort</b>
Port number to match against the destination port number of an incoming IPv4 packet.
Omitting the port number creates an all-ports simple ACL rule, which matches any port. In that case, you cannot create another simple ACL rule specifying a specific port and the same source IPv4 address.

<b>protocol</b>
Protocol to match against the protocol of an incoming IPv4 packet. You must set this parameter if you have set the Destination Port parameter.
Possible values: TCP, UDP

<b>TTL</b>
Number of seconds, in multiples of four, after which the simple ACL rule expires. If you do not want the simple ACL rule to expire, do not specify a TTL value.
Minimum value: 4
Maximum value: 2147483647



##Example

add simpleacl rule1 DENY -srcIP 1.1.1.1 -destPort 80 -protocol TCPadd simpleacl rule2 DENY -srcIP 2.2.2.2 -TTL 600

##Related Commands

<ul><li><a href="../../..//">add ns acl</a></li><li><a href="../../..//">rm ns acl</a></li></ul>



##clear ns simpleacl

Removes all simple ACL rules from the NetScaler appliance.


##Synopsys

clear ns simpleacl


##rm ns simpleacl

Removes a simple ACL rule from the NetScaler appliance.


##Synopsys

rm ns simpleacl &lt;aclname> ...


##Arguments

<b>aclname</b>
Name of the simple ACL rule that you want to remove.



##Example

rm ns simpleacl rule1

##Related Commands

<ul><li><a href="../../..//">rm ns acl</a></li></ul>



##flush ns simpleacl

Terminates all established IPv4 connections that match any of the newly configured simple ACL rules.Note:  If you plan to create more than one simple ACL rule and flush existing connections that match any of them, you can minimize the affect on performance by first creating all of the simple ACL rules and then running flush only once.


##Synopsys

flush ns simpleacl -estSessions


##Arguments

<b>estSessions</b>



##show ns simpleacl

Displays settings of all the simple ACL rules or of the specified simple ACL rule. To display settings of all the simple ACL rules, run the command without any parameters. To display settings of a particular simple ACL rule, specify the name of the simple ACL rule.


##Synopsys

show ns simpleacl [&lt;aclname>]


##Arguments

<b>aclname</b>
Name of the simple ACL rule whose details you want the NetScaler appliance to display.



##Outputs

<b>aclaction</b>
Drop incoming IPv4 packets that match the simple ACL rule.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>srcIP</b>
Source IP address.

<b>stateflag</b>
SACL state flag.

<b>destPort</b>
Destination Port.

<b>protocol</b>
Protocol associated with the ACL rule.

<b>TTL</b>
Time to expire this ACL rule(in seconds).

<b>time</b>
Time when this acl is added.

<b>hits</b>
Number of hits for this ACL rule.

<b>devno</b>

<b>count</b>



##Example

show simpleacl rule1	Name: rule1                            Action: DENY	srcIP = 10.102.1.150	Protocol = TCP                         DestPort = 110	Hits: 5                                TTL: 200(seconds)

##stat ns simpleacl

Displays statistics related to the simple ACL rules.


##Synopsys

stat ns simpleacl [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

<b>SimpleACL hits (SACLHits)</b>
Packets matching a SimpleACL.

<b>SimpleACL misses (SACLMiss)</b>
Packets not matching any SimpleACL.

<b>SimpleACLs count (SACLsCount)</b>
Number of SimpleACLs configured.

<b>Allow SimpleACL hits (SACLAllow)</b>
Total packets that matched a SimpleACL with action ALLOW and got consumed by NetScaler.

<b>Bridge SimpleACL hits (SACLBdg)</b>
Total packets that matched a SimpleACL with action BRIDGE and got bridged by NetScaler.

<b>Deny SimpleACL hits (SACLDeny)</b>
Packets dropped because they match SimpleACL (Access Control List) with processing mode set to DENY.



##Example

stat simpleacl

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li><li><a href="../../../t-ns-part/t-ns-part">stat ns partition</a></li></ul>



