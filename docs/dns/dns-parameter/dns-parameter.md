#dns parameter

The following operations can be performed on "dns parameter":


[set](#set-dns-parameter) | [unset](#unset-dns-parameter) | [show](#show-dns-parameter)

##set dns parameter

Modifies global DNS parameters on the NetScaler appliance.


##Synopsys

set dns parameter [-retries &lt;positive_integer>] [-minTTL &lt;secs>] [-maxTTL &lt;secs>] [-nameLookupPriority ( WINS | DNS )] [-recursion ( ENABLED | DISABLED )] [-resolutionOrder &lt;resolutionOrder>] [-dnssec ( ENABLED | DISABLED )] [-maxPipeline &lt;positive_integer>] [-dnsRootReferral ( ENABLED | DISABLED )] [-dns64Timeout &lt;msecs>] [-ecsMaxSubnets &lt;positive_integer>] [-maxnegcacheTTL &lt;secs>] [-cacheHitBypass ( ENABLED | DISABLED )] [-maxCacheSize &lt;MBytes>] [-maxNegativeCacheSize &lt;MBytes>] [-cacheNoExpire ( ENABLED | DISABLED )] [-splitPktQueryProcessing ( ALLOW | DROP )] [-cacheECSZeroPrefix ( ENABLED | DISABLED )]


##Arguments

<b>retries</b>
Maximum number of retry attempts when no response is received for a query sent to a name server. Applies to end resolver and forwarder configurations.
Default value: 5
Minimum value: 1
Maximum value: 5

<b>minTTL</b>
Minimum permissible time to live (TTL) for all records cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is lower than the value configured for minTTL, the TTL of the record is set to the value of minTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.
Maximum value: 604800

<b>maxTTL</b>
Maximum time to live (TTL) for all records cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is higher than the value configured for maxTTL, the TTL of the record is set to the value of maxTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.
Default value: 604800
Minimum value: 1
Maximum value: 604800

<b>nameLookupPriority</b>
Type of lookup (DNS or WINS) to attempt first. If the first-priority lookup fails, the second-priority lookup is attempted. Used only by the SSL VPN feature.
Possible values: WINS, DNS
Default value: WINS

<b>recursion</b>
Function as an end resolver and recursively resolve queries for domains that are not hosted on the NetScaler appliance. Also resolve queries recursively when the external name servers configured on the appliance (for a forwarder configuration) are unavailable. When external name servers are unavailable, the appliance queries a root server and resolves the request recursively, as it does for an end resolver configuration.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>resolutionOrder</b>
Type of DNS queries (A, AAAA, or both) to generate during the routine functioning of certain NetScaler features, such as SSL VPN, cache redirection, and the integrated cache. The queries are sent to the external name servers that are configured for the forwarder function. If you specify both query types, you can also specify the order. Available settings function as follows:
* OnlyAQuery. Send queries for IPv4 address records (A records) only. 
* OnlyAAAAQuery. Send queries for IPv6 address records (AAAA records) instead of queries for IPv4 address records (A records).
* AThenAAAAQuery. Send a query for an A record, and then send a query for an AAAA record if the query for the A record results in a NODATA response from the name server.
* AAAAThenAQuery. Send a query for an AAAA record, and then send a query for an A record if the query for the AAAA record results in a NODATA response from the name server.
Possible values: OnlyAQuery, OnlyAAAAQuery, AThenAAAAQuery, AAAAThenAQuery
Default value: OnlyAQuery

<b>dnssec</b>
Enable or disable the Domain Name System Security Extensions (DNSSEC) feature on the appliance. Note: Even when the DNSSEC feature is enabled, forwarder configurations (used by internal NetScaler features such as SSL VPN and Cache Redirection for name resolution) do not support the DNSSEC OK (DO) bit in the EDNS0 OPT header.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxPipeline</b>
Maximum number of concurrent DNS requests to allow on a single client connection, which is identified by the &lt;clientip:port&gt;-&lt;vserver ip:port&gt; tuple. A value of 0 (zero) applies no limit to the number of concurrent DNS requests allowed on a single client connection.
Default value: NSNATPCB_MAXPIPELINE
Minimum value: 0

<b>dnsRootReferral</b>
Send a root referral if a client queries a domain name that is unrelated to the domains configured/cached on the NetScaler appliance. If the setting is disabled, the appliance sends a blank response instead of a root referral. Applicable to domains for which the appliance is authoritative. Disable the parameter when the appliance is under attack from a client that is sending a flood of queries for unrelated domains.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>dns64Timeout</b>
While doing DNS64 resolution, this parameter specifies the time to wait before sending an A query if no response is received from backend DNS server for AAAA query.
Default value: -1 
Maximum value: 10000

<b>ecsMaxSubnets</b>
Maximum number of subnets that can be cached corresponding to a single domain. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Caching of such responses can be disabled using DNS profile settings. A value of zero indicates that the number of subnets cached is limited only by existing memory constraints. The default value is zero.
Default value: 0
Minimum value: 0
Maximum value: 1280

<b>maxnegcacheTTL</b>
Maximum time to live (TTL) for all negative records ( NXDONAIN and NODATA ) cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is higher than the value configured for maxnegcacheTTL, the TTL of the record is set to the value of maxnegcacheTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.
Default value: 604800
Minimum value: 1
Maximum value: 604800

<b>cacheHitBypass</b>
This parameter is applicable only in proxy mode and if this parameter is enabled  we will forward all the client requests to the backend DNS server and the response served will be cached on netscaler
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxCacheSize</b>
Maximum memory, in megabytes, that can be used for dns caching per Packet Engine.

<b>maxNegativeCacheSize</b>
Maximum memory, in megabytes, that can be used for caching of negative DNS responses per packet engine.

<b>cacheNoExpire</b>
If this flag is set to YES, the existing entries in cache do not age out. On reaching the max limit the cache records are frozen
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>splitPktQueryProcessing</b>
Processing requests split across multiple packets
Possible values: ALLOW, DROP
Default value: ALLOW

<b>cacheECSZeroPrefix</b>
Cache ECS responses with a Scope Prefix length of zero. Such a cached response will be used for all queries with this domain name and any subnet. When disabled, ECS responses with Scope Prefix length of zero will be cached, but not tied to any subnet. This option has no effect if caching of ECS responses is disabled in the corresponding DNS profile.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##unset dns parameter

Use this command to remove dns parameter settings.Refer to the set dns parameter command for meanings of the arguments.


##Synopsys

unset dns parameter [-retries] [-minTTL] [-maxTTL] [-nameLookupPriority] [-recursion] [-resolutionOrder] [-dnssec] [-maxPipeline] [-dnsRootReferral] [-dns64Timeout] [-ecsMaxSubnets] [-maxnegcacheTTL] [-cacheHitBypass] [-maxCacheSize] [-maxNegativeCacheSize] [-cacheNoExpire] [-splitPktQueryProcessing] [-cacheECSZeroPrefix]


##show dns parameter

Displays the global DNS parameters.


##Synopsys

show dns parameter


##Outputs

<b>retries</b>
Maximum number of retry attempts when no response is received for a query sent to a name server. Applies to end resolver and forwarder configurations.

<b>minTTL</b>
Minimum permissible time to live (TTL) for all records cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is lower than the value configured for minTTL, the TTL of the record is set to the value of minTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.

<b>maxTTL</b>
Maximum time to live (TTL) for all records cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is higher than the value configured for maxTTL, the TTL of the record is set to the value of maxTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.

<b>nameLookupPriority</b>
Type of lookup (DNS or WINS) to attempt first. If the first-priority lookup fails, the second-priority lookup is attempted. Used only by the SSL VPN feature.

<b>cacheRecords</b>
Cache resource records in the DNS cache. Applies to resource records obtained through proxy configurations only. End resolver and forwarder configurations always cache records in the DNS cache, and you cannot disable this behavior. When you disable record caching, the appliance stops caching server responses. However, cached records are not flushed. The appliance does not serve requests from the cache until record caching is enabled again.

<b>recursion</b>
Function as an end resolver and recursively resolve queries for domains that are not hosted on the NetScaler appliance. Also resolve queries recursively when the external name servers configured on the appliance (for a forwarder configuration) are unavailable. When external name servers are unavailable, the appliance queries a root server and resolves the request recursively, as it does for an end resolver configuration.

<b>resolutionOrder</b>
Type of DNS queries (A, AAAA, or both) to generate during the routine functioning of certain NetScaler features, such as SSL VPN, cache redirection, and the integrated cache. The queries are sent to the external name servers that are configured for the forwarder function. If you specify both query types, you can also specify the order. Available settings function as follows:
* OnlyAQuery. Send queries for IPv4 address records (A records) only. 
* OnlyAAAAQuery. Send queries for IPv6 address records (AAAA records) instead of queries for IPv4 address records (A records).
* AThenAAAAQuery. Send a query for an A record, and then send a query for an AAAA record if the query for the A record results in a NODATA response from the name server.
* AAAAThenAQuery. Send a query for an AAAA record, and then send a query for an A record if the query for the AAAA record results in a NODATA response from the name server.

<b>dnssec</b>
Enable or disable the Domain Name System Security Extensions (DNSSEC) feature on the appliance. Note: Even when the DNSSEC feature is enabled, forwarder configurations (used by internal NetScaler features such as SSL VPN and Cache Redirection for name resolution) do not support the DNSSEC OK (DO) bit in the EDNS0 OPT header.

<b>maxPipeline</b>
Maximum value of the concurrent DNS pipeline. A setting of zero makes the pipeline infinite

<b>dnsRootReferral</b>
Send a root referral if a client queries a domain name that is unrelated to the domains configured/cached on the NetScaler appliance. If the setting is disabled, the appliance sends a blank response instead of a root referral. Applicable to domains for which the appliance is authoritative. Disable the parameter when the appliance is under attack from a client that is sending a flood of queries for unrelated domains.

<b>dns64Timeout</b>
While doing DNS64 resolution, this parameter specifies the time to wait before sending an A query if no response is received from backend DNS server for AAAA query.

<b>ecsMaxSubnets</b>
Maximum number of subnets that can be cached corresponding to a single domain. Subnet caching will occur for responses with EDNS Client Subnet (ECS) option. Caching of such responses can be disabled using DNS profile settings. A value of zero indicates that the number of subnets cached is limited only by existing memory constraints. The default value is zero.

<b>maxnegcacheTTL</b>
Maximum time to live (TTL) for all negative records ( NXDONAIN and NODATA ) cached in the DNS cache by DNS proxy, end resolver, and forwarder configurations. If the TTL of a record that is to be cached is higher than the value configured for maxnegcacheTTL, the TTL of the record is set to the value of maxnegcacheTTL before caching. When you modify this setting, the new value is applied only to those records that are cached after the modification. The TTL values of existing records are not changed.

<b>cacheHitBypass</b>
This parameter is applicable only in proxy mode and if this parameter is enabled  we will forward all the client requests to the backend DNS server and the response served will be cached on netscaler

<b>maxCacheSize</b>
Maximum memory, in megabytes, that can be used for dns caching per Packet Engine.

<b>maxNegativeCacheSize</b>
Maximum memory, in megabytes, that can be used for caching of negative DNS responses per packet engine.

<b>cacheNoExpire</b>
If this flag is set to YES, the existing entries in cache do not age out. On reaching the max limit the cache records are frozen

<b>splitPktQueryProcessing</b>
Processing requests split across multiple packets

<b>cacheECSZeroPrefix</b>
Cache ECS responses with a Scope Prefix length of zero. Such a cached response will be used for all queries with this domain name and any subnet. When disabled, ECS responses with Scope Prefix length of zero will be cached, but not tied to any subnet. This option has no effect if caching of ECS responses is disabled in the corresponding DNS profile.



