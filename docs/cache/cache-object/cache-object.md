#cache object

The following operations can be performed on "cache object":


[show](#show-cache-object) | [expire](#expire-cache-object) | [flush](#flush-cache-object) | [save](#save-cache-object)

##show cache object

Displays a list of all cached objects. The list displays the unique locator ID of each cached object along with the content group in which it was cached, and other details. To view more details of a specific cached object, use the -locator parameter along with this command.


##Synopsys

show cache object [(-url &lt;URL>  (-host &lt;string>  [-port &lt;port>]  [-groupName &lt;string>]  [-httpMethod ( GET | POST )])) | -locator &lt;positive_integer> | -httpStatus &lt;positive_integer> | -group &lt;string> | -ignoreMarkerObjects ( ON | OFF ) | -includeNotReadyObjects ( ON | OFF )]


##Arguments

<b>url</b>
URL of the particular object whose details is required. Parameter "host" must be specified along with the URL.

<b>locator</b>
ID of the cached object.
Minimum value: 0

<b>httpStatus</b>
HTTP status of the object.
Minimum value: 0

<b>host</b>
Host name of the object. Parameter "url" must be specified.

<b>port</b>
Host port of the object. You must also set the Host parameter.
Default value: 80
Minimum value: 1

<b>groupName</b>
Name of the content group to which the object belongs. It will display only the objects belonging to the specified content group. You must also set the Host parameter.

<b>httpMethod</b>
HTTP request method that caused the object to be stored.
Possible values: GET, POST
Default value: GET

<b>group</b>
Name of the content group whose objects should be listed.

<b>ignoreMarkerObjects</b>
Ignore marker objects. Marker objects are created when a response exceeds the maximum or minimum response size for the content group or has not yet received the minimum number of hits for the content group.
Possible values: ON, OFF

<b>includeNotReadyObjects</b>
Include responses that have not yet reached a minimum number of hits before being cached.
Possible values: ON, OFF



##Outputs

<b>cacheResSize</b>
Cache response size of the object.

<b>cacheResHdrSize</b>
Cache response header size of the object.

<b>cacheETag</b>
Cache ETag of the object.

<b>httpStatusOutput</b>
HTTP status of the object.

<b>cacheResLastMod</b>
Value of "Last-modified" header.

<b>cacheControl</b>
Cache-Control header of the object.

<b>cacheResDate</b>
Value of "Date" header

<b>contentGroup</b>
Name of the contentgroup in which it is stored.

<b>destIP</b>
Destination IP.

<b>destIPV46</b>
Destination IP.

<b>destPort</b>
Destination Port.

<b>cacheCellComplex</b>
The state of the parameterized caching on this cell.

<b>hitParams</b>
Parameterized hit evaluation of an object.

<b>hitValues</b>
Values of hitparams for this object.

<b>cacheCellReqTime</b>
Required time of the cache cell object.

<b>cacheCellResTime</b>
Response time to the cache cell object.

<b>cacheCurAge</b>
Current age of the cache object.

<b>cacheCellExpires</b>
Expiry time of the cache cell object in seconds.

<b>cacheCellExpiresMilliSec</b>
Expiry time of the cache cell object in milliseconds.

<b>flushed</b>
Specifies whether the object is flushed.

<b>prefetch</b>
Specifies whether Integrated Cache should attempt to refresh an object immediately before it goes stale.

<b>prefetchPeriod</b>
The duration in seconds of the period during which prefetch should be attempted, immediately before the object's calculated expiry time.

<b>prefetchPeriodMilliSec</b>
The duration in milliseconds of the period during which prefetch should be attempted, immediately before the object's calculated expiry time.

<b>cacheCellCurReaders</b>
Current readers of the cache cell object.

<b>cacheCellCurMisses</b>
Current misses of the cache cell object.

<b>cacheCellHits</b>
Cache cell hits.

<b>cacheCellMisses</b>
Cache cell misses.

<b>cacheCellDHits</b>
Cache cell disk hits.

<b>cacheCellGzipCompressed</b>
The state of the response being gzip-compressed.

<b>cacheCellDeflateCompressed</b>
The state of the response being deflate-compressed.

<b>cacheCellCompressionFormat</b>
Compression format of this object. Identity means not compressed

<b>cacheCellAppFWMetadataExists</b>
AppFirewall cache object.

<b>cacheCellHttp11</b>
The state of the response to be HTTP/1.1.

<b>cacheCellWeakEtag</b>
The state of the weak HTTP Entity Tag in the cell.

<b>cacheCellResBadSize</b>
The marked state of the cell.

<b>markerReason</b>
Reason for marking the cell.

<b>cacheCellPollEveryTime</b>
The state to poll every time on object.

<b>cacheCellEtagInserted</b>
The state of the ETag to be inserted by IC for this object.

<b>cacheCellReadyWithLastByte</b>
The state of the complete arrived response.

<b>cacheInMemory</b>
The cache data is available in memory.

<b>cacheInDisk</b>
The cache data is available in disk.

<b>cacheInSecondary</b>
The cache data is available in secondary in HA deployment.

<b>cacheDirname</b>
The directory name used if saved.

<b>cacheFilename</b>
The filename used if saved.

<b>cacheCellDestipVerified</b>
The state of DNS verification.

<b>cacheCellFwpxyObj</b>
The state of the object to be stored on a request to a forward proxy.

<b>cacheCellBasefile</b>
The state of delta being used as a basefile.

<b>cacheCellMinHitFlag</b>
The state of the minhit feature on this cell.

<b>cacheCellMinHit</b>
Min hit value for the object.

<b>policy</b>
Policy info for the object.

<b>policyName</b>
Policy which created the object.

<b>selectorName</b>
The hit selector for the object.

<b>rule</b>
Selectors for this object.

<b>selectorValue</b>
The HTTP request method that caused the object to be stored.

<b>cacheUrls</b>
List of cache object URLs.

<b>numurls</b>
Total number of cache object entries returned in cacheUrls field

<b>warnBucketSkip</b>
Bucket skipped warning.

<b>totalObjs</b>
Total objects.

<b>httpCalloutCell</b>
Is it a http callout cell ?

<b>httpCalloutName</b>
Name of the http callout

<b>returnType</b>
Return type of the http callout

<b>httpCalloutResult</b>
First few bytes of http callout response

<b>locatorshow</b>
ID of the cached object.

<b>ceflags</b>
Indicates state and type of cached cell

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##expire cache object

Forces expiry of a cached object. You have to specify the locator ID of the cached object by using the -locator parameter.


##Synopsys

expire cache object (-locator &lt;positive_integer> | (-url &lt;URL>  (-host &lt;string>  [-port &lt;port>]  [-groupName &lt;string>]  [-httpMethod ( GET | POST )])))


##Arguments

<b>locator</b>
ID of the cached object to be expired To view the locator ID of the cached objects, use the show cache object command.
Minimum value: 0

<b>url</b>
The URL of the object to be expired.

<b>host</b>
The host of the object to be expired.

<b>port</b>
The host port of the object to be expired.
Default value: 80
Minimum value: 1

<b>groupName</b>
Name of the content group to which the object belongs.

<b>httpMethod</b>
HTTP request method that caused the object to be stored.
Possible values: GET, POST
Default value: GET



##flush cache object

Removes a cached object from memory and from disk (if it has a disk copy). You have to specify the locator ID of the cached object by using the -locator parameter


##Synopsys

flush cache object (-locator &lt;positive_integer> | (-url &lt;URL>  (-host &lt;string>  [-port &lt;port>]  [-groupName &lt;string>]  [-httpMethod ( GET | POST )])))


##Arguments

<b>locator</b>
ID of the cached object. To view the locator ID of the cached objects, use the show cache object command.
Minimum value: 0

<b>url</b>
URL of the object to be flushed. You must also set the Host parameter.

<b>host</b>
Host of the object to be flushed. Must provide the "url" parameter along with the host.

<b>port</b>
Host port of the object to be flushed. Must provide the "host" parameter along with the port.
Default value: 80
Minimum value: 1

<b>groupName</b>
Name of the content group to which the object belongs. Must provide the \\"host\\" parameter along with the group name.

<b>httpMethod</b>
HTTP request method that caused the object to be stored. All objects cached by that method will be flushed.
Possible values: GET, POST
Default value: GET



##save cache object

Save a cached object to local disk.


##Synopsys

save cache object [-locator &lt;positive_integer>] [-tosecondary ( YES | NO )]


##Arguments

<b>locator</b>
The ID of the cached object.
Minimum value: 0

<b>tosecondary</b>
Object will be saved onto Secondary.
Possible values: YES, NO
Default value: NO



