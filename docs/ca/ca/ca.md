#ca

The following operations can be performed on "ca":


##stat ca

Shows CA performance statistics.


##Synopsys

stat ca [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>unindentified device bytes ratio (caunindentifiedytesHR)</b>
This tells the hit ratio of unindentified bytes

<b>Ios bytes ratio (caiosBytesHR)</b>
This tells the hit ratio of IOS bytes

<b>Other device bytes ratio (caotherBytesHR)</b>
This tells the hit ratio of Other device

<b>Laptop/desktop bytes ratio (calaptpdsktpBytesHR)</b>
This tells the hit ratio of laptop_desktop bytes

<b>Android bytes ratio (caandroidBytesHR)</b>
This tells the hit ratio of 3GP bytes

<b>3GP bytes ratio (ca3GPcacheBytesHR)</b>
This tells the hit ratio of 3GP bytes

<b>MP4 bytes ratio (CaMP4cacheBytesHR)</b>
This tells the hit ratio of MP4 bytes

<b>FLV bytes ratio (CaFLVcacheBytesHR)</b>
This tells the hit ratio of FLV bytes

<b>AAC bytes ratio (CaAACcachebytesHR)</b>
This tells the hit ratio AAC bytes served

<b>ADTS bytes ratio (CaADTScachebytesHR)</b>
This tells the byte hit ratio of ADTS bytes

<b>AppleLive PL bytes ratio (CaApleLiveStrmgPlcacheBytesHR)</b>
This tells the byte hit ratio of AppleLive Playlist bytes

<b>AppleLiveStream bytes ratio (CaApleLiveStrmngcacheBytesHR)</b>
This tells the total number of AppleLive bytes

<b>MSFT SmoothStreamPL bytes ratio (CaMsftSmthStrmingPlCaBytesHR)</b>
This tells the byte hit ratio of MicrosoftSmoothStreaming Playlist bytes

<b>MSFT SmoothStream bytes ratio (CaMsftSmthStrmingiCaBytesHR)</b>
This tells the Bytes hit ratio of MicrosoftSmoothStreaming bytes .

<b>unidentified devices (caunidentifiedHR)</b>
This tells the hit ratio of android requests

<b>IOS (caiosHR)</b>
This tells the hit ratio of ios requests

<b>Other device (caotherHR)</b>
This tells the hit ratio of other mobile device requests

<b>Laptop/desktop (calaptopdesktpHR)</b>
This tells the hit ratio of laptop/desktop requests

<b>Android (caandroidHR)</b>
This tells the hit ratio of android requests

<b>3GP (ca3GPHR)</b>
This tells the total number of 3GP requests

<b>MP4 (CacMP4HR)</b>
This tells the hit ratio of MP4 requests

<b>FLV (CacFLVHR)</b>
This tells the hit ratio of FLV requests

<b>AAC (CacAACHR)</b>
This tells the hit ratio of AAC requests

<b>ADTS (CacADTSHR)</b>
This tells the Hit Ratio of ADTS requests

<b>AppleLive PL (CacAppleLiveStreamingPlaylistiHR)</b>
This tells the hit ratio of AppleLive Playlist requests

<b>AppleLiveStream (CacAppleLiveStreamingHR)</b>
This tells the hit ratio of AppleLive requests

<b>MSFT SmoothStreamPL (CacMsftSmthStrmPlHR)</b>
This tells the hit ratio of MicrosoftSmoothStreaming Playlist requests

<b>MSFT SmoothStream (MsftSmthStrmHR)</b>
This tells the hit ratio of MicrosoftSmoothStreaming requests

<b>Total Other Objects (caOther)</b>

<b>Total Video Objects (caVideo)</b>

<b>Total Audio Objects (caAudio)</b>

<b>Total objects stored in cache (catotobj)</b>

<b>Hits being served (CaHit)</b>
This number should be close to the number of hits being served currently.

<b>Total fetch request from cache (Catotgetobjres)</b>

<b>Total Lookup Requests (CaReq)</b>

<b>MSFT SmoothStream objects (MsftSmthStrm)</b>
This tells the total number of MicrosoftSmoothStreaming requests served by NS

<b>MSFT SmoothStream hits (CacMstSmthStrm)</b>
This tells the total number of MicrosoftSmoothStreaming requests served from cache

<b>MSFT SmoothStreamPL objects (MsftSmthStreamingPl)</b>
This tells the total number of MicrosoftSmoothStreaming Playlist requests served by NS

<b>MSFT SmoothStreamPL hits (CacMsftSmthStrmPl)</b>
This tells the total number of MicrosoftSmoothStreaming Playlist requests served from cache

<b>AppleLiveStream objects (AppleLiveStrm)</b>
This tells the total number of AppleLive requests served by NS

<b>AppleLiveStream hits (CacAppleLiveStreaming)</b>
This tells the total number of AppleLive requests served from cache

<b>AppleLive PL objects (AppleLiveStrmPl)</b>
This tells the total number of AppleLive Playlist requests served by NS

<b>AppleLive PL hits (CacAppleLiveStreamingPlaylist)</b>
This tells the total number of AppleLive Playlist requests served from cache

<b>ADTS objects (CaADTS)</b>
This tells the total number of ADTS requests served by NS

<b>ADTS hits (CacADTS)</b>
This tells the total number of ADTS requests served from cache

<b>AAC objects (CaAAC)</b>
This tells the total number of AAC requests served by NS

<b>AAC hits (CacAAC)</b>
This tells the total number of AAC requests served from cache

<b>FLV objects (CaFLV)</b>
This tells the total number of FLV requests served by NS

<b>FLV hits (CacFLV)</b>
This tells the total number of FLV requests served from cache

<b>MP4 objects (CaMP4)</b>
This tells the total number of MP4 requests served by NS

<b>MP4 hits (CacMP4)</b>
This tells the total number of MP4 requests served from cache

<b>3GP Objects (ca3GP)</b>
This tells the total number of 3GP requests served by NS

<b>3GP hits (ca3GP)</b>
This tells the hit ratio of 3GP requests served from cache

<b>Total MSFT SmoothStream Bytes (CaMsftSthStrmBytes)</b>
This tells the total number of MicrosoftSmoothStreaming bytes served by NS

<b>CA MSFT SmoothStream Bytes (CaMicrosoftSmoothStreamingiCacheBytes)</b>
This tells the total number of MicrosoftSmoothStreaming bytes served from cache.

<b>Total MSFT SmoothStreamPL Bytes (CaMisftSmthStrmPlBytes)</b>
This tells the total number of MicrosoftSmoothStreaming Playlist bytes served by NS

<b>CA MSFT SmoothStreamPL Bytes (CaMicrosoftSmoothStreamingPlaylistCacheBytes)</b>
This tells the total number of MicrosoftSmoothStreaming Playlist bytes served from cache

<b>Total AppleLiveStream Bytes (CaAppleLiveStreamingBytes)</b>
This tells the total number of AppleLive bytes served by NS

<b>CA AppleLiveStream Bytes (CaAppleLiveStreamingcacheBytes)</b>
This tells the total number of AppleLive bytes served from cache

<b>Total AppleLive PL Bytes (CaAppleLiveStreamingPlaylistBytes)</b>
This tells the total number of AppleLive Playlist bytes served by NS

<b>CA AppleLivePL Bytes (CaAppleLiveStreamingPlaylistcacheBytes)</b>
This tells the total number of AppleLive Playlist bytes served from cache

<b>Total ADTS bytes (CaADTSbytes)</b>
This tells the total number of ADTS bytes served by NS

<b>CA ADTS bytes (CaADTScachebytes)</b>
This tells the total number of ADTS bytes served from cache

<b>Total AAC bytes (CaAACbytes)</b>
This tells the total number of AAC bytes served by NS

<b>CA AAC bytes (CaAACcachebytes)</b>
This tells the total number of AAC bytes served from cache

<b>Total FLV bytes (CaFLVBytes)</b>
This tells the total number of FLV bytes served by NS

<b>CA FLV bytes (CaFLVcacheBytes)</b>
This tells the total number of FLV bytes served from cache

<b>Total MP4 bytes (CaMP4Bytes)</b>
This tells the total number of MP4 bytes served by NS

<b>CA MP4 bytes (CaMP4cacheBytes)</b>
This tells the total number of MP4 bytes served from cache

<b>Total 3GP Bytes (ca3GPBytes)</b>
This tells the total number of 3GP bytes served by NS

<b>CA 3GP Bytes (ca3GPcacheBytes)</b>
This tells the total number of 3GP bytes served from cache

<b>Android requests (caandroid)</b>
Total number of android requests to netscaler

<b>Laptop/Desktop requests (calaptopDesktp)</b>
Total number of laptop/desktop requests to netscaler

<b>IOS requests (caios)</b>
Total number of iOs requests to netscaler

<b>Other requests (caother)</b>
Total number of other mobile device requests to netscaler

<b>Unidentified requests (caunidentified)</b>
Total number of unidentified requests to netscaler

<b>Android hits (caandroidcache)</b>
This tells android requests served from cache

<b>IOS hits (caioscache)</b>
This tells iOS requests served from cache

<b>Other device hits (caothercache)</b>
This tells Other device requests served from cache

<b>laptop/desktop hits (calaptopdesktpcache)</b>
This tells laptop/desktop requests served from cache

<b>Unidentified device hits (caunidentifiedcache)</b>
This tells unidentified device requests served from cache

<b>Total Android Bytes (caandroidBytes)</b>
This tells the total number of Android bytes served by NS

<b>Total IOS Bytes (caiosBytes)</b>
This tells the total number of IOS bytes served by NS

<b>Total Other device Bytes (caotherBytes)</b>
This tells the total number of Other mobile device bytes served by NS

<b>Total Laptop/desktop Bytes (calaptopdesktpBytes)</b>
This tells the total number of Laptop/desktop bytes served by NS

<b>Total unidentified device Bytes (caunidentifiedBytes)</b>
This tells the total number of unidentified device bytes served by NS

<b>CA Android Bytes (caandroidcacheBytes)</b>
This tells the total number of Android bytes served from cache

<b>CA IOS Bytes (caioscacheBytes)</b>
This tells the total number of IOS bytes served from cache

<b>CA Other device Bytes (caothercacheBytes)</b>
This tells the total number of other device bytes served from cache

<b>CA Laptop/desktop Bytes (calaptpdesktpBytes)</b>
This tells the total number of Laptop/desktop bytes served from cache

<b>CA unindentified device Bytes (caunindentifiedBytes)</b>
This tells the total number of unindentified device bytes served from cache



