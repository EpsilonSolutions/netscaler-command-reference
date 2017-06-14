#ns httpProfile

The following operations can be performed on "ns httpProfile":


[add](#add-ns-httpprofile) | [rm](#rm-ns-httpprofile) | [set](#set-ns-httpprofile) | [unset](#unset-ns-httpprofile) | [show](#show-ns-httpprofile)

##add ns httpProfile

Adds an HTTP profile to the NetScaler appliance.


##Synopsys

add ns httpProfile &lt;name> [-dropInvalReqs ( ENABLED | DISABLED )] [-markHttp09Inval ( ENABLED | DISABLED )] [-markConnReqInval ( ENABLED | DISABLED )] [-cmpOnPush ( ENABLED | DISABLED )] [-conMultiplex ( ENABLED | DISABLED )] [-maxReusePool &lt;positive_integer>] [-dropExtraCRLF ( ENABLED | DISABLED )] [-incompHdrDelay &lt;positive_integer>] [-webSocket ( ENABLED | DISABLED )] [-rtspTunnel ( ENABLED | DISABLED )] [-reqTimeout &lt;positive_integer>] [-adptTimeout ( ENABLED | DISABLED )] [-reqTimeoutAction &lt;string>] [-dropExtraData ( ENABLED | DISABLED )] [-webLog ( ENABLED | DISABLED )] [-clientIpHdrExpr &lt;expression>] [-maxReq &lt;positive_integer>] [-persistentETag ( ENABLED | DISABLED )] [-spdy &lt;spdy>] [-reusePoolTimeout &lt;positive_integer>] [-maxHeaderLen &lt;positive_integer>]


##Arguments

<b>name</b>
Name for an HTTP profile. Must begin with a letter, number, or the underscore \\(_\\) character. Other characters allowed, after the first character, are the hyphen \\(-\\), period \\(.\\), hash \\(\\#\\), space \\( \\), at \\(@\\), and equal \\(=\\) characters. The name of a HTTP profile cannot be changed after it is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my http profile" or 'my http profile'\\).

<b>dropInvalReqs</b>
Drop invalid HTTP requests or responses.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>markHttp09Inval</b>
Mark HTTP/0.9 requests as invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>markConnReqInval</b>
Mark CONNECT requests as invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cmpOnPush</b>
Start data compression on receiving a TCP packet with PUSH flag set.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>conMultiplex</b>
Reuse server connections for requests from more than one client connections.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxReusePool</b>
Maximum limit on the number of connections, from the NetScaler to a particular server that are kept in the reuse pool. This setting is helpful for optimal memory utilization and for reducing the idle connections to the server just after the peak time.
Maximum value: 360000

<b>dropExtraCRLF</b>
Drop any extra 'CR' and 'LF' characters present after the header.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>incompHdrDelay</b>
Maximum time to wait, in milliseconds, between incomplete header packets. If the header packets take longer to arrive at NetScaler, the connection is silently dropped.
Default value: 7000
Maximum value: 360000

<b>webSocket</b>
HTTP connection to be upgraded to a web socket connection. Once upgraded, NetScaler does not process Layer 7 traffic on this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rtspTunnel</b>
Allow RTSP tunnel in HTTP. Once application/x-rtsp-tunnelled is seen in Accept or Content-Type header, NetScaler does not process Layer 7 traffic on this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>reqTimeout</b>
Time, in seconds, within which the HTTP request must complete. If the request does not complete within this time, the specified request timeout action is executed.
Maximum value: 86400

<b>adptTimeout</b>
Adapts the configured request timeout based on flow conditions. The timeout is increased or decreased internally and applied on the flow.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>reqTimeoutAction</b>
Action to take when the HTTP request does not complete within the specified request timeout duration. You can configure the following actions:
* RESET - Send RST (reset) to client when timeout occurs.
* DROP - Drop silently when timeout occurs.
* Custom responder action - Name of the responder action to trigger when timeout occurs, used to send custom message.

<b>dropExtraData</b>
Drop any extra data when server sends more data than the specified content-length.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>webLog</b>
Enable or disable web logging.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>clientIpHdrExpr</b>
Name of the header that contains the real client IP address.

<b>maxReq</b>
Maximum requests allowed on a single connection.
Default value: 0
Maximum value: 65534

<b>persistentETag</b>
Generate the persistent NetScaler specific ETag for the HTTP response with ETag header.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>spdy</b>
Enable SPDYv2 or SPDYv3 or both over SSL vserver. SSL will advertise SPDY support during NPN Handshake. Both SPDY versions are enabled when this parameter is set to BOTH.
Possible values: DISABLED, ENABLED, V2, V3
Default value: DISABLED

<b>reusePoolTimeout</b>
Idle timeout (in seconds) for server connections in re-use pool. Connections in the re-use pool are flushed, if they remain idle for the configured timeout.
Default value: 0
Minimum value: 0
Maximum value: 31536000

<b>maxHeaderLen</b>
Number of bytes to be queued to look for complete header before returning error. If complete header is not obtained after queuing these many bytes, request will be marked as invalid and no L7 processing will be done for that TCP connection.
Default value: 24820
Minimum value: 2048
Maximum value: 61440



##Example

add httpprofile &lt;profile name&gt; -dropInvalReqs ON -markHttp09Inval ON

##rm ns httpProfile

Removes an HTTP profile from the appliance.


##Synopsys

rm ns httpProfile &lt;name>


##Arguments

<b>name</b>
Name of the HTTP profile to be removed.



##Example

rm httpprofile &lt;profile name&gt;

##set ns httpProfile

Modifies the attributes of an HTTP profile.


##Synopsys

set ns httpProfile &lt;name> [-dropInvalReqs ( ENABLED | DISABLED )] [-markHttp09Inval ( ENABLED | DISABLED )] [-markConnReqInval ( ENABLED | DISABLED )] [-cmpOnPush ( ENABLED | DISABLED )] [-conMultiplex ( ENABLED | DISABLED )] [-maxReusePool &lt;positive_integer>] [-dropExtraCRLF ( ENABLED | DISABLED )] [-incompHdrDelay &lt;positive_integer>] [-webSocket ( ENABLED | DISABLED )] [-rtspTunnel ( ENABLED | DISABLED )] [-reqTimeout &lt;positive_integer>] [-adptTimeout ( ENABLED | DISABLED )] [-reqTimeoutAction &lt;string>] [-dropExtraData ( ENABLED | DISABLED )] [-webLog ( ENABLED | DISABLED )] [-clientIpHdrExpr &lt;expression>] [-maxReq &lt;positive_integer>] [-persistentETag ( ENABLED | DISABLED )] [-spdy &lt;spdy>] [-reusePoolTimeout &lt;positive_integer>] [-maxHeaderLen &lt;positive_integer>]


##Arguments

<b>name</b>
Name of the HTTP profile to be modified.

<b>dropInvalReqs</b>
Drop invalid HTTP requests or responses.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>markHttp09Inval</b>
Mark HTTP/0.9 requests as invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>markConnReqInval</b>
Mark CONNECT requests as invalid.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>cmpOnPush</b>
Start data compression on receiving a TCP packet with PUSH flag set.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>conMultiplex</b>
Reuse server connections for requests from more than one client connections.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxReusePool</b>
Maximum limit on the number of connections, from the NetScaler to a particular server that are kept in the reuse pool. This setting is helpful for optimal memory utilization and for reducing the idle connections to the server just after the peak time.
Maximum value: 360000

<b>dropExtraCRLF</b>
Drop any extra 'CR' and 'LF' characters present after the header.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>incompHdrDelay</b>
Maximum time to wait, in milliseconds, between incomplete header packets. If the header packets take longer to arrive at NetScaler, the connection is silently dropped.
Default value: 7000
Maximum value: 360000

<b>webSocket</b>
HTTP connection to be upgraded to a web socket connection. Once upgraded, NetScaler does not process Layer 7 traffic on this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>rtspTunnel</b>
Allow RTSP tunnel in HTTP. Once application/x-rtsp-tunnelled is seen in Accept or Content-Type header, NetScaler does not process Layer 7 traffic on this connection.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>reqTimeout</b>
Time, in seconds, within which the HTTP request must complete. If the request does not complete within this time, the specified request timeout action is executed.
Maximum value: 86400

<b>adptTimeout</b>
Adapts the configured request timeout based on flow conditions. The timeout is increased or decreased internally and applied on the flow.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>reqTimeoutAction</b>
Action to take when the HTTP request does not complete within the specified request timeout duration. You can configure the following actions:
* RESET - Send RST (reset) to client when timeout occurs.
* DROP - Drop silently when timeout occurs.
* Custom responder action - Name of the responder action to trigger when timeout occurs, used to send custom message.

<b>dropExtraData</b>
Drop any extra data when server sends more data than the specified content-length.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>webLog</b>
Enable or disable web logging.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>clientIpHdrExpr</b>
Name of the header that contains the real client IP address.

<b>maxReq</b>
Maximum requests allowed on a single connection.
Default value: 0
Maximum value: 65534

<b>persistentETag</b>
Generate the persistent NetScaler specific ETag for the HTTP response with ETag header.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>spdy</b>
Enable SPDYv2 or SPDYv3 or both over SSL vserver. SSL will advertise SPDY support during NPN Handshake. Both SPDY versions are enabled when this parameter is set to BOTH.
Possible values: DISABLED, ENABLED, V2, V3
Default value: DISABLED

<b>reusePoolTimeout</b>
Idle timeout (in seconds) for server connections in re-use pool. Connections in the re-use pool are flushed, if they remain idle for the configured timeout.
Default value: 0
Minimum value: 0
Maximum value: 31536000

<b>maxHeaderLen</b>
Number of bytes to be queued to look for complete header before returning error. If complete header is not obtained after queuing these many bytes, request will be marked as invalid and no L7 processing will be done for that TCP connection.
Default value: 24820
Minimum value: 2048
Maximum value: 61440



##Example

set httpprofile &lt;profile name&gt; -dropInvalReqs ON -markHttp09Inval ON

##unset ns httpProfile

Removes the attributes of the HTTP profile. Attributes for which a default value is available revert to their default values. Refer to the 'set ns httpProfile' command for a description of the parameters..Refer to the set ns httpProfile command for meanings of the arguments.


##Synopsys

unset ns httpProfile &lt;name> [-dropInvalReqs] [-markHttp09Inval] [-markConnReqInval] [-cmpOnPush] [-conMultiplex] [-maxReusePool] [-dropExtraCRLF] [-incompHdrDelay] [-webSocket] [-dropExtraData] [-clientIpHdrExpr] [-reqTimeout] [-adptTimeout] [-reqTimeoutAction] [-webLog] [-maxReq] [-persistentETag] [-spdy] [-reusePoolTimeout] [-maxHeaderLen] [-rtspTunnel]


##show ns httpProfile

Displays information about HTTP profiles configured on the appliance.


##Synopsys

show ns httpProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the HTTP profile to be displayed. If a name is not provided, information about all HTTP profiles is shown.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>dropInvalReqs</b>
Dropping of invalid HTTP requests/responses

<b>markHttp09Inval</b>
Invalidating HTTP 0.9 requests

<b>markConnReqInval</b>
Invalidating CONNECT HTTP requests

<b>cmpOnPush</b>
Compression on PUSH packet

<b>conMultiplex</b>
Reuse server connections for requests from more than one client connections.

<b>maxReusePool</b>
Maximum connections in reusepool

<b>webSocket</b>
HTTP connection to be upgraded to a web socket connection. Once upgraded, NetScaler does not process Layer 7 traffic on this connection.

<b>refCnt</b>
Number of entities using this profile

<b>stateflag</b>
State flag

<b>dropExtraCRLF</b>
Drop any extra 'CR' and 'LF' characters present after the header.

<b>incompHdrDelay</b>
Maximum time to wait, in milliseconds, between incomplete header packets. If the header packets take longer to arrive at NetScaler, the connection is silently dropped.

<b>reqTimeout</b>
Time, in seconds, within which the HTTP request must complete. If the request does not complete within this time, the specified request timeout action is executed.

<b>adptTimeout</b>
Adapts the configured request timeout based on flow conditions. The timeout is increased or decreased internally and applied on the flow.

<b>reqTimeoutAction</b>
Action to take when the HTTP request does not complete within the specified request timeout duration. You can configure the following actions:
* RESET - Send RST (reset) to client when timeout occurs.
* DROP - Drop silently when timeout occurs.
* Custom responder action - Name of the responder action to trigger when timeout occurs, used to send custom message.

<b>dropExtraData</b>
Drop any extra data when server sends more data than the specified content-length.

<b>webLog</b>
Disabling weblog option

<b>clientIpHdrExpr</b>
Name of the header that contains the real client IP address.

<b>maxReq</b>
Maximum requests allowed on a single connection.

<b>persistentETag</b>
Generate the persistent NetScaler specific ETag for the HTTP response with ETag header.

<b>spdy</b>
Enable SPDYv2 or SPDYv3 or both over SSL vserver. SSL will advertise SPDY support during NPN Handshake. Both SPDY versions are enabled when this parameter is set to BOTH.

<b>reusePoolTimeout</b>
Idle timeout (in seconds) for server connections in re-use pool. Connections in the re-use pool are flushed, if they remain idle for the configured timeout.

<b>maxHeaderLen</b>
Number of bytes to be queued to look for complete header before returning error. If complete header is not obtained after queuing these many bytes, request will be marked as invalid and no L7 processing will be done for that TCP connection.

<b>rtspTunnel</b>
Allow RTSP tunnel in HTTP. Once application/x-rtsp-tunnelled is seen in Accept or Content-Type header, NetScaler does not process Layer 7 traffic on this connection.

<b>devno</b>

<b>count</b>



##Example

show http profile [profile name]
