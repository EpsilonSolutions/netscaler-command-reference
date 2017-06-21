#dns cnameRec

The following operations can be performed on "dns cnameRec":


[add](#add-dns-cnamerec) | [rm](#rm-dns-cnamerec) | [show](#show-dns-cnamerec)

##add dns cnameRec

Creates a canonical name (CNAME) record, or alias, for the specified domain name.


##Synopsys

add dns cnameRec &lt;aliasName> &lt;canonicalName> [-TTL &lt;secs>]


##Arguments

<b>aliasName</b>
Alias for the canonical domain name.

<b>canonicalName</b>
Canonical domain name.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

add dns cnameRec www.mynw.org www.mynw.com -ttl 20

##rm dns cnameRec

Removes a canonical name (CNAME) record.


##Synopsys

rm dns cnameRec &lt;aliasName>


##Arguments

<b>aliasName</b>
Alias for which to remove the CNAME record.



##Example

rm dns cnamerec www.mynw.org

##show dns cnameRec

Displays the canonical name (CNAME) records configured for the specified alias. If no alias is specified, all configured CNAME records are displayed


##Synopsys

show dns cnameRec [&lt;aliasName> | -type &lt;type>]


##Arguments

<b>aliasName</b>
Alias for which to display CNAME records.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY
Default value: ADNS



##Outputs

<b>canonicalName</b>
Canonical domain name.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>vServerName</b>
GSLB Vitual server name to which this domain is bound

<b>authType</b>
Record type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns cnameRec www.mynw.org

