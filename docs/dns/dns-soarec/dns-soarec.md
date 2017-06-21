#dns soaRec

The following operations can be performed on "dns soaRec":


[add](#add-dns-soarec) | [rm](#rm-dns-soarec) | [set](#set-dns-soarec) | [unset](#unset-dns-soarec) | [show](#show-dns-soarec)

##add dns soaRec

Creates a Start of Authority (SOA) record. Note: You can set the SOA parameters that are associated with zone transfers. However, the NetScaler appliance currently does not support zone transfers.


##Synopsys

add dns soaRec &lt;domain> -originServer &lt;string> -contact &lt;string> [-serial &lt;positive_integer>] [-refresh &lt;secs>] [-retry &lt;secs>] [-expire &lt;secs>] [-minimum &lt;secs>] [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain name for which to add the SOA record.

<b>originServer</b>
Domain name of the name server that responds authoritatively for the domain.

<b>contact</b>
Email address of the contact to whom domain issues can be addressed. In the email address, replace the @ sign with a period (.). For example, enter domainadmin.example.com instead of domainadmin@example.com.

<b>serial</b>
The secondary server uses this parameter to determine whether it requires a zone transfer from the primary server.
Default value: 100
Minimum value: 0
Maximum value: 4294967294

<b>refresh</b>
Time, in seconds, for which a secondary server must wait between successive checks on the value of the serial number.
Default value: 3600
Maximum value: 4294967294

<b>retry</b>
Time, in seconds, between retries if a secondary server's attempt to contact the primary server for a zone refresh fails.
Default value: 3
Maximum value: 4294967294

<b>expire</b>
Time, in seconds, after which the zone data on a secondary name server can no longer be considered authoritative because all refresh and retry attempts made during the period have failed. After the expiry period, the secondary server stops serving the zone. Typically one week. Not used by the primary server.
Default value: 3600
Maximum value: 4294967294

<b>minimum</b>
Default time to live (TTL) for all records in the zone. Can be overridden for individual records.
Default value: 5
Maximum value: 2147483647

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##rm dns soaRec

Removes the Start of Authority (SOA) record for the specified domain name.


##Synopsys

rm dns soaRec &lt;domain>


##Arguments

<b>domain</b>
Domain name of the SOA record.



##set dns soaRec

Modifies the parameters of the specified Start Of Authority (SOA) record.


##Synopsys

set dns soaRec &lt;domain> [-originServer &lt;string>] [-contact &lt;string>] [-serial &lt;positive_integer>] [-refresh &lt;secs>] [-retry &lt;secs>] [-expire &lt;secs>] [-minimum &lt;secs>] [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain of the SOA record to be modified.

<b>originServer</b>
Domain name of the name server that responds authoritatively for the domain.

<b>contact</b>
Email address of the contact to whom domain issues can be addressed. In the email address, replace the @ sign with a period (.). For example, enter domainadmin.example.com instead of domainadmin@example.com.

<b>serial</b>
The secondary server uses this parameter to determine whether it requires a zone transfer from the primary server.
Default value: 100
Minimum value: 1
Maximum value: 4294967294

<b>refresh</b>
Time, in seconds, for which a secondary server must wait between successive checks on the value of the serial number.
Default value: 3600
Maximum value: 4294967294

<b>retry</b>
Time, in seconds, between retries if a secondary server's attempt to contact the primary server for a zone refresh fails.
Default value: 3
Maximum value: 4294967294

<b>expire</b>
Time, in seconds, after which the zone data on a secondary name server can no longer be considered authoritative because all refresh and retry attempts made during the period have failed. After the expiry period, the secondary server stops serving the zone. Typically one week. Not used by the primary server.
Default value: 3600
Maximum value: 4294967294

<b>minimum</b>
Default time to live (TTL) for all records in the zone. Can be overridden for individual records.
Default value: 5
Maximum value: 2147483647

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##unset dns soaRec

Use this command to remove dns soaRec settings.Refer to the set dns soaRec command for meanings of the arguments.


##Synopsys

unset dns soaRec &lt;domain> [-serial] [-refresh] [-retry] [-expire] [-minimum] [-TTL]


##show dns soaRec

Displays the parameters of the specified Start of Authority (SOA) record. If no domain name is specified, all SOA records are displayed.


##Synopsys

show dns soaRec [&lt;domain> | -type &lt;type>]


##Arguments

<b>domain</b>
The domain name.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>originServer</b>
Domain name of the name server that responds authoritatively for the domain.

<b>contact</b>
Email address of the contact to whom domain issues can be addressed. In the email address, replace the @ sign with a period (.). For example, enter domainadmin.example.com instead of domainadmin@example.com.

<b>serial</b>
The secondary server uses this parameter to determine whether it requires a zone transfer from the primary server.

<b>refresh</b>
Time, in seconds, for which a secondary server must wait between successive checks on the value of the serial number.

<b>retry</b>
Time, in seconds, between retries if a secondary server's attempt to contact the primary server for a zone refresh fails.

<b>expire</b>
Time, in seconds, after which the zone data on a secondary name server can no longer be considered authoritative because all refresh and retry attempts made during the period have failed. After the expiry period, the secondary server stops serving the zone. Typically one week. Not used by the primary server.

<b>minimum</b>
Default time to live (TTL) for all records in the zone. Can be overridden for individual records.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>authType</b>
Record type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



