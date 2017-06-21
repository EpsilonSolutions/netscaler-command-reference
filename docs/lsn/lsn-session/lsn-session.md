#lsn session

The following operations can be performed on "lsn session":


[show](#show-lsn-session) | [flush](#flush-lsn-session)

##show lsn session

Show LSN Session.


##Synopsys

show lsn session [-nattype ( NAT44 | DS-Lite )  [-network &lt;ip_addr>  [-netmask &lt;netmask>]  [-td &lt;positive_integer>]]  [-network6 &lt;ipv6_addr|*>]] [-clientname &lt;string>] [-natIP &lt;ip_addr>]


##Arguments

<b>nattype</b>
Type of sessions to be displayed.
Possible values: NAT44, DS-Lite
Default value: NAT44

<b>clientname</b>
Name of the LSN Client entity.

<b>network</b>
IP address or network address of subscriber(s).

<b>netmask</b>
Subnet mask for the IP address specified by the network parameter.
Default value: 0xFFFFFFFF

<b>network6</b>
IPv6 address of the LSN subscriber or B4 device.

<b>td</b>
Traffic domain ID of the LSN client entity.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>natIP</b>
Mapped NAT IP address used in LSN sessions.



##Outputs

<b>natprefix</b>
IPv6 address of the LSN subscriber(s) or subscriber network(B4-Device) on whose traffic the NetScaler ADC perform Large Scale NAT.

<b>subscrIP</b>
The Source IP address.

<b>subscrPort</b>
The Source Port.

<b>destIP</b>
The Destination IP address.

<b>destPort</b>
The Destination Port.

<b>natPort</b>
The NAT Port

<b>transportprotocol</b>
The Transport Protocol for the session.

<b>sessionestdir</b>
The Session establishment direction, session was established for outbound or inbound packet.

<b>dsttd</b>

<b>srctd</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn session

##flush lsn session

Flush LSN Session.


##Synopsys

flush lsn session [-nattype ( NAT44 | DS-Lite )  [-network &lt;ip_addr>  [-netmask &lt;netmask>]  [-td &lt;positive_integer>]]  [-network6 &lt;ipv6_addr|*>]] [-clientname &lt;string>] [-natIP &lt;ip_addr>  [-natPort &lt;port>]]


##Arguments

<b>nattype</b>
Type of sessions to be displayed.
Possible values: NAT44, DS-Lite
Default value: NAT44

<b>clientname</b>
Name of the LSN Client entity.

<b>network</b>
IP address or network address of subscriber(s).

<b>netmask</b>
Subnet mask for the IP address specified by the network parameter.
Default value: 0xFFFFFFFF

<b>network6</b>
IPv6 address of the LSN subscriber or B4 device.

<b>td</b>
Traffic domain ID of the LSN client entity.
Default value: 0
Minimum value: 0
Maximum value: 4094

<b>natIP</b>
Mapped NAT IP address used in LSN sessions.

<b>natPort</b>
Mapped NAT port used in the LSN sessions.



##Example

flush lsn session

