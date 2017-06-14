#ns simpleacl6

The following operations can be performed on "ns simpleacl6":


[add](#add-ns-simpleacl6) | [clear](#clear-ns-simpleacl6) | [flush](#flush-ns-simpleacl6) | [rm](#rm-ns-simpleacl6) | [show](#show-ns-simpleacl6) | [stat](#stat-ns-simpleacl6)

##add ns simpleacl6

Adds a simple ACL6 rule to the NetScaler appliance. Simple ACL6 rules filter IPv6 packets on the basis of their source IP addresses and, optionally, the destination port and/or protocol. Any packet with the characteristics specified in the simple ACL6 rule is dropped.


##Synopsys

add ns simpleacl6 &lt;aclname> [-td &lt;positive_integer>] &lt;aclaction> -srcIPv6 &lt;ipv6_addr|null> [-destPort &lt;port>  -protocol ( TCP | UDP )] [-TTL &lt;positive_integer>]


##Arguments

<b>aclname</b>
Name for the simple ACL6 rule. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the simple ACL6 rule is created.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>aclaction</b>
Drop incoming IPv6 packets that match the simple ACL6 rule.
Possible values: DENY

<b>srcIPv6</b>
IP address to match against the source IP address of an incoming IPv6 packet.

<b>destPort</b>
Port number to match against the destination port number of an incoming IPv6 packet.
Omitting the port number creates an all-ports simple ACL6 rule, which matches any port. In that case, you cannot create another simple ACL6 rule specifying a specific port and the same source IPv6 address.

<b>TTL</b>
Number of seconds, in multiples of four, after which the simple ACL6 rule expires. If you do not want the simple ACL6 rule to expire, do not specify a TTL value.
Minimum value: 4
Maximum value: 2147483647



##Example

add simpleacl6 rule1 DENY -srcIP6 fe80::2c0:95ff:fec5:d9b8 -destPort 80 -protocol TCPadd simpleacl rule2 DENY -srcIP6 3ffe:100:100::1 -TTL 600

##clear ns simpleacl6

Removes all simple ACL6 rules from the NetScaler appliance.


##Synopsys

clear ns simpleacl6


##Example

clear ns simpleacl6

##flush ns simpleacl6

Terminates all established IPv6 connections that match any of the newly configured simple ACL6 rules.Note:  If you plan to create more than one simple ACL6 rule and flush existing connections that match any of them, you can minimize the affect on performance by first creating all of the simple ACL6 rules and then running flush only once.


##Synopsys

flush ns simpleacl6 -estSessions


##Arguments

<b>estSessions</b>



##rm ns simpleacl6

Removes a simple ACL6 rule from the NetScaler appliance.


##Synopsys

rm ns simpleacl6 &lt;aclname> ...


##Arguments

<b>aclname</b>
Name of the simple ACL6 rule that you want to remove.



##Example

rm ns simpleacl6 rule1

##Related Commands

<ul><li><a href="../../..//">rm ns acl6</a></li></ul>



##show ns simpleacl6

Displays settings of all the simple ACL6 rules or of the specified simple ACL6 rule. To display settings of all the simple ACL6 rules, run the command without any parameters. To display settings of a particular simple ACL6 rule, specify the name of the simple ACL6 rule.


##Synopsys

show ns simpleacl6 [&lt;aclname>]


##Arguments

<b>aclname</b>
Name of the simple ACL6 rule whose settings you want the NetScaler appliance to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>aclaction</b>
Action associated with the SACL6 rule.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>srcIPv6</b>
Source IP6 address.

<b>stateflag</b>
SACL6 state flag.

<b>destPort</b>
Destination Port.

<b>protocol</b>
Protocol associated with the ACL rule.

<b>TTL</b>
Time to expire this ACL rule(in seconds).

<b>hits</b>
Number of hits for this SACL6 rule.

<b>time</b>
Time when this acl is added.

<b>devno</b>

<b>count</b>



##Example

show simpleacl6 rule1	Name: rule1   	Action: DENY                          Hits: 5	srcIP6 = 3ffe:100:100::1	Protocol = TCP                         DestPort = 110	TTL: 200(seconds)

##stat ns simpleacl6

Displays statistics related to the simple ACL6 rules.


##Synopsys

stat ns simpleacl6 [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>SimpleACL6 hits (SACL6Hits)</b>
Packets matching a SimpleACL6.

<b>SimpleACL6 misses (SACL6Miss)</b>
Packets not matching any SimpleACL6.

<b>SimpleACLs6 count (SACL6sCount)</b>
Number of SimpleACL6s configured.

<b>Allow SimpleACL6 hits (SACL6Allow)</b>
Total packets that matched a SimpleACL6 with action ALLOW and got consumed by NetScaler.

<b>Bridge SimpleACL6 hits (SACL6Bdg)</b>
Total packets that matched a SimpleACL6 with action BRIDGE and got bridged by NetScaler.

<b>Deny SimpleACL6 hits (SACL6Deny)</b>
Packets dropped because they match SimpleACL6 with processing mode set to DENY.



##Example

stat simpleacl6

##Related Commands

<ul><li><a href="../../..//">stat ns</a></li><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li></ul>



