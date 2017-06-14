#cache contentGroup

The following operations can be performed on "cache contentGroup":


[add](#add-cache-contentgroup) | [rm](#rm-cache-contentgroup) | [set](#set-cache-contentgroup) | [unset](#unset-cache-contentgroup) | [show](#show-cache-contentgroup) | [expire](#expire-cache-contentgroup) | [flush](#flush-cache-contentgroup) | [stat](#stat-cache-contentgroup) | [save](#save-cache-contentgroup)

##add cache contentGroup

Creates a new content group for grouping cached objects on the basis of some unique property.


##Synopsys

add cache contentGroup &lt;name> [-weakPosRelExpiry &lt;secs> | -relExpiry &lt;secs> | -relExpiryMilliSec &lt;msecs> | -absExpiry &lt;HH:MM> ... | -absExpiryGMT &lt;HH:MM> ...] [-heurExpiryParam &lt;positive_integer>] [-weakNegRelExpiry &lt;secs>] [(-hitParams &lt;string> ...  [-ignoreParamValueCase ( YES | NO ) | -hitSelector &lt;string> | -invalSelector &lt;string>]  [-matchCookies ( YES | NO )])] [-invalParams &lt;string> ...  [-invalRestrictedToHost ( YES | NO )]] [-pollEveryTime ( YES | NO )] [-ignoreReloadReq ( YES | NO )] [-removeCookies ( YES | NO )] [-prefetch ( YES | NO )  [-prefetchPeriod &lt;secs> | -prefetchPeriodMilliSec &lt;msecs>]] [-prefetchMaxPending &lt;positive_integer>] [-flashCache ( YES | NO )] [-expireAtLastByte ( YES | NO )] [-insertVia ( YES | NO )] [-insertAge ( YES | NO )] [-insertETag ( YES | NO )] [-cacheControl &lt;string>] [-quickAbortSize &lt;KBytes>] [-minResSize &lt;KBytes>] [-maxResSize &lt;KBytes>] [-memLimit &lt;MBytes>] [-ignoreReqCachingHdrs ( YES | NO )] [-minHits &lt;integer>] [-alwaysEvalPolicies ( YES | NO )] [-persistHA ( YES | NO )] [-pinned ( YES | NO )] [-lazyDnsResolve ( YES | NO )] [-type &lt;type>]


##Arguments

<b>name</b>
Name for the content group.  Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the content group is created.

<b>weakPosRelExpiry</b>
Relative expiry time, in seconds, for expiring positive responses with response codes between 200 and 399. Cannot be used in combination with other Expiry attributes. Similar to -relExpiry but has lower precedence.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>heurExpiryParam</b>
Heuristic expiry time, in percent of the duration, since the object was last modified.
Default value: VAL_NOT_SET
Maximum value: 100

<b>relExpiry</b>
Relative expiry time, in seconds, after which to expire an object cached in this content group.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>relExpiryMilliSec</b>
Relative expiry time, in milliseconds, after which to expire an object cached in this content group.
Default value: VAL_NOT_SET
Maximum value: 86400000

<b>absExpiry</b>
Local time, up to 4 times a day, at which all objects in the content group must expire. 
CLI Users:
For example, to specify that the objects in the content group should expire by 11:00 PM, type the following command: add cache contentgroup &lt;contentgroup name&gt; -absexpiry 23:00 
To specify that the objects in the content group should expire at 10:00 AM, 3 PM, 6 PM, and 11:00 PM, type: add cache contentgroup &lt;contentgroup name&gt; -absexpiry 10:00 15:00 18:00 23:00

<b>absExpiryGMT</b>
Coordinated Universal Time (GMT), up to 4 times a day, when all objects in the content group must expire.

<b>weakNegRelExpiry</b>
Relative expiry time, in seconds, for expiring negative responses. This value is used only if the expiry time cannot be determined from any other source. It is applicable only to the following status codes: 307, 403, 404, and 410.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>hitParams</b>
Parameters to use for parameterized hit evaluation of an object. Up to 128 parameters can be specified. Mutually exclusive with the Hit Selector parameter.

<b>invalParams</b>
Parameters for parameterized invalidation of an object. You can specify up to 8 parameters. Mutually exclusive with invalSelector.

<b>ignoreParamValueCase</b>
Ignore case when comparing parameter values during parameterized hit evaluation. (Parameter value case is ignored by default during parameterized invalidation.)
Possible values: YES, NO
Default value: VAL_NOT_SET

<b>matchCookies</b>
Evaluate for parameters in the cookie header also.
Possible values: YES, NO
Default value: VAL_NOT_SET

<b>invalRestrictedToHost</b>
Take the host header into account during parameterized invalidation.
Possible values: YES, NO
Default value: VAL_NOT_SET

<b>pollEveryTime</b>
Always poll for the objects in this content group. That is, retrieve the objects from the origin server whenever they are requested.
Possible values: YES, NO
Default value: NO

<b>ignoreReloadReq</b>
Ignore any request to reload a cached object from the origin server.
To guard against Denial of Service attacks, set this parameter to YES. For RFC-compliant behavior, set it to NO.
Possible values: YES, NO
Default value: YES

<b>removeCookies</b>
Remove cookies from responses.
Possible values: YES, NO
Default value: YES

<b>prefetch</b>
Attempt to refresh objects that are about to go stale.
Possible values: YES, NO
Default value: YES

<b>prefetchPeriod</b>
Time period, in seconds before an object's calculated expiry time, during which to attempt prefetch.
Default value: VAL_NOT_SET
Maximum value: 4294967294

<b>prefetchPeriodMilliSec</b>
Time period, in milliseconds before an object's calculated expiry time, during which to attempt prefetch.
Default value: VAL_NOT_SET
Maximum value: 4294967290

<b>prefetchMaxPending</b>
Maximum number of outstanding prefetches that can be queued for the content group.
Default value: VAL_NOT_SET
Maximum value: 4294967294

<b>flashCache</b>
Perform flash cache. Mutually exclusive with Poll Every Time (PET) on the same content group.
Possible values: YES, NO
Default value: NO

<b>expireAtLastByte</b>
Force expiration of the content immediately after the response is downloaded (upon receipt of the last byte of the response body). Applicable only to positive responses.
Possible values: YES, NO
Default value: NO

<b>insertVia</b>
Insert a Via header into the response.
Possible values: YES, NO
Default value: YES

<b>insertAge</b>
Insert an Age header into the response. An Age header contains information about the age of the object, in seconds, as calculated by the integrated cache.
Possible values: YES, NO
Default value: YES

<b>insertETag</b>
Insert an ETag header in the response. With ETag header insertion, the integrated cache does not serve full responses on repeat requests.
Possible values: YES, NO
Default value: YES

<b>cacheControl</b>
Insert a Cache-Control header into the response.

<b>quickAbortSize</b>
If the size of an object that is being downloaded is less than or equal to the quick abort value, and a client aborts during the download, the cache stops downloading the response. If the object is larger than the quick abort size, the cache continues to download the response.
Default value: 4194303
Maximum value: 4194303

<b>minResSize</b>
Minimum size of a response that can be cached in this content group.
 Default minimum response size is 0.
Maximum value: 2097151

<b>maxResSize</b>
Maximum size of a response that can be cached in this content group.
Default value: 80
Maximum value: 2097151

<b>memLimit</b>
Maximum amount of memory that the cache can use. The effective limit is based on the available memory of the NetScaler appliance.
Default value: 65536

<b>ignoreReqCachingHdrs</b>
Ignore Cache-Control and Pragma headers in the incoming request.
Possible values: YES, NO
Default value: YES

<b>minHits</b>
Number of hits that qualifies a response for storage in this content group.
Default value: 0

<b>alwaysEvalPolicies</b>
Force policy evaluation for each response arriving from the origin server. Cannot be set to YES if the Prefetch parameter is also set to YES.
Possible values: YES, NO
Default value: NO

<b>persistHA</b>
Setting persistHA to YES causes IC to save objects in contentgroup to Secondary node in HA deployment.
Possible values: YES, NO
Default value: NO

<b>pinned</b>
Do not flush objects from this content group under memory pressure.
Possible values: YES, NO
Default value: NO

<b>lazyDnsResolve</b>
Perform DNS resolution for responses only if the destination IP address in the request does not match the destination IP address of the cached response.
Possible values: YES, NO
Default value: YES

<b>hitSelector</b>
Selector for evaluating whether an object gets stored in a particular content group. A selector is an abstraction for a collection of PIXL expressions.

<b>invalSelector</b>
Selector for invalidating objects in the content group. A selector is an abstraction for a collection of PIXL expressions.

<b>type</b>
The type of the content group.
Possible values: HTTP, MYSQL, MSSQL
Default value: NSSVC_HTTP



##rm cache contentGroup

Removes the specified content group. Before removing, make sure that no cache policy has its storeInGroup attribute set to this group, otherwise the group cannot be removed.


##Synopsys

rm cache contentGroup &lt;name>


##Arguments

<b>name</b>
Name of the content group to be removed.



##set cache contentGroup

Modifies the specified attributes of the content group.


##Synopsys

set cache contentGroup &lt;name> [-weakPosRelExpiry &lt;secs> | -relExpiry &lt;secs> | -relExpiryMilliSec &lt;msecs> | -absExpiry &lt;HH:MM> ... | -absExpiryGMT &lt;HH:MM> ...] [-heurExpiryParam &lt;positive_integer>] [-weakNegRelExpiry &lt;secs>] [-hitParams &lt;string> ... | -hitSelector &lt;string> | -invalSelector &lt;string>] [-invalParams &lt;string> ...] [-ignoreParamValueCase ( YES | NO )] [-matchCookies ( YES | NO )] [-invalRestrictedToHost ( YES | NO )] [-pollEveryTime ( YES | NO )] [-ignoreReloadReq ( YES | NO )] [-removeCookies ( YES | NO )] [-prefetch ( YES | NO )] [-prefetchPeriod &lt;secs> | -prefetchPeriodMilliSec &lt;msecs>] [-prefetchMaxPending &lt;positive_integer>] [-flashCache ( YES | NO )] [-expireAtLastByte ( YES | NO )] [-insertVia ( YES | NO )] [-insertAge ( YES | NO )] [-insertETag ( YES | NO )] [-cacheControl &lt;string>] [-quickAbortSize &lt;KBytes>] [-minResSize &lt;KBytes>] [-maxResSize &lt;KBytes>] [-memLimit &lt;MBytes>] [-ignoreReqCachingHdrs ( YES | NO )] [-minHits &lt;integer>] [-alwaysEvalPolicies ( YES | NO )] [-persistHA ( YES | NO )] [-pinned ( YES | NO )] [-lazyDnsResolve ( YES | NO )]


##Arguments

<b>name</b>
Name of the content group to be modified.

<b>weakPosRelExpiry</b>
Relative expiry time, in seconds, for expiring positive responses with response codes between 200 and 399. Cannot be used in combination with other Expiry attributes. Similar to -relExpiry but has lower precedence.
Maximum value: 31536000

<b>heurExpiryParam</b>
Heuristic expiry time, in percent of the duration, since the object was last modified.
Maximum value: 100

<b>relExpiry</b>
Relative expiry time, in seconds, after which to expire an object cached in this content group.
Default value: VAL_NOT_SET
Maximum value: 31536000

<b>relExpiryMilliSec</b>
Relative expiry time, in milliseconds, after which to expire an object cached in this content group.
Default value: VAL_NOT_SET
Maximum value: 86400000

<b>absExpiry</b>
Local time, up to 4 times a day, at which all objects in the content group must expire. 
CLI Users:
For example, to specify that the objects in the content group should expire by 11:00 PM, type the following command: add cache contentgroup &lt;contentgroup name&gt; -absexpiry 23:00 
To specify that the objects in the content group should expire at 10:00 AM, 3 PM, 6 PM, and 11:00 PM, type: add cache contentgroup &lt;contentgroup name&gt; -absexpiry 10:00 15:00 18:00 23:00

<b>absExpiryGMT</b>
Coordinated Universal Time (GMT), up to 4 times a day, when all objects in the content group must expire.

<b>weakNegRelExpiry</b>
Relative expiry time, in seconds, for expiring negative responses. This value is used only if the expiry time cannot be determined from any other source. It is applicable only to the following status codes: 307, 403, 404, and 410.
Maximum value: 31536000

<b>hitParams</b>
Parameters to use for parameterized hit evaluation of an object. Up to 128 parameters can be specified. Mutually exclusive with the Hit Selector parameter.

<b>invalParams</b>
Parameters for parameterized invalidation of an object. You can specify up to 8 parameters. Mutually exclusive with invalSelector.

<b>ignoreParamValueCase</b>
Ignore case when comparing parameter values during parameterized hit evaluation. (Parameter value case is ignored by default during parameterized invalidation.)
Possible values: YES, NO

<b>matchCookies</b>
Evaluate for parameters in the cookie header also.
Possible values: YES, NO

<b>invalRestrictedToHost</b>
Take the host header into account during parameterized invalidation.
Possible values: YES, NO

<b>pollEveryTime</b>
Always poll for the objects in this content group. That is, retrieve the objects from the origin server whenever they are requested.
Possible values: YES, NO
Default value: NO

<b>ignoreReloadReq</b>
Ignore any request to reload a cached object from the origin server.
To guard against Denial of Service attacks, set this parameter to YES. For RFC-compliant behavior, set it to NO.
Possible values: YES, NO
Default value: YES

<b>removeCookies</b>
Remove cookies from responses.
Possible values: YES, NO
Default value: YES

<b>prefetch</b>
Attempt to refresh objects that are about to go stale.
Possible values: YES, NO
Default value: YES

<b>prefetchPeriod</b>
Time period, in seconds before an object's calculated expiry time, during which to attempt prefetch.
Default value: VAL_NOT_SET
Maximum value: 4294967294

<b>prefetchPeriodMilliSec</b>
Time period, in milliseconds before an object's calculated expiry time, during which to attempt prefetch.
Default value: VAL_NOT_SET
Maximum value: 4294967290

<b>prefetchMaxPending</b>
Maximum number of outstanding prefetches that can be queued for the content group.
Maximum value: 4294967294

<b>flashCache</b>
Perform flash cache. Mutually exclusive with Poll Every Time (PET) on the same content group.
Possible values: YES, NO
Default value: NO

<b>expireAtLastByte</b>
Force expiration of the content immediately after the response is downloaded (upon receipt of the last byte of the response body). Applicable only to positive responses.
Possible values: YES, NO
Default value: NO

<b>insertVia</b>
Insert a Via header into the response.
Possible values: YES, NO
Default value: YES

<b>insertAge</b>
Insert an Age header into the response. An Age header contains information about the age of the object, in seconds, as calculated by the integrated cache.
Possible values: YES, NO
Default value: YES

<b>insertETag</b>
Insert an ETag header in the response. With ETag header insertion, the integrated cache does not serve full responses on repeat requests.
Possible values: YES, NO
Default value: YES

<b>cacheControl</b>
Insert a Cache-Control header into the response.

<b>quickAbortSize</b>
If the size of an object that is being downloaded is less than or equal to the quick abort value, and a client aborts during the download, the cache stops downloading the response. If the object is larger than the quick abort size, the cache continues to download the response.
Maximum value: 4194303

<b>minResSize</b>
Minimum size of a response that can be cached in this content group.
 Default minimum response size is 0.
Maximum value: 2097151

<b>maxResSize</b>
Maximum size of a response that can be cached in this content group.
Default value: 80
Maximum value: 2097151

<b>memLimit</b>
Maximum amount of memory that the cache can use. The effective limit is based on the available memory of the NetScaler appliance.
Default value: 65536

<b>ignoreReqCachingHdrs</b>
Ignore Cache-Control and Pragma headers in the incoming request.
Possible values: YES, NO
Default value: YES

<b>minHits</b>
Number of hits that qualifies a response for storage in this content group.

<b>alwaysEvalPolicies</b>
Force policy evaluation for each response arriving from the origin server. Cannot be set to YES if the Prefetch parameter is also set to YES.
Possible values: YES, NO
Default value: NO

<b>persistHA</b>
The option for IC objects to save objects to Secondary in a HA deployment. Set YES for IC to take this state.
Possible values: YES, NO
Default value: NO

<b>pinned</b>
The option for IC from flushing objects from this contentgroup under memory pressure. Set YES for IC to take this state.
Possible values: YES, NO
Default value: NO

<b>lazyDnsResolve</b>
Perform DNS resolution for responses only if the destination IP address in the request does not match the destination IP address of the cached response.
Possible values: YES, NO
Default value: YES

<b>hitSelector</b>
Selector for evaluating whether an object gets stored in a particular content group. A selector is an abstraction for a collection of PIXL expressions.

<b>invalSelector</b>
Selector for invalidating objects in the content group. A selector is an abstraction for a collection of PIXL expressions.



##unset cache contentGroup

Use this command to remove cache contentGroup settings.Refer to the set cache contentGroup command for meanings of the arguments.


##Synopsys

unset cache contentGroup &lt;name> [-weakPosRelExpiry] [-heurExpiryParam] [-relExpiry] [-relExpiryMilliSec] [-absExpiry] [-absExpiryGMT] [-weakNegRelExpiry] [-hitParams] [-invalParams] [-ignoreParamValueCase] [-matchCookies] [-invalRestrictedToHost] [-pollEveryTime] [-ignoreReloadReq] [-removeCookies] [-prefetch] [-prefetchPeriod] [-prefetchPeriodMilliSec] [-prefetchMaxPending] [-flashCache] [-expireAtLastByte] [-insertVia] [-insertAge] [-insertETag] [-cacheControl] [-quickAbortSize] [-minResSize] [-maxResSize] [-memLimit] [-ignoreReqCachingHdrs] [-minHits] [-alwaysEvalPolicies] [-persistHA] [-pinned] [-lazyDnsResolve] [-hitSelector] [-invalSelector]


##show cache contentGroup

Displays information about all content groups, or about the specified content group.


##Synopsys

show cache contentGroup [&lt;name>]


##Arguments

<b>name</b>
Name of the content group about which to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>flags</b>
Flags.

<b>type</b>
The type of the content group.

<b>relExpiry</b>
The relative expiry time in seconds.

<b>relExpiryMilliSec</b>
Relative expiry time, in milliseconds, after which to expire an object cached in this content group.

<b>absExpiry</b>
Local time, up to 4 times a day, at which all objects in the content group must expire. 
CLI Users:
For example, to specify that the objects in the content group should expire by 11:00 PM, type the following command: add cache contentgroup &lt;contentgroup name> -absexpiry 23:00 
To specify that the objects in the content group should expire at 10:00 AM, 3 PM, 6 PM, and 11:00 PM, type: add cache contentgroup &lt;contentgroup name> -absexpiry 10:00 15:00 18:00 23:00

<b>absExpiryGMT</b>
Coordinated Universal Time (GMT), up to 4 times a day, when all objects in the content group must expire.

<b>heurExpiryParam</b>
Heuristic expiry time, in percent of the duration, since the object was last modified.

<b>weakPosRelExpiry</b>
Relative expiry time, in seconds, for expiring positive responses with response codes between 200 and 399. Cannot be used in combination with other Expiry attributes. Similar to -relExpiry but has lower precedence.

<b>weakNegRelExpiry</b>
Relative expiry time, in seconds, for expiring negative responses. This value is used only if the expiry time cannot be determined from any other source. It is applicable only to the following status codes: 307, 403, 404, and 410.

<b>hitParams</b>
Parameters to use for parameterized hit evaluation of an object. Up to 128 parameters can be specified. Mutually exclusive with the Hit Selector parameter.

<b>invalParams</b>
Parameters for parameterized invalidation of an object. You can specify up to 8 parameters. Mutually exclusive with invalSelector.

<b>ignoreParamValueCase</b>
Ignore case when comparing parameter values during parameterized hit evaluation. (Parameter value case is ignored by default during parameterized invalidation.)

<b>matchCookies</b>
Evaluate for parameters in the cookie header also.

<b>invalRestrictedToHost</b>
Take the host header into account during parameterized invalidation.

<b>pollEveryTime</b>
Always poll for the objects in this content group. That is, retrieve the objects from the origin server whenever they are requested.

<b>ignoreReloadReq</b>
Ignore any request to reload a cached object from the origin server.
To guard against Denial of Service attacks, set this parameter to YES. For RFC-compliant behavior, set it to NO.

<b>removeCookies</b>
Remove cookies from responses.

<b>prefetch</b>
Attempt to refresh objects that are about to go stale.

<b>prefetchPeriod</b>
Time period, in seconds before an object's calculated expiry time, during which to attempt prefetch.

<b>prefetchPeriodMilliSec</b>
Time period, in milliseconds before an object's calculated expiry time, during which to attempt prefetch.

<b>prefetchCur</b>
Current outstanding prefetches.

<b>prefetchMaxPending</b>
Maximum number of outstanding prefetches that can be queued for the content group.

<b>flashCache</b>
Perform flash cache. Mutually exclusive with Poll Every Time (PET) on the same content group.

<b>expireAtLastByte</b>
Force expiration of the content immediately after the response is downloaded (upon receipt of the last byte of the response body). Applicable only to positive responses.

<b>insertVia</b>
Insert a Via header into the response.

<b>insertAge</b>
Insert an Age header into the response. An Age header contains information about the age of the object, in seconds, as calculated by the integrated cache.

<b>insertETag</b>
Insert an ETag header in the response. With ETag header insertion, the integrated cache does not serve full responses on repeat requests.

<b>cacheControl</b>
Insert a Cache-Control header into the response.

<b>quickAbortSize</b>
If the size of an object that is being downloaded is less than or equal to the quick abort value, and a client aborts during the download, the cache stops downloading the response. If the object is larger than the quick abort size, the cache continues to download the response.

<b>minResSize</b>
Minimum size of a response that can be cached in this content group.
 Default minimum response size is 0.

<b>maxResSize</b>
Maximum size of a response that can be cached in this content group.

<b>memUsage</b>
Current memory usage.

<b>memDUsage</b>
Current disk memory usage.

<b>diskLimit</b>
Maximum amount of disk that the cache can use. The effective limit is based on the available memory of the NetScaler appliance.

<b>memLimit</b>
Maximum amount of memory that the cache can use. The effective limit is based on the available memory of the NetScaler appliance.

<b>ignoreReqCachingHdrs</b>
Ignore Cache-Control and Pragma headers in the incoming request.

<b>cacheNon304Hits</b>
Cache non 304 hits.

<b>cache304Hits</b>
Cache 304 hits.

<b>cacheCells</b>
Number of cells.

<b>cacheGroupIncarnation</b>
Cache group incarnation.

<b>minHits</b>
Number of hits that qualifies a response for storage in this content group.

<b>alwaysEvalPolicies</b>
Force policy evaluation for each response arriving from the origin server. Cannot be set to YES if the Prefetch parameter is also set to YES.

<b>persist</b>
Setting persist to YES causes IC to save objects in contentgroup to disk.

<b>persistHA</b>
Setting persistHA to YES causes IC to save objects in contentgroup to Secondary node in HA deployment.

<b>pinned</b>
Do not flush objects from this content group under memory pressure.

<b>lazyDnsResolve</b>
Perform DNS resolution for responses only if the destination IP address in the request does not match the destination IP address of the cached response.

<b>hitSelector</b>
Selector for evaluating whether an object gets stored in a particular content group. A selector is an abstraction for a collection of PIXL expressions.

<b>invalSelector</b>
Selector for invalidating objects in the content group. A selector is an abstraction for a collection of PIXL expressions.

<b>policyName</b>
Active cache policies refering to this group.

<b>cacheNumInvalPolicy</b>
Number of active Invalidation policies refering to this group.

<b>markerCells</b>
Numbers of marker cells in this group.

<b>builtin</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##expire cache contentGroup

Forces expiration of all the objects in the specified content group. The next request for any object in the group is sent to the origin server.


##Synopsys

expire cache contentGroup &lt;name>


##Arguments

<b>name</b>
Name of the content group whose objects are to be expired.



##flush cache contentGroup

Flush the objects in the specified content group.


##Synopsys

flush cache contentGroup &lt;name> [-query &lt;string> | -selectorValue &lt;string>] [-host &lt;string>]


##Arguments

<b>name</b>
Name of the content group from which to flush objects, or "all" to flush all content groups.

<b>query</b>
Query string specifying individual objects to flush from this group by using parameterized invalidation. If this parameter is not set, all objects are flushed from the group.

<b>host</b>
Flush only objects that belong to the specified host. Do not use except with parameterized invalidation. Also, the Invalidation Restricted to Host parameter for the group must be set to YES.

<b>selectorValue</b>
Value of the selector to be used for flushing objects from the content group. Requires that an invalidation selector be configured for the content group.



##stat cache contentGroup

Displays a summary of cache group statistics.


##Synopsys

stat cache contentGroup [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the cache contentgroup for which to display statistics. If you do not set this parameter, statistics are shown for all cache contentgroups.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>non304 Hits for Content group (non304hit)</b>
Non304 hits for ContentGroup

<b>304 Hits for Content group (304hit)</b>
304 hits for ContentGroup

<b>Number of objects in contentgroup (cell)</b>
Number of objects in contentgroup

<b>Number of marker objects in contentgroup (Mrkcell)</b>
Number of marker objects in contentgroup

<b>Number of times contentgroup is flushed (flushed)</b>
Number of times contentgroup is flushed

<b>current memory usage (CurMem)</b>
current memory usage

<b>maximum memory usage limit (MaxMem)</b>
maximum memory usage limit



##Example

stat cache contentgroup

##Related Commands

<ul><li><a href="../../..//">stat cache</a></li><li><a href="../../../stat-cache-p/stat-cache-p">stat cache policy</a></li><li><a href="../../../html#stat-cache-policy/html#stat-cache-policy">stat cache policylabel</a></li></ul>



##save cache contentGroup

Save the objects in the specified content group.


##Synopsys

save cache contentGroup &lt;name> [-tosecondary ( YES | NO )]


##Arguments

<b>name</b>
The name of the content group whose objects are to be save.

<b>tosecondary</b>
content group whose objects are to be sent to secondary.
Possible values: YES, NO
Default value: NO



