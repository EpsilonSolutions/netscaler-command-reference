#dns srvRec

The following operations can be performed on "dns srvRec":


[add](#add-dns-srvrec) | [rm](#rm-dns-srvrec) | [set](#set-dns-srvrec) | [unset](#unset-dns-srvrec) | [show](#show-dns-srvrec)

##add dns srvRec

Creates a service (SRV) record for the service offered by the specified target host, in the specified domain.


##Synopsys

add dns srvRec &lt;domain> &lt;target> -priority &lt;positive_integer> -weight &lt;positive_integer> -port &lt;positive_integer> [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Domain name, which, by convention, is prefixed by the symbolic name of the desired service and the symbolic name of the desired protocol, each with an underscore (_) prepended. For example, if an SRV-aware client wants to discover a SIP service that is provided over UDP, in the domain example.com, the client performs a lookup for _sip._udp.example.com.

<b>target</b>
Target host for the specified service.

<b>priority</b>
Integer specifying the priority of the target host. The lower the number, the higher the priority. If multiple target hosts have the same priority, selection is based on the Weight parameter.
Minimum value: 0
Maximum value: 65535

<b>weight</b>
Weight for the target host. Aids host selection when two or more hosts have the same priority. A larger number indicates greater weight.
Minimum value: 0
Maximum value: 65535

<b>port</b>
Port on which the target host listens for client requests.
Minimum value: 0
Maximum value: 65535

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##rm dns srvRec

Removes, from the specified domain, the SRV record created for the service provided by the specified target host.


##Synopsys

rm dns srvRec &lt;domain> &lt;target> ...


##Arguments

<b>domain</b>
Domain name of the SRV record.

<b>target</b>
Target host for the specified service.



##set dns srvRec

Modifies the parameters of the specified service (SRV) record.


##Synopsys

set dns srvRec &lt;domain> &lt;target> [-priority &lt;positive_integer>] [-weight &lt;positive_integer>] [-port &lt;positive_integer>] [-TTL &lt;secs>]


##Arguments

<b>domain</b>
Name of the SRV record to be modified.

<b>target</b>
Target of the SRV record to be modified.

<b>priority</b>
Integer specifying the priority of the target host. The lower the number, the higher the priority. If multiple target hosts have the same priority, selection is based on the Weight parameter.
Minimum value: 0
Maximum value: 65535

<b>weight</b>
Weight for the target host. Aids host selection when two or more hosts have the same priority. A larger number indicates greater weight.
Minimum value: 0
Maximum value: 65535

<b>port</b>
Port on which the target host listens for client requests.
Minimum value: 0
Maximum value: 65535

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.
Default value: 3600
Maximum value: 2147483647



##unset dns srvRec

Use this command to remove dns srvRec settings.Refer to the set dns srvRec command for meanings of the arguments.


##Synopsys

unset dns srvRec &lt;domain> &lt;target> -TTL


##show dns srvRec

Displays the service (SRV) record configured for the specified target host and domain. If the domain name is not specified, all of the SRV records are shown.


##Synopsys

show dns srvRec [(&lt;domain>  [&lt;target>]) | -type &lt;type>]


##Arguments

<b>domain</b>
Domain name for which to display the SRV record.

<b>target</b>
Target host for the specified service.

<b>type</b>
Type of records to display. Available settings function as follows:
* ADNS - Display all authoritative address records.
* PROXY - Display all proxy address records.
* ALL - Display all address records.
Possible values: ALL, ADNS, PROXY



##Outputs

<b>priority</b>
Priority of the target host. This helps in server selection by the client.

<b>weight</b>
Weight for the target host. Aids host selection when two or more hosts have the same priority. A larger number indicates greater weight.

<b>port</b>
Port on which the target host listens for client requests.

<b>TTL</b>
Time to Live (TTL), in seconds, for the record. TTL is the time for which the record must be cached by DNS proxies. The specified TTL is applied to all the resource records that are of the same record type and belong to the specified domain name. For example, if you add an address record, with a TTL of 36000, to the domain name example.com, the TTLs of all the address records of example.com are changed to 36000. If the TTL is not specified, the NetScaler appliance uses either the DNS zone's minimum TTL or, if the SOA record is not available on the appliance, the default value of 3600.

<b>authType</b>
Record type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



