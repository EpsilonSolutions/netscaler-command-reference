#MapBmr

The following operations can be performed on "MapBmr":


[add](#add-mapbmr) | [rm](#rm-mapbmr) | [bind](#bind-mapbmr) | [unbind](#unbind-mapbmr) | [show](#show-mapbmr)

##add MapBmr

Add MAP-T Basic Mapping rule.


##Synopsys

add MapBmr &lt;name> -RuleIpv6Prefix &lt;ipv6_addr|*> [-psidoffset &lt;positive_integer>] [-EAbitLength &lt;positive_integer>] [-psidlength &lt;positive_integer>]


##Arguments

<b>name</b>
Name for the Basic Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Basic Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8" ).
			The Basic Mapping Rule information allows a MAP BR to determine source IPv4 address from the IPv6 packet sent from MAP CE device.
			Also it allows to determine destination IPv6 address of MAP CE before sending packets to MAP CE

<b>RuleIpv6Prefix</b>
IPv6 prefix of Customer Edge(CE) device.MAP-T CE will send ipv6 packets with this ipv6 prefix as source ipv6 address prefix

<b>psidoffset</b>
Start bit position  of Port Set Identifier(PSID) value in Embedded Address (EA) bits.
Default value: 6
Minimum value: 1
Maximum value: 15

<b>EAbitLength</b>
The Embedded Address (EA) bit field encodes the CE-specific IPv4 address and port information.  The EA bit field, which is unique for a 
			          given Rule IPv6 prefix.
Default value: 16
Minimum value: 2
Maximum value: 47

<b>psidlength</b>
Length of Port Set IdentifierPort Set Identifier(PSID) in Embedded Address (EA) bits
Default value: 8
Minimum value: 1
Maximum value: 16



##Example

add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8

##rm MapBmr

Remove MAP Basic Mapping Rule.


##Synopsys

rm MapBmr &lt;name>


##Arguments

<b>name</b>
Name for the Basic Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Basic Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8" ).
			The Basic Mapping Rule information allows a MAP BR to determine source IPv4 address from the IPv6 packet sent from MAP CE device.
			Also it allows to determine destination IPv6 address of MAP CE before sending packets to MAP CE



##Example

rm network MapBmr bmr1

##bind MapBmr

Bind network to BMR rule.


##Synopsys

bind MapBmr &lt;name> (-network &lt;ip_addr>  [-netmask &lt;netmask>])


##Arguments

<b>name</b>
Name for the Basic Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Basic Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8" ).
			The Basic Mapping Rule information allows a MAP BR to determine source IPv4 address from the IPv6 packet sent from MAP CE device.
			Also it allows to determine destination IPv6 address of MAP CE before sending packets to MAP CE

<b>network</b>
IPv4 NAT address range of Customer Edge (CE).

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.
Default value: 0xFFFFFFFF



##Example

bind network MapBmr bmr1 -network 192.168.0.0 -netmask 255.255.255.0

##unbind MapBmr

unbind network from BMR rule.


##Synopsys

unbind MapBmr &lt;name> (-network &lt;ip_addr>  [-netmask &lt;netmask>])


##Arguments

<b>name</b>
Name for the Basic Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Basic Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8" ).
			The Basic Mapping Rule information allows a MAP BR to determine source IPv4 address from the IPv6 packet sent from MAP CE device.
			Also it allows to determine destination IPv6 address of MAP CE before sending packets to MAP CE

<b>network</b>
IPv4 NAT address range of Customer Edge (CE).

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.
Default value: 0xFFFFFFFF



##Example

unbind network MapBmr bmr1 -network 192.168.0.0 -netmask 255.255.255.0

##show MapBmr

Display Basic mapping rule.


##Synopsys

show MapBmr [&lt;name>]


##Arguments

<b>name</b>
Name for the Basic Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the  MAP Basic Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapBmr bmr1 -natprefix 2005::/64 -EAbitLength 16 -psidoffset 6 -portsharingratio 8" ).
			The Basic Mapping Rule information allows a MAP BR to determine source IPv4 address from the IPv6 packet sent from MAP CE device.
			Also it allows to determine destination IPv6 address of MAP CE before sending packets to MAP CE



##Outputs

<b>RuleIpv6Prefix</b>
IPv6 prefix of Customer Edge(CE) device.MAP-T CE will send ipv6 packets with this ipv6 prefix as source ipv6 address prefix

<b>network</b>
IPv4 NAT address range of Customer Edge (CE).

<b>netmask</b>
Subnet mask for the IPv4 address specified in the Network parameter.

<b>EAbitLength</b>
The Embedded Address (EA) bit field encodes the CE-specific IPv4 address and port information.  The EA bit field, which is unique for a 
			          given Rule IPv6 prefix.

<b>psidoffset</b>
Start bit position  of Port Set Identifier(PSID) value in Embedded Address (EA) bits.

<b>psidlength</b>
Length of Port Set IdentifierPort Set Identifier(PSID) in Embedded Address (EA) bits

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show network MapBmr bmr1

