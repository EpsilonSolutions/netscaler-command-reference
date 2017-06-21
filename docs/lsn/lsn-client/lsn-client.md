#lsn client

The following operations can be performed on "lsn client":


[add](#add-lsn-client) | [bind](#bind-lsn-client) | [unbind](#unbind-lsn-client) | [show](#show-lsn-client) | [rm](#rm-lsn-client)

##add lsn client

Add LSN Client.


##Synopsys

add lsn client &lt;clientname>


##Arguments

<b>clientname</b>
Name for the LSN client entity. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN client is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn client1" or 'lsn client1').



##Example

add lsn client client1

##bind lsn client

Bind LSN Client with client network or host. There can be a maximum of 1 million LSN subscribers globally.


##Synopsys

bind lsn client &lt;clientname> ((-network &lt;ip_addr>  [-netmask &lt;netmask>]  [-td &lt;positive_integer>]) | -aclname &lt;string> | -network6 &lt;ipv6_addr|*> | -acl6name &lt;string>)


##Arguments

<b>clientname</b>
Name for the LSN client entity. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN client is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn client1" or 'lsn client1').

<b>network</b>
IPv4 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.
Default value: 0xFFFFFFFF

<b>aclname</b>
Name(s) of any configured extended ACL(s) whose action is ALLOW.
The condition specified in the extended ACL rule identifies the traffic from an LSN subscriber for which the NetScaler ADC is to perform large scale NAT.

<b>acl6name</b>
Name of any configured extended ACL6 whose action is ALLOW. The condition specified in the extended ACL6 rule is used as the condition for the LSN client.

<b>network6</b>
IPv6 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>td</b>
ID of the traffic domain on which this subscriber or the subscriber network (as specified by the network parameter) belongs. 
If you do not specify an ID, the subscriber or the subscriber network becomes part of the default traffic domain.
Default value: 0
Minimum value: 0
Maximum value: 4094



##Example

bind  lsn client client1 -network 1.1.1.0 -netmask 255.255.255.0 -td 0

##unbind lsn client

Unbind LSN Client with client network or host.


##Synopsys

unbind lsn client &lt;clientname> ((-network &lt;ip_addr>  [-netmask &lt;netmask>]  [-td &lt;positive_integer>]) | -aclname &lt;string> | -network6 &lt;ipv6_addr|*> | -acl6name &lt;string>)


##Arguments

<b>clientname</b>
Name for the LSN client entity. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN client is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn client1" or 'lsn client1').

<b>network</b>
IPv4 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.
Default value: 0xFFFFFFFF

<b>aclname</b>
Name(s) of any configured extended ACL(s) whose action is ALLOW.
The condition specified in the extended ACL rule identifies the traffic from an LSN subscriber for which the NetScaler ADC is to perform large scale NAT.

<b>acl6name</b>
Name of any configured extended ACL6 whose action is ALLOW. The condition specified in the extended ACL6 rule is used as the condition for the LSN client.

<b>network6</b>
IPv6 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>td</b>
ID of the traffic domain on which this subscriber or the subscriber network (as specified by the network parameter) belongs. 
If you do not specify an ID, the subscriber or the subscriber network becomes part of the default traffic domain.
Default value: 0
Minimum value: 0
Maximum value: 4094



##Example

unbind  lsn client client1 -network 1.1.1.0 -netmask 255.255.255.0 -td 0 

##show lsn client

Display LSN Client.


##Synopsys

show lsn client [&lt;clientname>]


##Arguments

<b>clientname</b>
Name for the LSN client entity. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN client is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn client1" or 'lsn client1').



##Outputs

<b>network</b>
IPv4 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.

<b>td</b>
ID of the traffic domain on which this subscriber or the subscriber network (as specified by the network parameter) belongs. 
If you do not specify an ID, the subscriber or the subscriber network becomes part of the default traffic domain.

<b>aclname</b>
Name(s) of any configured extended ACL(s) whose action is ALLOW.
The condition specified in the extended ACL rule identifies the traffic from an LSN subscriber for which the NetScaler ADC is to perform large scale NAT.

<b>acl6name</b>
Name of any configured extended ACL6 whose action is ALLOW. The condition specified in the extended ACL6 rule is used as the condition for the LSN client.

<b>network6</b>
IPv6 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn client client1

##rm lsn client

Remove LSN Client.


##Synopsys

rm lsn client &lt;clientname>


##Arguments

<b>clientname</b>
Name for the LSN client entity. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN client is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn client1" or 'lsn client1').



##Example

rm lsn client client1

