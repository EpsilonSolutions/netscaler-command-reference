#dns aaaaRec

The following operations can be performed on "dns aaaaRec":


[add](#add-dns-aaaarec) | [rm](#rm-dns-aaaarec) | [show](#show-dns-aaaarec)

##add dns aaaaRec

Creates a AAAA address record for the specified domain name. You cannot modify a AAAA address record.


##Synopsys

add dns aaaaRec &lt;hostName> &lt;IPv6Address> ... [-TTL &lt;secs>]


##Arguments

<b>hostName</b>
Domain name.

<b>IPv6Address</b>
One or more IPv6 addresses to assign to the domain name.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

add dns aaaarec www.mynw.com 3::4:5 -ttl 10

##rm dns aaaaRec

Removes an IPv6 address from a AAAA address record. The associated domain name must be specified. If no IPv6 address is specified, all AAAA records that belong to the specified domain name are removed.


##Synopsys

rm dns aaaaRec &lt;hostName> [&lt;IPv6Address> ...]


##Arguments

<b>hostName</b>
Domain name.

<b>IPv6Address</b>
IPv6 address(es) of the AAAA record(s) to remove from the specified domain name.



##Example

rm dns aaaarec www.mynw.com

##show dns aaaaRec

Displays the AAAA (IPv6) address record for the specified host name. If a hostname is not specified, all configured AAAA records are shown.


##Synopsys

show dns aaaaRec [&lt;hostName> | -type &lt;type>] [&lt;IPv6Address>]


##Arguments

<b>hostName</b>
Domain name.

<b>IPv6Address</b>
One or more IPv6 addresses to assign to the domain name.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>vServerName</b>
Vitual server name.

<b>authType</b>
Authentication type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



