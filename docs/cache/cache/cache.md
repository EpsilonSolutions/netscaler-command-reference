#cache

The following operations can be performed on "cache":


##stat cache

Shows Integrated Cache performance statistics.


##Synopsys

stat cache [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Maximum memory(KB) Deprecated (MaxMem)</b>
Largest amount of memory the NetScaler can dedicate to caching, up to 50% of available memory. A 0 value disables caching, but the caching module continues to run.

<b>Recent successful reval ratio(%) (RPSucRev)</b>
Recently recorded percentage of times stored content was successfully revalidated by a 304 response rather than by a full response

<b>Recent storable miss ratio(%) (RPctStMis)</b>
Recently recorded ratio of store-able misses to all misses expressed as percentage.

<b>Recent parameterized 304 hit ratio(%) (RPPHit)</b>
Recently recorded ratio of parameterized 304 hits to all parameterized hits expressed as a percentage

<b>Recent origin bandwidth saved(%) (RPOrBan)</b>
Bytes served from cache divided by total bytes served to client. This ratio can be greater than 1 because of the assumption that all compression has been done in the NetScaler.

<b>Recent hit ratio(%) (RPctHit)</b>
Recently recorded cache hit ratio expressed as percentage

<b>Recent byte hit ratio(%) (RPcByHit)</b>
Recently recorded cache byte hit ratio expressed as percentage. Here we define byte hit ratio as ((number of bytes served from the cache)/(total number of bytes served to the client)). This is the standard definition of Byte Hit Ratio. If compression is turned ON in NS then this ratio doesn't mean much. This might under or over estimate the origin-to-cache bandwidth saving (depending upon whether bytes served by CMP in NetScaler are more or less than compressed bytes served from the cache). If CMP is turned OFF in NS then this ratio is same as cacheRecentPercentOriginBandwidthSaved.

<b>Recent 304 hit ratio(%) (RPct304Hit)</b>
Recently recorded ratio of 304 hits to all hits expressed as percentage

<b>Utilized memory(KB) (UtiMem)</b>
Amount of memory the integrated cache is currently using.

<b>Maximum memory active value(KB) (MaxMemActive)</b>
Currently active value of maximum memory

<b>Maximum memory(KB) (Max64Mem)</b>
Largest amount of memory the NetScaler can dedicate to caching, up to 50% of available memory. A 0 value disables caching, but the caching module continues to run.

<b>Poll every time hit ratio(%) (PPeHit)</b>
Percentage of cache hits in content groups that have Poll Every Time enabled, relative to all searches of content groups with Poll Every Time enabled.

<b>Poll every time hits (PeHit)</b>
Number of times a cache hit was found during a search of a content group that has Poll Every Time enabled.

<b>Parameterized 304 hit ratio(%) (PP304Hit)</b>
Percentage of parameterized 304 hits relative to all parameterized hits.

<b>Total parameterized hits (PHit)</b>
Parameterized requests resulting in either a 304 or non-304 hit.

<b>Successful reval ratio(%) (PSucRev)</b>
Percentage of times stored content was successfully revalidated by a 304 (Object Not Modifed) response rather than by a full response

<b>Storable miss ratio(%) (PStrMiss)</b>
Responses that were fetched from the origin, stored in the cache, and then served to the client, as a percentage of all cache misses.

<b>Conversions to conditional req (FuToCon)</b>
Number of user-agent requests for a cached  Poll Every Time (PET) response that were sent to the origin server as conditional requests.

<b>Successful revalidations (TSucRev)</b>
Total number of times stored content was successfully revalidated by a 304 Not Modified response from the origin.

<b>Revalidations (Reval)</b>
Responses that an intervening cache revalidated with the integrated cache before serving, as determined by a Cache-Control: Max-Age header configurable in the integrated cache

<b>Non-storable misses (NStrMiss)</b>
Cache misses for which the fetched response is not stored in the cache. These responses match policies with a NOCACHE action or are affected by Poll Every Time.

<b>Storable misses (StrMiss)</b>
Cache misses for which the fetched response is stored in the cache before serving it to the client. Storable misses conform to a built-in or user-defined caching policy that contains a CACHE action.

<b>Compressed bytes from cache (CmpBySer)</b>
Number of compressed bytes served from the cache

<b>Byte hit ratio(%) (PByHit)</b>
Bytes served from the cache divided by total bytes served to the client. If compression is On in the NetScaler, this ratio may not reflect the bytes served by the compression module. If the compression is Off, this ratio is the same as cachePercentOriginBandwidthSaved.

<b>Bytes served by cache (BySer)</b>
Total number of bytes served from the integrated cache

<b>Bytes served by NetScaler (RespBy)</b>
Total number of HTTP response bytes served by NetScaler from both the origin and the cache

<b>304 hit ratio(%) (Pct304Hit)</b>
304 responses as a percentage of all responses that the NetScaler served.

<b>Marker objects (NumMark)</b>
Marker objects created when a response exceeds the maximum or minimum size for entries in its content group or has not yet received the minimum number of hits required for items in its content group.

<b>Origin bandwidth saved(%) (POrBan)</b>
Percentage of origin bandwidth saved, expressed as number of bytes served from the integrated cache divided by all bytes served. The assumption is that all compression is done in the NetScaler.

<b>Hit ratio(%) (PctHit)</b>
Cache hits as percentage of the total number of requests

<b>Misses (TotMiss)</b>
Intercepted HTTP requests requiring fetches from origin server.

<b>Hits (TotHit)</b>
Responses served from the integrated cache. These responses match a policy with a CACHE action.

<b>Requests (CacReq)</b>
Total cache hits plus total cache misses.

<b>Cached objects (NumCac)</b>
Responses currently in integrated cache. Includes responses fully downloaded, in the process of being downloaded, and expired or flushed but not yet removed.

<b>Hits being served (CacHit)</b>
This number should be close to the number of hits being served currently.

<b>Misses being handled (CurMiss)</b>
Responses fetched from the origin and served from the cache. Should approximate storable misses. Does not include non-storable misses.

<b>Non-304 hits (Non304Hit)</b>
Total number of full (non-304) responses served from the cache. A 304 status code indicates that a response has not been modified since the last time it was served

<b>304 hits (304Hit)</b>
Object not modified responses served from the cache. (Status code 304 served instead of the full response.)

<b>sql hits (sqlHit)</b>
sql response served from cache

<b>Expire at last byte (ExpLa)</b>
Instances of content expiring immediately after receiving the last body byte due to the Expire at Last Byte setting for the content group.

<b>Flashcache misses (FlMi)</b>
Number of requests to a content group with flash cache enabled that were cache misses. Flash cache distributes the response to all the clients in aqueue.

<b>Flashcache hits (FlHi)</b>
Number of requests to a content group with flash cache enabled that were cache hits. The flash cache setting queues requests that arrive simultaneously and distributes the response to all the clients in the queue.

<b>Parameterized inval requests (PInReq)</b>
Requests matching a policy with an invalidation (INVAL) action and a content group that uses an invalidation selector or parameters.

<b>Full inval requests (NPInReq)</b>
Requests that match an invalidation policy where the invalGroups parameter is configured and expires one or more content groups.

<b>Inval requests (INStrMis)</b>
Requests that match an invalidation policy and result in expiration of specific cached responses or entire content groups.

<b>Parameterized requests (PReq)</b>
Total number of requests where the content group has hit and invalidation parameters or selectors.

<b>Parameterized non-304 hits (PN304Hit)</b>
Parameterized requests resulting in a full response (not status code 304: Object Not Updated) served from the cache.

<b>Parameterized 304 hits (P304Hit)</b>
Parameterized requests resulting in an object not modified (status code 304) response.

<b>Poll every time requests (PeReq)</b>
Requests that triggered a search of a content group that has Poll Every Time (PET) enabled (always consult the origin server before serving cached data).

<b>Memory allocation failures (ErrMem)</b>
Total number of times the cache failed to allocate memory to store responses.

<b>Largest response so far(B) (LarResp)</b>
Size, in bytes, of largest response sent to client from the cache or the origin server.

<b>Compressed bytes transmitted</b>
Number of bytes the NetScaler sends to the client after compressing the response from the server.

<b>Compressible bytes received</b>
Number of bytes that can be compressed, which the NetScaler receives from the server. This gives the content length of the response that the NetScaler receives from server.

<b>Response bytes received (HTRspbRx)</b>
Total number of bytes of HTTP response data received.



##Related Commands

<ul><li><a href="../../../stat-cache-p/stat-cache-p">stat cache policy</a></li><li><a href="../../../html#stat-cache-policy/html#stat-cache-policy">stat cache policylabel</a></li><li><a href="../../../.html#stat-cache-content/.html#stat-cache-content">stat cache contentGroup</a></li></ul>



