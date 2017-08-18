#dns mxRec

The following operations can be performed on "dns mxRec":


[add](#add-dns-mxrec) | [rm](#rm-dns-mxrec) | [set](#set-dns-mxrec) | [unset](#unset-dns-mxrec) | [show](#show-dns-mxrec)

##add dns mxRec

Creates a mail exchange (MX) record for the specified domain name.


##Synopsys

add dns mxRec &lt;domain> -mx &lt;string> -pref &lt;positive_integer> [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain name for which to add the MX record.

<b>mx</b>
Host name of the mail exchange server.

<b>pref</b>
Priority number to assign to the mail exchange server. A domain name can have multiple mail servers, with a priority number assigned to each server. The lower the priority number, the higher the mail server's priority. When other mail servers have to deliver mail to the specified domain, they begin with the mail server with the lowest priority number, and use other configured mail servers, in priority order, as backups.
Minimum value: 0
Maximum value: 65535

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##rm dns mxRec

Removes the specified mail exchange (MX) record from the specified domain. For EDNS Client Subnet (ECS) records, a subnet needs to be specified to remove the specified mail exchange (MX) record which is cached for that particular subnet


##Synopsys

rm dns mxRec &lt;domain> &lt;mx> [-ecsSubnet &lt;ip_addr[/prefix]|ipv6_addr[/prefix]>]


##Arguments

<b>domain</b>
Domain name.

<b>mx</b>
Host name of the mail exchange server.

<b>ecsSubnet</b>
Subnet for which the cached MX record need to be removed.



##set dns mxRec

Modifies the priority number and TTL of the mail exchange (MX) record.


##Synopsys

set dns mxRec &lt;domain> -mx &lt;string> [-pref &lt;positive_integer>] [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain of the MX record to be modified.

<b>mx</b>
Host name of the mail exchange server to be modified.

<b>pref</b>
Priority number to assign to the mail exchange server. A domain name can have multiple mail servers, with a priority number assigned to each server. The lower the priority number, the higher the mail server's priority. When other mail servers have to deliver mail to the specified domain, they begin with the mail server with the lowest priority number, and use other configured mail servers, in priority order, as backups.
Minimum value: 0
Maximum value: 65535

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##unset dns mxRec

Use this command to remove dns mxRec settings.Refer to the set dns mxRec command for meanings of the arguments.


##Synopsys

unset dns mxRec &lt;domain> -mx &lt;string> -TTL


##show dns mxRec

Displays the mail exchange (MX) records for the specified domain. If no domain name is specified, all configured mail exchange records are shown.


##Synopsys

show dns mxRec [&lt;domain> | -type &lt;type>]


##Arguments

<b>domain</b>
Domain name.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY
Default value: ADNS



##Outputs

<b>mx</b>
Host name of the mail exchange server.

<b>pref</b>
Priority number to assign to the mail exchange server. A domain name can have multiple mail servers, with a priority number assigned to each server. The lower the priority number, the higher the mail server's priority. When other mail servers have to deliver mail to the specified domain, they begin with the mail server with the lowest priority number, and use other configured mail servers, in priority order, as backups.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>authType</b>
Record type.

<b>ecsSubnet</b>
Subnet for which this particular record is cached. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Applies to resource records obtained through proxy configurations only.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



