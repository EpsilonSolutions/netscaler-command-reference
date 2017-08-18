#lsn ip6profile

The following operations can be performed on "lsn ip6profile":


[add](#add-lsn-ip6profile) | [rm](#rm-lsn-ip6profile) | [show](#show-lsn-ip6profile)

##add lsn ip6profile

Add LSN IP6 profile.


##Synopsys

add lsn ip6profile &lt;name> -type ( DS-Lite | NAT64 ) [-natprefix &lt;ipv6_addr|*>] [-network6 &lt;ipv6_addr|*>]


##Arguments

<b>name</b>
Name for the LSN ip6 profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN ip6 profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn ip6 profile1" or 'lsn ip6 profile1').

<b>type</b>
IPv6 translation type for which to set the LSN IP6 profile parameters.
Possible values: DS-Lite, NAT64

<b>natprefix</b>
IPv6 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>network6</b>
IPv6 address of the NetScaler ADC AFTR device



##Example

add lsn ip6profile i1 -type DS-Lite -network6 1001::1/64

##rm lsn ip6profile

Remove LSN IP6Profile.


##Synopsys

rm lsn ip6profile &lt;name>


##Arguments

<b>name</b>
Name for the LSN ip6 profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN ip6 profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn ip6 profile1" or 'lsn ip6 profile1').



##Example

rm lsn ip6profile i1

##show lsn ip6profile

Display LSN IP6 profile.


##Synopsys

show lsn ip6profile [&lt;name>]


##Arguments

<b>name</b>
Name for the LSN ip6 profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN ip6 profile is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn ip6 profile1" or 'lsn ip6 profile1').



##Outputs

<b>type</b>
IPv6 translation type for which to set the LSN IP6 profile parameters.

<b>network6</b>
IPv6 address of the NetScaler ADC AFTR device

<b>natprefix</b>
IPv6 address(es) of the LSN subscriber(s) or subscriber network(s) on whose traffic you want the NetScaler ADC to perform Large Scale NAT.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn ip6 profile

