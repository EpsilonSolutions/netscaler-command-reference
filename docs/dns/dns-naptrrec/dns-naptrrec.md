#dns naptrRec

The following operations can be performed on "dns naptrRec":


[add](#add-dns-naptrrec) | [rm](#rm-dns-naptrrec) | [show](#show-dns-naptrrec)

##add dns naptrRec

Creates an NAPTR record. Each resource record is stored with a unique, internally generated record ID, which you can view and use to delete the record.


##Synopsys

add dns naptrRec &lt;domain> &lt;order> &lt;preference> [-flags &lt;string>] [-services &lt;string>] (-regexp &lt;expression> | -replacement &lt;string>) [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Name of the domain for the NAPTR record.

<b>order</b>
An integer specifying the order in which the NAPTR records MUST be processed in order to accurately represent the ordered list of Rules. The ordering is from lowest to highest
Minimum value: 0
Maximum value: 65535

<b>preference</b>
An integer specifying the preference of this NAPTR among NAPTR records having same order. lower the number, higher the preference.
Minimum value: 0
Maximum value: 65535

<b>flags</b>
flags for this NAPTR.

<b>services</b>
Service Parameters applicable to this delegation path.

<b>regexp</b>
The regular expression, that specifies the substitution expression for this NAPTR

<b>replacement</b>
The replacement domain name for this NAPTR.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

TBD

##rm dns naptrRec

Removes the specified NAPTR record from the specified domain. For EDNS Client Subnet (ECS) records, a subnet needs to be specified to remove a NAPTR record which is cached for that particular subnet


##Synopsys

rm dns naptrRec &lt;domain> ((&lt;order>  &lt;preference>  [-flags &lt;string>]  [-services &lt;string>]  (-regexp &lt;expression> | -replacement &lt;string>) ) | -recordId &lt;positive_integer>@) [-ecsSubnet &lt;ip_addr[/prefix]|ipv6_addr[/prefix]>]


##Arguments

<b>domain</b>
Name of the domain for the NAPTR record.

<b>order</b>
An integer specifying the order in which the NAPTR records MUST be processed in order to accurately represent the ordered list of Rules. The ordering is from lowest to highest
Minimum value: 0
Maximum value: 65535

<b>recordId</b>
Unique, internally generated record ID. View the details of the naptr record to obtain its record ID. Records can be removed by either specifying the domain name and record id OR by specifying
domain name and all other naptr record attributes as was supplied during the add command.
Minimum value: 1
Maximum value: 65535

<b>ecsSubnet</b>
Subnet for which the cached NAPTR record need to be removed.

<b>preference</b>
An integer specifying the preference of this NAPTR among NAPTR records having same order. lower the number, higher the preference.
Minimum value: 0
Maximum value: 65535

<b>flags</b>
flags for this NAPTR.

<b>services</b>
Service Parameters applicable to this delegation path.

<b>regexp</b>
The regular expression, that specifies the substitution expression for this NAPTR

<b>replacement</b>
The replacement domain name for this NAPTR.



##Example

 TBD 

##show dns naptrRec

Displays NAPTR records owned by the specified domain. If no domain name is specified, all configured NAPTR records are shown.


##Synopsys

show dns naptrRec [&lt;domain> | -type &lt;type>]


##Arguments

<b>domain</b>
Name of the domain for the NAPTR record.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY
Default value: ADNS



##Outputs

<b>order</b>
An integer specifying the order in which the NAPTR records MUST be processed in order to accurately represent the ordered list of Rules. The ordering is from lowest to highest

<b>preference</b>
An integer specifying the preference of this NAPTR among NAPTR records having same order. lower the number, higher the preference.

<b>flags</b>
flags for this NAPTR.

<b>services</b>
Service Parameters applicable to this delegation path.

<b>regexp</b>
The regular expression, that specifies the substitution expression for this NAPTR

<b>replacement</b>
The replacement domain name for this NAPTR.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>recordId</b>

<b>authType</b>
Authentication type.

<b>ecsSubnet</b>
Subnet for which this particular record is cached. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Applies to resource records obtained through proxy configurations only.

<b>vServerName</b>
Virtual server name.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns naptrRec spf.m.test.show dns naptrRec 

