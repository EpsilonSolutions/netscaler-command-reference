#ipsecalg session

The following operations can be performed on "ipsecalg session":


[show](#show-ipsecalg-session) | [flush](#flush-ipsecalg-session)

##show ipsecalg session

Display all of the configured ipsec alg profiles


##Synopsys

show ipsecalg session [-sourceIP &lt;ip_addr|*>] [-natIP &lt;ip_addr>] [-destIP &lt;ip_addr|*>]


##Arguments

<b>sourceIP</b>
Original Source IP address

<b>natIP</b>
Natted Source IP address

<b>destIP</b>
Destination IP address



##Outputs

<b>sourceIP</b>
Original Source IP address

<b>natIP</b>
Natted Source IP address

<b>destIP</b>
Destination IP address

<b>spiIn</b>
Client SPI for ESP

<b>spiOut</b>
Server SPI for ESP

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ipsecalg session

##flush ipsecalg session

Flush IPSec Alg Sessions


##Synopsys

flush ipsecalg session [-sourceIP &lt;ip_addr|*>] [-natIP &lt;ip_addr>] [-destIP &lt;ip_addr|*>]


##Arguments

<b>sourceIP</b>
Original Source IP address

<b>natIP</b>
Natted Source IP address

<b>destIP</b>
Destination IP address



##Example

flush ipsecalg session

