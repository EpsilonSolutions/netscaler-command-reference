#lsn static

The following operations can be performed on "lsn static":


[add](#add-lsn-static) | [rm](#rm-lsn-static) | [show](#show-lsn-static)

##add lsn static

Add LSN Static Mapping.


##Synopsys

add lsn static &lt;name> &lt;transportprotocol> (&lt;subscrIP>  [&lt;network6>]) &lt;subscrPort> [-td &lt;positive_integer>] [&lt;natIP>  [&lt;natPort>]] [-destIP &lt;ip_addr>  [-dsttd &lt;positive_integer>]]


##Arguments

<b>name</b>
Name for the LSN static mapping entry. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn static1" or 'lsn static1').

<b>transportprotocol</b>
Protocol for the LSN mapping entry.
Possible values: TCP, UDP, ICMP, ALL

<b>subscrIP</b>
IPv4(NAT44 & DS-Lite)/IPv6(NAT64) address of an LSN subscriber for the LSN static mapping entry.

<b>subscrPort</b>
Port of the LSN subscriber for the LSN mapping entry. * represents all ports being used. Used in case of static wildcard
Maximum value: 65535

<b>network6</b>
B4 address in DS-Lite setup

<b>td</b>
ID of the traffic domain to which the subscriber belongs. 
If you do not specify an ID, the subscriber is assumed to be a part of the default traffic domain.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>natIP</b>
IPv4 address, already existing on the NetScaler ADC as type LSN, to be used as NAT IP address for this mapping entry.

<b>natPort</b>
NAT port for this LSN mapping entry. * represents all ports being used. Used in case of static wildcard
Maximum value: 65535

<b>destIP</b>
Destination IP address for the LSN mapping entry.

<b>dsttd</b>
ID of the traffic domain through which the destination IP address for this LSN mapping entry is reachable from the NetScaler ADC.
If you do not specify an ID, the destination IP address is assumed to be reachable through the default traffic domain, which has an ID of 0.
Default value: 0
Minimum value: 0
Maximum value: 4094



##Example

add lsn static 10.10.10.100 80

##rm lsn static

Remove LSN Static Mapping.


##Synopsys

rm lsn static &lt;name>


##Arguments

<b>name</b>
Name for the LSN static mapping entry. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn static1" or 'lsn static1').



##Example

rm lsn static

##show lsn static

Display LSN Static Mapping.


##Synopsys

show lsn static [&lt;name>] [-nattype &lt;nattype>]


##Arguments

<b>name</b>
Name for the LSN static mapping entry. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the LSN group is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "lsn static1" or 'lsn static1').

<b>nattype</b>
Type of sessions to be displayed.
Possible values: NAT44, DS-Lite, NAT64



##Outputs

<b>transportprotocol</b>
Protocol for the LSN mapping entry.

<b>subscrIP</b>
IPv4(NAT44 & DS-Lite)/IPv6(NAT64) address of an LSN subscriber for the LSN static mapping entry.

<b>subscrPort</b>
Port of the LSN subscriber for the LSN mapping entry. * represents all ports being used. Used in case of static wildcard

<b>network6</b>
B4 address in DS-Lite setup

<b>natIP</b>
IPv4 address, already existing on the NetScaler ADC as type LSN, to be used as NAT IP address for this mapping entry.

<b>natPort</b>
NAT port for this LSN mapping entry. * represents all ports being used. Used in case of static wildcard

<b>td</b>
ID of the traffic domain to which the subscriber belongs. 
If you do not specify an ID, the subscriber is assumed to be a part of the default traffic domain.

<b>destIP</b>
Destination IP address for the LSN mapping entry.

<b>dsttd</b>
ID of the traffic domain through which the destination IP address for this LSN mapping entry is reachable from the NetScaler ADC.
If you do not specify an ID, the destination IP address is assumed to be reachable through the default traffic domain, which has an ID of 0.

<b>status</b>
The status of the Mapping. Status could be Inactive, if mapping addition failed due to already existing dynamic/static mapping, port allocation failure.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn static

