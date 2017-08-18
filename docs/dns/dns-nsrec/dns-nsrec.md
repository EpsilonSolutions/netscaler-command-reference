#dns nsRec

The following operations can be performed on "dns nsRec":


[add](#add-dns-nsrec) | [rm](#rm-dns-nsrec) | [show](#show-dns-nsrec)

##add dns nsRec

Creates a name server record for the specified domain.


##Synopsys

add dns nsRec &lt;domain> &lt;nameServer> [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain name.

<b>nameServer</b>
Host name of the name server to add to the domain.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##rm dns nsRec

Removes the specified name server record from the specified domain. For EDNS Client Subnet (ECS) records, a subnet needs to be specified to remove the specified name server record from the specified domain which is cached for that particular subnet


##Synopsys

rm dns nsRec &lt;domain> &lt;nameServer> [-ecsSubnet &lt;ip_addr[/prefix]|ipv6_addr[/prefix]>]


##Arguments

<b>domain</b>
Domain name.

<b>nameServer</b>
Name server to remove.

<b>ecsSubnet</b>
Subnet for which the cached name server record need to be removed.



##show dns nsRec

Displays the name server records for the specified domain. If no domain name is specified, all configured name server records are shown.


##Synopsys

show dns nsRec [&lt;domain> | -type &lt;type>]


##Arguments

<b>domain</b>
Domain name.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>nameServer</b>
Host name of the name server to add to the domain.

<b>ecsSubnet</b>
Subnet for which this particular record is cached. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Applies to resource records obtained through proxy configurations only.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>authType</b>
Record type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



