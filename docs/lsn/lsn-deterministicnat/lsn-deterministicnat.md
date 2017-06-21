#lsn deterministicNat

The following operations can be performed on "lsn deterministicNat":


##show lsn deterministicNat

Show LSN deterministic.


##Synopsys

show lsn deterministicNat (-clientname &lt;string> | (-subscrIP &lt;ip_addr>  [-td &lt;positive_integer>]) | -natIP &lt;ip_addr>)


##Arguments

<b>clientname</b>
The name of the LSN Client.

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

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn deterministic

