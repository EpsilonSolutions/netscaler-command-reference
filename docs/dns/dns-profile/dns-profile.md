#dns profile

The following operations can be performed on "dns profile":


[add](#add-dns-profile) | [set](#set-dns-profile) | [unset](#unset-dns-profile) | [rm](#rm-dns-profile) | [show](#show-dns-profile)

##add dns profile

Creates a DNS profile. These DNS profiles can be associated with DNS/DNS-TCP LB vservers ,ADNS/ADNS-TCP services , end resolvers and with DNS actions. DNS profiles dictate the caching and logging behavior for a DNS transaction.


##Synopsys

add dns profile &lt;dnsProfileName> [-dnsQueryLogging ( ENABLED | DISABLED )] [-dnsAnswerSecLogging ( ENABLED | DISABLED )] [-dnsExtendedLogging ( ENABLED | DISABLED )] [-dnsErrorLogging ( ENABLED | DISABLED )] [-cacheRecords ( ENABLED | DISABLED )] [-cacheNegativeResponses ( ENABLED | DISABLED )] [-dropMultiQueryRequest ( ENABLED | DISABLED )] [-cacheECSResponses ( ENABLED | DISABLED )]


##Arguments

<b>dnsProfileName</b>
Name of the DNS profile

<b>dnsQueryLogging</b>
DNS query logging; if enabled, DNS query information such as DNS query id, DNS query flags , DNS domain name and DNS query type will be logged
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsAnswerSecLogging</b>
DNS answer section; if enabled, answer section in the response will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsExtendedLogging</b>
DNS extended logging; if enabled, authority and additional section in the response will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsErrorLogging</b>
DNS error logging; if enabled, whenever error is encountered in DNS module reason for the error will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cacheRecords</b>
Cache resource records in the DNS cache. Applies to resource records obtained through proxy configurations only. End resolver and forwarder configurations always cache records in the DNS cache, and you cannot disable this behavior. When you disable record caching, the appliance stops caching server responses. However, cached records are not flushed. The appliance does not serve requests from the cache until record caching is enabled again.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cacheNegativeResponses</b>
Cache negative responses in the DNS cache. When disabled, the appliance stops caching negative responses except referral records. This applies to all configurations - proxy, end resolver, and forwarder. However, cached responses are not flushed. The appliance does not serve negative responses from the cache until this parameter is enabled again.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>dropMultiQueryRequest</b>
Drop the DNS requests containing multiple queries. When enabled, DNS requests containing multiple queries will be dropped. In case of proxy configuration by default the DNS request containing multiple queries is forwarded to the backend and in case of ADNS and Resolver configuration NOCODE error response will be sent to the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cacheECSResponses</b>
Cache DNS responses with EDNS Client Subnet(ECS) option in the DNS cache. When disabled, the appliance stops caching responses with ECS option. This is relevant to proxy configuration. Enabling/disabling support of ECS option when NetScaler is authoritative for a GSLB domain is supported using a knob in GSLB vserver. In all other modes, ECS option is ignored.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add dns profile testprofile -caching yes

##set dns profile

Modifies the attributes of a DNS profile.


##Synopsys

set dns profile &lt;dnsProfileName> [-dnsQueryLogging ( ENABLED | DISABLED )] [-dnsAnswerSecLogging ( ENABLED | DISABLED )] [-dnsExtendedLogging ( ENABLED | DISABLED )] [-dnsErrorLogging ( ENABLED | DISABLED )] [-cacheRecords ( ENABLED | DISABLED )] [-cacheNegativeResponses ( ENABLED | DISABLED )] [-dropMultiQueryRequest ( ENABLED | DISABLED )] [-cacheECSResponses ( ENABLED | DISABLED )]


##Arguments

<b>dnsProfileName</b>
Name of the DNS profile

<b>dnsQueryLogging</b>
DNS query logging; if enabled, DNS query information such as DNS query id, DNS query flags , DNS domain name and DNS query type will be logged
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsAnswerSecLogging</b>
DNS answer section; if enabled, answer section in the response will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsExtendedLogging</b>
DNS extended logging; if enabled, authority and additional section in the response will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dnsErrorLogging</b>
DNS error logging; if enabled, whenever error is encountered in DNS module reason for the error will be logged.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cacheRecords</b>
Cache resource records in the DNS cache. Applies to resource records obtained through proxy configurations only. End resolver and forwarder configurations always cache records in the DNS cache, and you cannot disable this behavior. When you disable record caching, the appliance stops caching server responses. However, cached records are not flushed. The appliance does not serve requests from the cache until record caching is enabled again.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>cacheNegativeResponses</b>
Cache negative responses in the DNS cache. When disabled, the appliance stops caching negative responses except referral records. This applies to all configurations - proxy, end resolver, and forwarder. However, cached responses are not flushed. The appliance does not serve negative responses from the cache until this parameter is enabled again.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>dropMultiQueryRequest</b>
Drop the DNS requests containing multiple queries. When enabled, DNS requests containing multiple queries will be dropped. In case of proxy configuration by default the DNS request containing multiple queries is forwarded to the backend and in case of ADNS and Resolver configuration NOCODE error response will be sent to the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cacheECSResponses</b>
Cache DNS responses with EDNS Client Subnet(ECS) option in the DNS cache. When disabled, the appliance stops caching responses with ECS option. This is relevant to proxy configuration. Enabling/disabling support of ECS option when NetScaler is authoritative for a GSLB domain is supported using a knob in GSLB vserver. In all other modes, ECS option is ignored.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set dns profile &lt;profile name&gt; -caching ENABLED

##unset dns profile

Use this command to remove dns profile settings.Refer to the set dns profile command for meanings of the arguments.


##Synopsys

unset dns profile &lt;dnsProfileName> [-dnsQueryLogging] [-dnsAnswerSecLogging] [-dnsExtendedLogging] [-dnsErrorLogging] [-cacheRecords] [-cacheNegativeResponses] [-dropMultiQueryRequest] [-cacheECSResponses]


##rm dns profile

Removes the specified DNS profile from the Netscaler appliance


##Synopsys

rm dns profile &lt;dnsProfileName>


##Arguments

<b>dnsProfileName</b>
Name of the DNS profile to be removed.



##Example

rm dns profile testprofile

##show dns profile

Displays the properties of the specified DNS profile. If profile name is not specified then all conifgured DNS profiles are displayed


##Synopsys

show dns profile [&lt;dnsProfileName>]


##Arguments

<b>dnsProfileName</b>
Name of the DNS profile



##Outputs

<b>dnsQueryLogging</b>
DNS query logging; if enabled, DNS query information such as DNS query id, DNS query flags , DNS domain name and DNS query type will be logged

<b>dnsAnswerSecLogging</b>
DNS answer section; if enabled, answer section in the response will be logged.

<b>dnsExtendedLogging</b>
DNS extended logging; if enabled, authority and additional section in the response will be logged.

<b>dnsErrorLogging</b>
DNS error logging; if enabled, whenever error is encountered in DNS module reason for the error will be logged.

<b>cacheRecords</b>
Cache resource records in the DNS cache. Applies to resource records obtained through proxy configurations only. End resolver and forwarder configurations always cache records in the DNS cache, and you cannot disable this behavior. When you disable record caching, the appliance stops caching server responses. However, cached records are not flushed. The appliance does not serve requests from the cache until record caching is enabled again.

<b>cacheNegativeResponses</b>
Cache negative responses in the DNS cache. When disabled, the appliance stops caching negative responses except referral records. This applies to all configurations - proxy, end resolver, and forwarder. However, cached responses are not flushed. The appliance does not serve negative responses from the cache until this parameter is enabled again.

<b>dropMultiQueryRequest</b>
Drop the DNS requests containing multiple queries. When enabled, DNS requests containing multiple queries will be dropped. In case of proxy configuration by default the DNS request containing multiple queries is forwarded to the backend and in case of ADNS and Resolver configuration NOCODE error response will be sent to the client.

<b>cacheECSResponses</b>
Cache DNS responses with EDNS Client Subnet(ECS) option in the DNS cache. When disabled, the appliance stops caching responses with ECS option. This is relevant to proxy configuration. Enabling/disabling support of ECS option when NetScaler is authoritative for a GSLB domain is supported using a knob in GSLB vserver. In all other modes, ECS option is ignored.

<b>referenceCount</b>
Number of entities using this profile

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show dns profile [profile name]

