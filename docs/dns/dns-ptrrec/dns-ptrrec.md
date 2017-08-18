#dns ptrRec

The following operations can be performed on "dns ptrRec":


[add](#add-dns-ptrrec) | [rm](#rm-dns-ptrrec) | [show](#show-dns-ptrrec)

##add dns ptrRec

Creates a pointer (PTR) record for the specified reverse domain name.


##Synopsys

add dns ptrRec &lt;reverseDomain> &lt;domain> ... [-TTL &lt;secs>]


##Arguments

<b>reverseDomain</b>
Reversed domain name representation of the IPv4 or IPv6 address for which to create the PTR record. Use the "in-addr.arpa." suffix for IPv4 addresses and the "ip6.arpa." suffix for IPv6 addresses.

<b>domain</b>
Domain name for which to configure reverse mapping.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

add dns ptrrec 1.1.1.in-addr.arpa. abc.com

##rm dns ptrRec

Removes a pointer (PTR) record for the specified domain name and reverse domain name. For EDNS Client Subnet (ECS) records, a subnet needs to be specified to remove a PTR record for the specified domain name and reverse domain name which is cached for that particular subnet


##Synopsys

rm dns ptrRec &lt;reverseDomain> [-ecsSubnet &lt;ip_addr[/prefix]|ipv6_addr[/prefix]>] [&lt;domain> ...]


##Arguments

<b>reverseDomain</b>
Reverse domain name of the PTR record.

<b>ecsSubnet</b>
Subnet for which the cached PTR record need to be removed.

<b>domain</b>
Domain name for which to remove reverse mapping.



##Example

rm dns ptrrec 1.1.1.1.in-addr.arpa. ptr.com

##show dns ptrRec

Displays the pointer (PTR) record for the specified reverse domain name and domain name.


##Synopsys

show dns ptrRec [&lt;reverseDomain> | -type &lt;type>]


##Arguments

<b>reverseDomain</b>
Reversed domain name representation of the IPv4 or IPv6 address for which to create the PTR record. Use the "in-addr.arpa." suffix for IPv4 addresses and the "ip6.arpa." suffix for IPv6 addresses.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>domain</b>
Domain name for which to configure reverse mapping.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>authType</b>
Authentication type.

<b>ecsSubnet</b>
Subnet for which this particular record is cached. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Applies to resource records obtained through proxy configurations only.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



