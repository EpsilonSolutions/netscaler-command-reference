#dns txtRec

The following operations can be performed on "dns txtRec":


[add](#add-dns-txtrec) | [rm](#rm-dns-txtrec) | [show](#show-dns-txtrec)

##add dns txtRec

Creates a text (TXT) record for the specified domain name. Each resource record is stored with a unique, internally generated record ID, which you can view and use to delete the record. You cannot modify a TXT resource record.


##Synopsys

add dns txtRec &lt;domain> &lt;string> ... [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Name of the domain for the TXT record.

<b>string</b>
Information to store in the TXT resource record. Enclose the string in single or double quotation marks. A TXT resource record can contain up to six strings, each of which can contain up to 255 characters. If you want to add a string of more than 255 characters, evaluate whether splitting it into two or more smaller strings, subject to the six-string limit, works for you.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##Example

add dns txtRec spf.m.test. "v=spf1 ip4:1.2.3.0/24 ip4:1.3.4.0/24 ?all" add dns txtRec comments.m.test. "This is a CHARSTR" "This is another CHARSTR"

##rm dns txtRec

Removes the specified TXT record from the specified domain.


##Synopsys

rm dns txtRec &lt;domain> (&lt;string> ... | -recordId &lt;positive_integer>@)


##Arguments

<b>domain</b>
Name of the domain for the TXT record.

<b>string</b>
Complete set of text strings in the TXT record, entered in the order in which they are stored in the record. Mutually exclusive with the record ID parameter.

<b>recordId</b>
Unique, internally generated record ID. View the details of the TXT record to obtain its record ID. Mutually exclusive with the string parameter.
Minimum value: 1
Maximum value: 65535



##Example

rm dns txtRec spf.m.test. "v=spf1 ip4:1.2.3.0/24 ip4:1.3.4.0/24 ?all" rm dns txtRec comments.m.test. "This is a CHARSTR" "This is another CHARSTR" rm dns txtRec comments.m.test. -recordId 1411

##show dns txtRec

Displays TXT records owned by the specified domain. If no domain name is specified, all configured TXT records are shown.


##Synopsys

show dns txtRec [&lt;domain> | -type &lt;type>]


##Arguments

<b>domain</b>
Name of the domain for the TXT record.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY
Default value: ADNS



##Outputs

<b>string</b>
Information to store in the TXT resource record. Enclose the string in single or double quotation marks. A TXT resource record can contain up to six strings, each of which can contain up to 255 characters. If you want to add a string of more than 255 characters, evaluate whether splitting it into two or more smaller strings, subject to the six-string limit, works for you.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>recordId</b>

<b>authType</b>
Authentication type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns txtRec spf.m.test.show dns txtRec 

