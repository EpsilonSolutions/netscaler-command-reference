#protocol http

The following operations can be performed on "protocol http":


##stat protocol http

Displays statistics of the HTTP protocol.


##Synopsys

stat protocol http [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Total SPDY requests (SPDYStrm)</b>
Total number of requests received over SPDYv2 and SPDYv3

<b>Total requests (HTReqRx)</b>
Total number of HTTP requests received.

<b>Total responses (HTRspRx)</b>
Total number of HTTP responses sent.

<b>Request bytes received (HTReqbRx)</b>
Total number of bytes of HTTP request data received.

<b>Response bytes received (HTRspbRx)</b>
Total number of bytes of HTTP response data received.

<b>GETs (HTGETs)</b>
Total number of HTTP requests received with the GET method.

<b>POSTs (HTPOSTs)</b>
Total number of HTTP requests received with the POST method.

<b>Other methods (HTOthers)</b>
Total number of HTTP requests received with methods other than GET and POST. Some of the other well-defined HTTP methods are HEAD, PUT, DELETE, OPTIONS, and TRACE. User-defined methods are also allowed.

<b>HTTP/1.0 requests (HT10ReqRx)</b>
Total number of HTTP/1.0 requests received.

<b>HTTP/1.1 requests (HT11ReqRx)</b>
Total number of HTTP/1.1 requests received.

<b>Content-length requests (HTCLnReq)</b>
Total number of HTTP requests in which the Content-length field of the HTTP header has been set. Content-length specifies the length of the content, in bytes, in the associated HTTP body.

<b>Chunked requests (HTChkReq)</b>
Total number of HTTP requests in which the Transfer-Encoding field of the HTTP header has been set to chunked.

<b>Request bytes transmitted (HTReqbTx)</b>
Total number of bytes of HTTP request data transmitted.

<b>HTTP/1.0 responses (HT10RspRx)</b>
Total number of HTTP/1.0 responses sent.

<b>HTTP/1.1 responses (HT11RspRx)</b>
Total number of HTTP/1.1 responses sent.

<b>Content-length responses (HTCLnRsp)</b>
Total number of HTTP responses sent in which the Content-length field of the HTTP header has been set. Content-length specifies the length of the content, in bytes, in the associated HTTP body.

<b>Chunked responses (HTChunk)</b>
Total number of HTTP responses sent in which the Transfer-Encoding field of the HTTP header has been set to chunked. This setting is used when the server wants to start sending the response before knowing its total length. The server breaks the response into chunks and sends them in sequence, inserting the length of each chunk before the actual data. The message ends with a chunk of size zero.

<b>Multi-part responses (HTMPrtHd)</b>
Total number of HTTP multi-part responses sent. In multi-part responses, one or more entities are encapsulated within the body of a single message.

<b>FIN-terminated responses (HTNoCLnChunk)</b>
Total number of FIN-terminated responses sent. In FIN-terminated responses, the server finishes sending the data and closes the connection.

<b>Response bytes transmitted (HTRspbTx)</b>
Total number of bytes of HTTP response data transmitted.

<b>Incomplete headers (HTIncHd)</b>
Total number of HTTP requests and responses received in which the HTTP header spans more than one packet.

<b>Incomplete request headers (HTIncReqHd)</b>
Total number of HTTP requests received in which the header spans more than one packet.

<b>Incomplete response headers (HTIncRspHd)</b>
Total number of HTTP responses received in which the header spans more than one packet.

<b>HTTP 500 Server-busy Responses (HT500Rsp)</b>
Total number of HTTP error responses received. Some of the error responses are: 
500 	Internal Server Error
501 	Not Implemented
502 	Bad Gateway
503 	Service Unavailable
504 	Gateway Timeout
505 	HTTP Version Not Supported

<b>Large/Invalid messages (HTInvReq)</b>
Total number of requests and responses received with large body.

<b>Large/Invalid chunk requests (HTInvChkRx)</b>
Total number of requests received with large chunk size, in which the Transfer-Encoding field of the HTTP header has been set to chunked.

<b>Large/Invalid content-length (HTInvCLn)</b>
Total number of requests received with large content, in which the Content-length field of the HTTP header has been set. Content-length specifies the length of the content, in bytes, in the associated HTTP body.

<b>SPDYv2 requests (SPDY2Strm)</b>
Total number of requests received over SPDYv2

<b>SPDYv3 requests (SPDY3Strm)</b>
Total number of requests received over SPDYv3



##Related Commands

<ul><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol tcp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol icmp</a></li><li><a href="../../../tml#stat-protocol/tml#stat-protocol">stat protocol ipv6</a></li><li><a href="../../../.html#stat-protocol-i/.html#stat-protocol-i">stat protocol icmpv6</a></li><li><a href="../../../ml#stat-protoco/ml#stat-protoco">stat protocol udp</a></li></ul>



