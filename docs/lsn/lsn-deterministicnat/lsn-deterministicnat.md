#lsn deterministicNat

The following operations can be performed on "lsn deterministicNat":


##show lsn deterministicNat

Show LSN deterministic.


##Synopsys

show lsn deterministicNat (-clientname &lt;string> | -network6 &lt;ipv6_addr|*> | -natIP &lt;ip_addr>) [-subscrIP &lt;ip_addr>  [-td &lt;positive_integer>]]


##Arguments

<b>clientname</b>
The name of the LSN Client.

<b>network6</b>
IPv6 address of the LSN subscriber or B4 device.

<b>subscrIP</b>
The Client IP address.

<b>td</b>
The LSN client TD.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>natIP</b>
The NAT IP address.



##Outputs

<b>natprefix</b>
IPv6 address of the LSN  subscriber network(B4-Device) on whose traffic the NetScaler ADC perform Large Scale NAT.

<b>subscrIP</b>
The Subscriber IP address.

<b>natIP</b>
The NAT IP address.

<b>firstport</b>
The Application Protocol Port of the Profile.

<b>lastport</b>
The Application Protocol Ending Port of the Profile.

<b>srctd</b>
The LSN client TD.

<b>nattype</b>
Type of subscriber info(ex: nat44 or ds-lite).

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn deterministic

