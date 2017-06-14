#forwardingSession

The following operations can be performed on "forwardingSession":


[add](#add-forwardingsession) | [set](#set-forwardingsession) | [rm](#rm-forwardingsession) | [show](#show-forwardingsession)

##add forwardingSession

Adds a forwarding session rule, which creates forwarding-session entries for traffic that originates from or is destined for a particular network and is forwarded by the NetScaler appliance. By default, the appliance does not create session entries for traffic that only forwards (L3 mode). Add a forwarding session rule for a case in which a client request that the appliance forwards to a server results in a response that has to return by the same path


##Synopsys

add forwardingSession &lt;name> ((&lt;network>  [&lt;netmask>]) | -acl6name &lt;string> | -aclname &lt;string>) [-td &lt;positive_integer>] [-connfailover ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the forwarding session rule. Can begin with a letter, number, or the underscore character (_), and can consist of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rule is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rule" or 'my rule').

<b>network</b>
An IPv4 network address or IPv6 prefix of a network from which the forwarded traffic originates or to which it is destined.

<b>acl6name</b>
Name of any configured ACL6 whose action is ALLOW. The rule of the ACL6 is used as a forwarding session rule.

<b>aclname</b>
Name of any configured ACL whose action is ALLOW. The rule of the ACL is used as a forwarding session rule.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094

<b>connfailover</b>
Synchronize connection information with the secondary appliance in a high availability (HA) pair. That is, synchronize all connection-related information for the forwarding session.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##set forwardingSession

Modifies parameters of a forwarding session rule.


##Synopsys

set forwardingSession &lt;name> [-connfailover ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the forwarding session rule. Required for identifying the forwarding session rule.

<b>connfailover</b>
Synchronize connection information with the secondary appliance in a high availability (HA) pair. That is, synchronize all connection-related information for the forwarding session.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set forwardsession fw1 -connfailover enabled.

##rm forwardingSession

Removes a forwarding session rule from the NetScaler appliance.


##Synopsys

rm forwardingSession &lt;name>


##Arguments

<b>name</b>
Name of the forwarding session rule to be removed.



##Example

rm forwardsession  name.

##show forwardingSession

Displays the settings of all forwarding session rules configured on the NetScaler appliance, or of the specified forwarding session rule.


##Synopsys

show forwardingSession [&lt;name>]


##Arguments

<b>name</b>
Name of the forwarding session rule whose details you want to display.

<b>format</b>

<b>level</b>



##Outputs

<b>network</b>
An IPv4 network address or IPv6 prefix of a network from which the forwarded traffic originates or to which it is destined.

<b>netmask</b>
Subnet mask associated with the network.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>aclname</b>
Name of any configured ACL whose action is ALLOW. The rule of the ACL is used as a forwarding session rule.

<b>acl6name</b>
Name of any configured ACL6 whose action is ALLOW. The rule of the ACL6 is used as a forwarding session rule.

<b>connfailover</b>
Synchronize connection information with the secondary appliance in a high availability (HA) pair. That is, synchronize all connection-related information for the forwarding session.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



