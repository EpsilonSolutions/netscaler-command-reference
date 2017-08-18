#dns proxyRecords

The following operations can be performed on "dns proxyRecords":


##flush dns proxyRecords

Flushes all/selected ( via -type or -negRecType )  proxy records from the DNS cache on the NetScaler appliance.


##Synopsys

flush dns proxyRecords (-type &lt;type> | -negRecType ( NXDOMAIN | NODATA ))


##Arguments

<b>type</b>
Filter the DNS records to be flushed.e.g flush dns proxyRecords -type A   will flush only the A records from the cache. 
Possible values: A, NS, CNAME, SOA, MX, AAAA, SRV, RRSIG, NSEC, DNSKEY, PTR, TXT, NAPTR

<b>negRecType</b>
Filter the Negative DNS records i.e NXDOMAIN and NODATA entries to be flushed. e.g flush dns proxyRecords NXDOMAIN will flush only the NXDOMAIN entries from the cache
Possible values: NXDOMAIN, NODATA



