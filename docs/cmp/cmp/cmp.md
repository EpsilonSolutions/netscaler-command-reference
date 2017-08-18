#cmp

The following operations can be performed on "cmp":


##stat cmp

Display compression statistics.


##Synopsys

stat cmp [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


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

<b>Bandwidth saving (%) (DlBndSav)</b>
Bandwidth saving from delta compression expressed as percentage.

<b>Delta compression ratio (DlCmpRt)</b>
Ratio of compressible data received to compressed data transmitted.If this ratio is one (uncmp:1.0) that means compression is disabled or we are not able to compress even a single compressible packet.

<b>Decompression ratio (DTCmpRt)</b>
Ratio of decompressed data transmitted to compressed data received.

<b>Bandwidth saving (%) (DBndSav)</b>
Bandwidth saving from TCP compression expressed as percentage.

<b>TCP compression ratio (TCmpRt)</b>
Ratio of compressible data received to compressed data transmitted.If this ratio is one (uncmp:1.0) that means compression is disabled or we are not able to compress even a single compressible packet.

<b>TCP Bandwidth saving (%) (BndSav)</b>
Bandwidth saving from TCP compression expressed as percentage.

<b>Total HTTP compression ratio</b>
Ratio of total HTTP data received to total HTTP data transmitted.

<b>HTTP Bandwidth saving (%) (HttpBndSav)</b>
Bandwidth saving from TCP compression expressed as percentage.

<b>HTTP compression ratio</b>
Ratio of the compressible data received from the server to the compressed data sent to the client.

<b>HTTP compression requests</b>
Number of HTTP compression requests the NetScaler receives for which the response is successfully compressed. For example, after you enable compression and configure services, if you send HTTP requests to the NetScaler using a HTTP client that supports compression, and NetScaler compresses the corresponding response, this counter is incremented.

<b>Compressible bytes received</b>
Number of bytes that can be compressed, which the NetScaler receives from the server. This gives the content length of the response that the NetScaler receives from server.

<b>Compressed bytes transmitted</b>
Number of bytes the NetScaler sends to the client after compressing the response from the server.

<b>Compressible packets received</b>
Number of HTTP packets that can be compressed, which the NetScaler receives from the server.

<b>Compressed packets transmitted</b>
Number of HTTP packets that the NetScaler sends to the client after compressing the response from the server.

<b>Compressible bytes received (TCmpRxB)</b>
Number of bytes that can be compressed, which the NetScaler receives from the server. This gives the content length of the response that the NetScaler receives from server.

<b>Compressible packets received (TCmpRxP)</b>
Total number of compressible packets received by NetScaler.

<b>Compressed bytes transmitted (TCmpTxB)</b>
Number of bytes that the NetScaler sends to the client after compressing the response from the server.

<b>Compressed packets transmitted (TCmpTxP)</b>
Number of TCP packets that the NetScaler sends to the client after compressing the response from the server.

<b>Quantum compression (TCmpQuan)</b>
Number of times the NetScaler compresses a quantum of data.  NetScaler buffers the data received from the server till it reaches the quantum size and then compresses the buffered data and transmits to the client.

<b>Push flag compression (TCmpPush)</b>
Number of times the NetScaler compresses data on receiving a TCP PUSH flag from the server. The PUSH flag ensures that data is compressed immediately without waiting for the buffered data size to reach the quantum size.

<b>End Of Input compression (TCmpEoi)</b>
Number of times the NetScaler compresses data on receiving End Of Input (FIN packet).  When the NetScaler receives End Of Input (FIN packet), it compresses the buffered data immediately without waiting for the buffered data size to reach the quantum size.

<b>Timer compression (TCmpTmr)</b>
Number of times the NetScaler compresses data on expiration of data accumulation timer. The timer expires if the server response is very slow and consequently, the NetScaler does not receive response for a certain amount of time.  Under such a condition, the NetScaler compresses the buffered data immediately without waiting for the buffered data size to reach the quantum size.

<b>Compressed bytes received (DCmpTRxB)</b>
Total number of compressed bytes received by NetScaler.

<b>Compressed packets received (DCmpTRxP)</b>
Total number of compressed packets received by NetScaler.

<b>Decompressed bytes transmitted (DCmpTTxB)</b>
Total number of decompressed bytes transmitted by NetScaler.

<b>Decompressed packets transmitted (DCmpTTxP)</b>
Total number of decompressed packets transmitted by NetScaler.

<b>Wrong data (DCmpErrD)</b>
Number of data errors encountered while decompressing.

<b>Less Data (DCmpErrL)</b>
Number of times NetScaler received less data than declared by protocol.

<b>More Data (DCmpErrM)</b>
Number of times NetScaler received more data than declared by protocol.

<b>Memory failures (DCmpMem)</b>
Number of times memory failures occurred while decompressing.

<b>Unknown (DCmpErrU)</b>
Number of times unknown errors occurred while decompressing.

<b>Delta compression requests (DlCmpRx)</b>
Total number of delta compression requests received by NetScaler.

<b>Delta compression applied (DlDone)</b>
Total number of delta compressions done by NetScaler.

<b>Compressible bytes received (DlCmpRxB)</b>
Total number of delta-compressible bytes received by NetScaler.

<b>Compressed bytes transmitted (DlCmpTxB)</b>
Total number of delta-compressed bytes transmitted by NetScaler.

<b>First-time access (DlCmpFAc)</b>
Total number of delta compression first accesses.

<b>Compressible packets received (DlCmpRxP)</b>
Number of delta-compressible packets received.

<b>Compressed packets transmitted (DlCmpTxP)</b>
Total number of delta-compressed packets transmitted by NetScaler.

<b>Basefile requests served (DlCBSrv)</b>
Total number of basefile requests served by NetScaler.

<b>Basefile bytes transmitted (DlCBTxB)</b>
Number of basefile bytes transmitted by NetScaler.

<b>Delta compression bypassed (DlCmpEBy)</b>
Number of times delta-compression bypassed by NetScaler.

<b>Basefile write header failed (DlCmpEBW)</b>
Number of times basefile could not be updated in NetScaler cache.

<b>Basefile no-store miss (DlCmpENM)</b>
Number of times basefile was not found in NetScaler cache.

<b>Request information too big (DlCmpERB)</b>
Number of times basefile request URL was too large.

<b>Request info alloc failed (DlCmpERF)</b>
Number of times requested basefile could not be allocated.

<b>Session allocation failed (DlCmpESF)</b>
Number of times delta compression session could not be allocated.

<b>Response bytes received (HTRspbRx)</b>
Total number of bytes of HTTP response data received.



##Related Commands

<ul><li><a href="../../../-cmp-p/-cmp-p">stat cmp policy</a></li><li><a href="../../../#stat-cmp-policy/#stat-cmp-policy">stat cmp policylabel</a></li></ul>



