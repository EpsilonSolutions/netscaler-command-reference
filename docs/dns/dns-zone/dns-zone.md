#dns zone

The following operations can be performed on "dns zone":


[add](#add-dns-zone) | [set](#set-dns-zone) | [unset](#unset-dns-zone) | [rm](#rm-dns-zone) | [sign](#sign-dns-zone) | [unsign](#unsign-dns-zone) | [show](#show-dns-zone)

##add dns zone

Creates a DNS zone on the NetScaler appliance. Mandatory if you want to use the appliance to implement Domain Name Security Extensions (DNSSEC) for the zone. When you add a DNS resource record, if the domain name of the record belongs to the zone, the record is automatically added to the zone.


##Synopsys

add dns zone &lt;zoneName> -proxyMode ( YES | NO ) [-dnssecOffload ( ENABLED | DISABLED )  [-nsec ( ENABLED | DISABLED )]]


##Arguments

<b>zoneName</b>
Name of the zone to create.

<b>proxyMode</b>
Deploy the zone in proxy mode. Enable in the following scenarios:
* The load balanced DNS servers are authoritative for the zone and all resource records that are part of the zone. 
* The load balanced DNS servers are authoritative for the zone, but the NetScaler appliance owns a subset of the resource records that belong to the zone (partial zone ownership configuration). Typically seen in global server load balancing (GSLB) configurations, in which the appliance responds authoritatively to queries for GSLB domain names but forwards queries for other domain names in the zone to the load balanced servers.
In either scenario, do not create the zone's Start of Authority (SOA) and name server (NS) resource records on the appliance. 
Disable if the appliance is authoritative for the zone, but make sure that you have created the SOA and NS records on the appliance before you create the zone.
Possible values: YES, NO
Default value: ENABLED



##Example

add dns zone foo.bar -proxyMode NO -dnssec ENABLED

##set dns zone

Modifies the parameters of the specified DNS zone.


##Synopsys

set dns zone &lt;zoneName> [-proxyMode ( YES | NO )] [-dnssecOffload ( ENABLED | DISABLED )] [-nsec ( ENABLED | DISABLED )]


##Arguments

<b>zoneName</b>
Name of the zone.

<b>proxyMode</b>
Deploy the zone in proxy mode. Enable in the following scenarios:
* The load balanced DNS servers are authoritative for the zone and all resource records that are part of the zone. 
* The load balanced DNS servers are authoritative for the zone, but the NetScaler appliance owns a subset of the resource records that belong to the zone (partial zone ownership configuration). Typically seen in global server load balancing (GSLB) configurations, in which the appliance responds authoritatively to queries for GSLB domain names but forwards queries for other domain names in the zone to the load balanced servers.
In either scenario, do not create the zone's Start of Authority (SOA) and name server (NS) resource records on the appliance. 
Disable if the appliance is authoritative for the zone, but make sure that you have created the SOA and NS records on the appliance before you create the zone.
Possible values: YES, NO
Default value: ENABLED



##Example

set dns zone foo.bar -proxyMode NO -dnssec ENABLED

##unset dns zone

Use this command to remove dns zone settings.Refer to the set dns zone command for meanings of the arguments.


##Synopsys

unset dns zone &lt;zoneName> [-proxyMode] [-dnssecOffload] [-nsec]


##rm dns zone

Removes a DNS zone from the NetScaler appliance.


##Synopsys

rm dns zone &lt;zoneName>


##Arguments

<b>zoneName</b>
Name of the zone to remove.



##sign dns zone

Signs a DNS zone with a DNS key. Before you sign a zone, make sure that you've enabled DNSSEC by setting the global DNS parameter "Enable DNSSEC extension."


##Synopsys

sign dns zone &lt;zoneName> [-keyName &lt;string> ...]


##Arguments

<b>zoneName</b>
Name of the zone.

<b>keyName</b>
Name of the public/private DNS key pair with which to sign the zone. You can sign a zone with up to four keys.



##Example

sign dns zone abc.com. -keyname abc.com.zsk abc.com.ksk

##unsign dns zone

Unsigns the specified DNS zone with the specified DNS key.


##Synopsys

unsign dns zone &lt;zoneName> [-keyName &lt;string> ...]


##Arguments

<b>zoneName</b>
Name of the zone.

<b>keyName</b>
Name of the public-private DNS key pair with which to unsign the zone.



##Example

unsign dns zone abc.com. -keyname abc.com.zsk abc.com.ksk

##show dns zone

Displays the parameters of the specified DNS zone, along with information about the types of resource records available for each domain name in the zone. If no zone name is specified, just the parameters are shown, for all configured zones.


##Synopsys

show dns zone [&lt;zoneName> | -type &lt;type>]


##Arguments

<b>zoneName</b>
Name of the zone. Mutually exclusive with the type parameter.

<b>type</b>
Type of zone to display. Mutually exclusive with the DNS Zone (zoneName) parameter. Available settings function as follows:
* ADNS - Display all the zones for which the NetScaler appliance is authoritative.
* PROXY - Display all the zones for which the NetScaler appliance is functioning as a proxy server.
* ALL - Display all the zones configured on the appliance.
Possible values: ALL, ADNS, PROXY

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>proxyMode</b>
Deploy the zone in proxy mode. Enable in the following scenarios:
* The load balanced DNS servers are authoritative for the zone and all resource records that are part of the zone. 
* The load balanced DNS servers are authoritative for the zone, but the NetScaler appliance owns a subset of the resource records that belong to the zone (partial zone ownership configuration). Typically seen in global server load balancing (GSLB) configurations, in which the appliance responds authoritatively to queries for GSLB domain names but forwards queries for other domain names in the zone to the load balanced servers.
In either scenario, do not create the zone's Start of Authority (SOA) and name server (NS) resource records on the appliance. 
Disable if the appliance is authoritative for the zone, but make sure that you have created the SOA and NS records on the appliance before you create the zone.

<b>flags</b>
Flags controlling display.

<b>nsecBitarray</b>
Bit array representing the different record types configured for the domain nameNOTE: This attribute is deprecated.This is deprecated attribute.

<b>domain</b>
Domain name that belongs to the given zone

<b>nextRecs</b>
An array of record types associated with the nsec record.

<b>stateflag</b>
flags controlling display

<b>dnssecOffload</b>
Enable dnssec offload for this zone.

<b>nsec</b>
Enable nsec generation for dnssec offload.

<b>keyName</b>
Name of the public/private DNS key pair with which to sign the zone. You can sign a zone with up to four keys.

<b>sigInceptionTime</b>
The time when sign was done with this key.

<b>signed</b>
Integer which denote status of keys.

<b>expires</b>
Time period for which to consider the key valid, after the key is used to sign a zone.

<b>devno</b>

<b>count</b>



##Example

show dns zone foo.bar

