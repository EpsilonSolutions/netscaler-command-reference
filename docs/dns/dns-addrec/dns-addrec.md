#dns addRec

The following operations can be performed on "dns addRec":


[add](#add-dns-addrec) | [rm](#rm-dns-addrec) | [show](#show-dns-addrec)

##add dns addRec

Creates an IPv4 address record for the specified domain name. You cannot modify an address resource record.


##Synopsys

add dns addRec &lt;hostName> &lt;IPAddress> ... [-TTL &lt;secs>]


##Arguments

<b>hostName</b>
Domain name.

<b>IPAddress</b>
One or more IPv4 addresses to assign to the domain name.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

Add dns addrec www.mynw.com 65.200.211.139 -ttl 10

##rm dns addRec

Removes an IPv4 address from an address record. The associated domain name must be specified. If no IPv4 address is specified, all records that belong to the specified domain name are removed.


##Synopsys

rm dns addRec &lt;hostName> [&lt;IPAddress> ...]


##Arguments

<b>hostName</b>
Domain name.

<b>IPAddress</b>
IPv4 address(es) of the address records to remove from the specified domain name.



##Example

rm dns addrec www.mynw.com

##show dns addRec

Displays the IPv4 address record for the specified host name. If a hostname is not specified, all configured address records are shown.


##Synopsys

show dns addRec [&lt;hostName> | -type &lt;type>]


##Arguments

<b>hostName</b>
Domain name.

<b>type</b>
The address record type. The type can take 3 values:
ADNS -  If this is specified, all of the authoritative address records will be displayed.
PROXY - If this is specified, all of the proxy address records will be displayed.
ALL  -  If this is specified, all of the address records will be displayed.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>IPAddress</b>
IP addresses for the domain name.

<b>TTL</b>
The time to live, in seconds.

<b>vServerName</b>
Vitual server name.

<b>authType</b>
Authentication type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



