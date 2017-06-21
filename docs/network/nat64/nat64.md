#nat64

The following operations can be performed on "nat64":


[add](#add-nat64) | [set](#set-nat64) | [unset](#unset-nat64) | [rm](#rm-nat64) | [stat](#stat-nat64) | [show](#show-nat64)

##add nat64

Configure a nat64 rule on the appliance.


##Synopsys

add nat64 &lt;name> &lt;acl6name> [-netProfile &lt;string>]


##Arguments

<b>name</b>
Name for the NAT64 rule. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rule is created. Choose a name that helps identify the NAT64 rule.

<b>acl6name</b>
Name of any configured ACL6 whose action is ALLOW.  IPv6 Packets matching the condition of this ACL6 rule and destination IP address of these packets matching the NAT64 IPv6 prefix are considered for NAT64 translation.

<b>netProfile</b>
Name of the configured netprofile. The NetScaler appliance selects one of the IP address in the netprofile as the source IP address of the translated IPv4 packet to be sent to the IPv4 server.



##set nat64

Set the configured nat64 rule.


##Synopsys

set nat64 &lt;name> [-acl6name &lt;string>] [-netProfile &lt;string>]


##Arguments

<b>name</b>
Name for the NAT64 rule. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rule is created. Choose a name that helps identify the NAT64 rule.

<b>acl6name</b>
Name of any configured ACL6 whose action is ALLOW.  IPv6 Packets matching the condition of this ACL6 rule and destination IP address of these packets matching the NAT64 IPv6 prefix are considered for NAT64 translation.

<b>netProfile</b>
Name of the configured netprofile. The NetScaler appliance selects one of the IP address in the netprofile as the source IP address of the translated IPv4 packet to be sent to the IPv4 server.



##Example

set nat64 rule1  -acl6name acl1 .

##unset nat64

Use this command to remove  nat64 settings.Refer to the set  nat64 command for meanings of the arguments.


##Synopsys

unset nat64 &lt;name> -netProfile


##rm nat64

Remove the configured nat64 rule.


##Synopsys

rm nat64 &lt;name>


##Arguments

<b>name</b>
Name for the NAT64 rule. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rule is created. Choose a name that helps identify the NAT64 rule.



##Example

rm nat64  name.

##stat nat64

Display statistics for nat64 sessions.


##Synopsys

stat nat64 [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>TCP Sessions (nat64TotTcpSessions)</b>
Total number of TCP sessions created by NAT64.

<b>UDP Sessions (nat64TotUdpSessions)</b>
Total number of UDP sessions created by NAT64.

<b>ICMP Sessions (nat64TotIcmpSessions)</b>
Total number of ICMP sessions created by NAT64.

<b>Total Sessions (nat64TotSessions)</b>
Total number of sessions created by NAT64.



##Example

stat nat64

##show nat64

Display the nat64 configuration.


##Synopsys

show nat64 [&lt;name>]


##Arguments

<b>name</b>
Name for the NAT64 rule. Must begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rule is created. Choose a name that helps identify the NAT64 rule.



##Outputs

<b>acl6name</b>
Name of any configured ACL6 whose action is ALLOW.  IPv6 Packets matching the condition of this ACL6 rule and destination IP address of these packets matching the NAT64 IPv6 prefix are considered for NAT64 translation.

<b>netProfile</b>
Name of the configured netprofile. The NetScaler appliance selects one of the IP address in the netprofile as the source IP address of the translated IPv4 packet to be sent to the IPv4 server.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



