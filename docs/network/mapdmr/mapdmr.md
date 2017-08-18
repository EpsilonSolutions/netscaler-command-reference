#MapDmr

The following operations can be performed on "MapDmr":


[add](#add-mapdmr) | [rm](#rm-mapdmr) | [show](#show-mapdmr)

##add MapDmr

Add MAP-T Default Mapping rule.


##Synopsys

add MapDmr &lt;name> -BRIpv6Prefix &lt;ipv6_addr|*>


##Arguments

<b>name</b>
Name for the Default Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the MAP Default Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDmr map1 -BRIpv6Prefix 2003::/96").
			Default Mapping Rule (DMR) is defined in terms of the IPv6 prefix advertised by one or more BRs, which provide external connectivity.  A typical MAP-T CE will install an IPv4 default route using this rule.  A BR will use this rule when translating all outside IPv4 source addresses to the IPv6 MAP domain.

<b>BRIpv6Prefix</b>
IPv6 prefix of Border Relay (Netscaler) device.MAP-T CE will send ipv6 packets to this ipv6 prefix.The DMR IPv6 prefix length SHOULD be 64 bits long by default and in any case MUST NOT exceed 96 bits



##Example

add network MapDmr map1 -BRIpv6Prefix 2003::/96

##rm MapDmr

Remove MAP-T Default Mapping rule.


##Synopsys

rm MapDmr &lt;name>


##Arguments

<b>name</b>
Name for the Default Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the MAP Default Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDmr map1 -BRIpv6Prefix 2003::/96").
			Default Mapping Rule (DMR) is defined in terms of the IPv6 prefix advertised by one or more BRs, which provide external connectivity.  A typical MAP-T CE will install an IPv4 default route using this rule.  A BR will use this rule when translating all outside IPv4 source addresses to the IPv6 MAP domain.



##Example

rm network MapDmr map1

##show MapDmr

Display MAP-T Default Mapping rule.


##Synopsys

show MapDmr [&lt;name>]


##Arguments

<b>name</b>
Name for the Default Mapping Rule. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the MAP Default Mapping Rule is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "add network MapDmr map1 -BRIpv6Prefix 2003::/96").
			Default Mapping Rule (DMR) is defined in terms of the IPv6 prefix advertised by one or more BRs, which provide external connectivity.  A typical MAP-T CE will install an IPv4 default route using this rule.  A BR will use this rule when translating all outside IPv4 source addresses to the IPv6 MAP domain.



##Outputs

<b>BRIpv6Prefix</b>
IPv6 prefix of Border Relay (Netscaler) device.MAP-T CE will send ipv6 packets to this ipv6 prefix.The DMR IPv6 prefix length SHOULD be 64 bits long by default and in any case MUST NOT exceed 96 bits

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show network MapDmr map1

