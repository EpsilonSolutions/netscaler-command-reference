#cache parameter

The following operations can be performed on "cache parameter":


[set](#set-cache-parameter) | [unset](#unset-cache-parameter) | [show](#show-cache-parameter)

##set cache parameter

Modifies the global configuration of the integrated cache. You can modify the settings of various parameters.


##Synopsys

set cache parameter [-memLimit &lt;MBytes>] [-via &lt;string>] [-verifyUsing &lt;verifyUsing>] [-maxPostLen &lt;positive_integer>] [-prefetchMaxPending &lt;positive_integer>] [-enableBypass ( YES | NO )] [-undefAction ( NOCACHE | RESET )] [-enableHaObjPersist ( YES | NO )]


##Arguments

<b>memLimit</b>
Amount of memory available for storing the cache objects. In practice, the amount of memory available for caching can be less than half the total memory of the NetScaler appliance.

<b>via</b>
String to include in the Via header. A Via header is inserted into all responses served from a content group if its Insert Via flag is set.

<b>verifyUsing</b>
Criteria for deciding whether a cached object can be served for an incoming HTTP request. Available settings function as follows:
HOSTNAME - The URL, host name, and host port values in the incoming HTTP request header must match the cache policy. The IP address and the TCP port of the destination host are not evaluated. Do not use the HOSTNAME setting unless you are certain that no rogue client can access a rogue server through the cache. 
HOSTNAME_AND_IP - The URL, host name, host port in the incoming HTTP request header, and the IP address and TCP port of
the destination server, must match the cache policy.
DNS - The URL, host name and host port in the incoming HTTP request, and the TCP port must match the cache policy. The host name is used for DNS lookup of the destination server's IP address, and is compared with the set of addresses returned by the DNS lookup.
Possible values: HOSTNAME, HOSTNAME_AND_IP, DNS

<b>maxPostLen</b>
Maximum number of POST body bytes to consider when evaluating parameters for a content group for which you have configured hit parameters and invalidation parameters.
Default value: 4096
Maximum value: 131072

<b>prefetchMaxPending</b>
Maximum number of outstanding prefetches in the Integrated Cache.

<b>enableBypass</b>
Evaluate the request-time policies before attempting hit selection. If set to NO, an incoming request for which a matching object is found in cache storage results in a response regardless of the policy configuration.
If the request matches a policy with a NOCACHE action, the request bypasses all cache processing. 
This parameter does not affect processing of requests that match any invalidation policy.
Possible values: YES, NO

<b>undefAction</b>
Action to take when a policy cannot be evaluated.
Possible values: NOCACHE, RESET

<b>enableHaObjPersist</b>
The HA object persisting parameter. When this value is set to YES, cache objects can be synced to Secondary in a HA deployment.  If set to NO, objects will never be synced to Secondary node.
Possible values: YES, NO
Default value: NO



##unset cache parameter

Use this command to remove cache parameter settings.Refer to the set cache parameter command for meanings of the arguments.


##Synopsys

unset cache parameter [-memLimit] [-via] [-verifyUsing] [-maxPostLen] [-prefetchMaxPending] [-enableBypass] [-undefAction] [-enableHaObjPersist]


##show cache parameter

Displays the global configuration of the Integrated Cache.


##Synopsys

show cache parameter


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>diskLimit</b>
The disk limit for the Integrated Cache.

<b>maxDiskLimit</b>
The maximum value of the memory limit for the Integrated Cache.

<b>memLimit</b>
The memory limit for the Integrated Cache.

<b>memLimitActive</b>
Active value of the memory limit for the Integrated Cache.

<b>maxMemLimit</b>
The maximum value of the memory limit for the Integrated Cache.

<b>via</b>
The string that is inserted in the "Via" header.

<b>verifyUsing</b>
The criteria for deciding whether a cached object can be served for an incoming HTTP request.

<b>maxPostLen</b>
The maximum POST body size that the IC can accumulate.

<b>prefetchCur</b>
Number of current outstanding prefetches in the IC.

<b>prefetchMaxPending</b>
The maximum number of outstanding prefetches on the content group.

<b>enableBypass</b>
When this value is set to NO, an incoming request will serve a hit if a matching object is found in cache storage, regardless of the cacheability policy configuration. If set to YES, the bound request cacheability policies are evaluated before attempting any hit selection in the cache storage. If the request matches a policy with a NOCACHE action, the request will bypass all cache processing. This flag does not affect processing of requests that match any invalidation policy.

<b>undefAction</b>
Action to take when a policy cannot be evaluated.

<b>enableHaObjPersist</b>
The HA object persisting parameter. When this value is set to YES, cache objects can be synced to Secondary in a HA deployment.  If set to NO, objects will never be syned to Secondary node.



