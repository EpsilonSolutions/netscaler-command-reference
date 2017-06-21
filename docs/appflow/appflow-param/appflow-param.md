#appflow param

The following operations can be performed on "appflow param":


[set](#set-appflow-param) | [unset](#unset-appflow-param) | [show](#show-appflow-param)

##set appflow param

Configures AppFlow parameters.


##Synopsys

set appflow param [-templateRefresh &lt;secs>] [-appnameRefresh &lt;secs>] [-flowRecordInterval &lt;secs>] [-udpPmtu &lt;positive_integer>] [-httpUrl ( ENABLED | DISABLED )] [-AAAUserName ( ENABLED | DISABLED )] [-httpCookie ( ENABLED | DISABLED )] [-httpReferer ( ENABLED | DISABLED )] [-httpMethod ( ENABLED | DISABLED )] [-httpHost ( ENABLED | DISABLED )] [-httpUserAgent ( ENABLED | DISABLED )] [-clientTrafficOnly ( YES | NO )] [-httpContentType ( ENABLED | DISABLED )] [-httpAuthorization ( ENABLED | DISABLED )] [-httpVia ( ENABLED | DISABLED )] [-httpXForwardedFor ( ENABLED | DISABLED )] [-httpLocation ( ENABLED | DISABLED )] [-httpSetCookie ( ENABLED | DISABLED )] [-httpSetCookie2 ( ENABLED | DISABLED )] [-connectionChaining ( ENABLED | DISABLED )] [-httpDomain ( ENABLED | DISABLED )] [-skipCacheRedirectionHttpTransaction ( ENABLED | DISABLED )] [-identifierName ( ENABLED | DISABLED )] [-identifierSessionName ( ENABLED | DISABLED )] [-observationDomainId &lt;positive_integer>] [-observationDomainName &lt;string>]


##Arguments

<b>templateRefresh</b>
Refresh interval, in seconds, at which to export the template data. Because data transmission is in UDP, the templates must be resent at regular intervals.
Default value: 600
Minimum value: 60
Maximum value: 3600

<b>appnameRefresh</b>
Interval, in seconds, at which to send Appnames to the configured collectors. Appname refers to the name of an entity (virtual server, service, or service group) in the NetScaler appliance.
Default value: 600
Minimum value: 60
Maximum value: 3600

<b>flowRecordInterval</b>
Interval, in seconds, at which to send flow records to the configured collectors.
Default value: 60
Minimum value: 60
Maximum value: 3600

<b>udpPmtu</b>
MTU, in bytes, for IPFIX UDP packets.
Default value: 1472
Minimum value: 128
Maximum value: 1472

<b>httpUrl</b>
Include the http URL that the NetScaler appliance received from the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>AAAUserName</b>
Enable AppFlow AAA Username logging.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpCookie</b>
Include the cookie that was in the HTTP request the appliance received from the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpReferer</b>
Include the web page that was last visited by the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpMethod</b>
Include the method that was specified in the HTTP request that the appliance received from the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpHost</b>
Include the host identified in the HTTP request that the appliance received from the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpUserAgent</b>
Include the client application through which the HTTP request was received by the NetScaler appliance.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>clientTrafficOnly</b>
Generate AppFlow records for only the traffic from the client.
Possible values: YES, NO
Default value: NO

<b>httpContentType</b>
Include the HTTP Content-Type header sent from the server to the client to determine the type of the content sent.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpAuthorization</b>
Include the HTTP Authorization header information.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpVia</b>
Include the httpVia header which contains the IP address of proxy server through which the client accessed the server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpXForwardedFor</b>
Include the httpXForwardedFor header, which contains the original IP Address of the client using a proxy server to access the server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpLocation</b>
Include the HTTP location headers returned from the HTTP responses.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpSetCookie</b>
Include the Set-cookie header sent from the server to the client in response to a HTTP request.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpSetCookie2</b>
Include the Set-cookie header sent from the server to the client in response to a HTTP request.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>connectionChaining</b>
Enable connection chaining so that the client server flows of a connection are linked. Also the connection chain ID is propagated across NetScalers, so that in a multi-hop environment the flows belonging to the same logical connection are linked. This id is also logged as part of appflow record
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>httpDomain</b>
Include the http domain request to be exported.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>skipCacheRedirectionHttpTransaction</b>
Skip Cache http transaction. This HTTP transaction is specific to Cache Redirection module. In Case of Cache Miss there will be another HTTP transaction initiated by the cache server.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>identifierName</b>
Include the stream identifier name to be exported.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>identifierSessionName</b>
Include the stream identifier session name to be exported.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>observationDomainId</b>
An observation domain groups a set of NetScalers based on deployment: cluster, HA etc. A unique Observation Domain ID is required to be assigned to each such group.
Default value: 0
Minimum value: 1000

<b>observationDomainName</b>
Name of the Observation Domain defined by the observation domain ID.



##Example

set appflow param -templateRefresh 240

##unset appflow param

Use this command to remove appflow param settings.Refer to the set appflow param command for meanings of the arguments.


##Synopsys

unset appflow param [-templateRefresh] [-appnameRefresh] [-flowRecordInterval] [-udpPmtu] [-httpUrl] [-AAAUserName] [-httpCookie] [-httpReferer] [-httpMethod] [-httpHost] [-httpUserAgent] [-clientTrafficOnly] [-httpContentType] [-httpAuthorization] [-httpVia] [-httpXForwardedFor] [-httpLocation] [-httpSetCookie] [-httpSetCookie2] [-connectionChaining] [-httpDomain] [-skipCacheRedirectionHttpTransaction] [-identifierName] [-identifierSessionName] [-observationDomainId] [-observationDomainName]


##show appflow param

Displays AppFlow parameters.


##Synopsys

show appflow param


##Outputs

<b>templateRefresh</b>
Refresh interval, in seconds, at which to export the template data. Because data transmission is in UDP, the templates must be resent at regular intervals.

<b>appnameRefresh</b>
Interval, in seconds, at which to send Appnames to the configured collectors. Appname refers to the name of an entity (virtual server, service, or service group) in the NetScaler appliance.

<b>flowRecordInterval</b>
Interval, in seconds, at which to send flow records to the configured collectors.

<b>udpPmtu</b>
MTU, in bytes, for IPFIX UDP packets.

<b>httpUrl</b>
State of AppFlow HTTP URL logging.

<b>AAAUserName</b>
State of AppFlow AAA User logging.

<b>httpCookie</b>
State of AppFlow HTTP cookie logging.

<b>httpReferer</b>
State of AppFlow HTTP referer logging.

<b>httpMethod</b>
State of AppFlow HTTP method logging.

<b>httpHost</b>
State of AppFlow HTTP host logging.

<b>httpUserAgent</b>
State of AppFlow HTTP user-agent logging.

<b>clientTrafficOnly</b>
Generate AppFlow records for only the traffic from the client.

<b>httpContentType</b>
State of AppFlow HTTP Content-Type header logging

<b>httpAuthorization</b>
State of AppFlow HTTP Authorization header logging

<b>httpVia</b>
State of AppFlow HTTP Via header logging

<b>httpXForwardedFor</b>
State of AppFlow HTTP X-Forwarded-For header logging

<b>httpLocation</b>
State of AppFlow HTTP Location header logging

<b>httpSetCookie</b>
State of AppFlow HTTP Setcookie header logging

<b>httpSetCookie2</b>
State of AppFlow HTTP Setcookie2 header logging

<b>connectionChaining</b>
State of connection-chaining feature

<b>httpDomain</b>
State of AppFlow HTTP Domain name logging

<b>skipCacheRedirectionHttpTransaction</b>
Skip Cache http transaction. This HTTP transaction is specific to Cache Redirection module. In Case of Cache Miss there will be another HTTP transaction initiated by the cache server.

<b>identifierName</b>
State of AppFlow Stream Identifier Name logging

<b>identifierSessionName</b>
State of AppFlow Stream Identifier Session Name logging

<b>observationDomainId</b>
An observation domain groups a set of NetScalers based on deployment: cluster, HA etc. A unique Observation Domain ID is required to be assigned to each such group.

<b>observationDomainName</b>
Name of the Observation Domain defined by the observation domain ID.

<b>builtin</b>
Flag to determine if the appflow param is built-in or not



