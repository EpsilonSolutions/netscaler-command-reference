#lb sipParameters

The following operations can be performed on "lb sipParameters":


[set](#set-lb-sipparameters) | [unset](#unset-lb-sipparameters) | [show](#show-lb-sipparameters)

##set lb sipParameters

Modifies the specified global SIP parameters.


##Synopsys

set lb sipParameters [-rnatSrcPort &lt;port>] [-rnatDstPort &lt;port>] [-retryDur &lt;integer>] [-addRportVip ( ENABLED | DISABLED )] [-sip503RateThreshold &lt;positive_integer>] [-rnatsecuresrcport &lt;port|*>] [-rnatsecuredstport &lt;port|*>]


##Arguments

<b>rnatSrcPort</b>
Port number with which to match the source port in server-initiated SIP traffic. The rport parameter is added, without a value, to SIP packets that have a matching source port number, and CALL-ID based persistence is implemented for the responses received by the virtual server. Default value: 0

<b>rnatDstPort</b>
Port number with which to match the destination port in server-initiated SIP traffic. The rport parameter is added, without a value, to SIP packets that have a matching destination port number, and CALL-ID based persistence is implemented for the responses received by the virtual server. Default value: 0

<b>retryDur</b>
Time, in seconds, for which a client must wait before initiating a connection after receiving a 503 Service Unavailable response from the SIP server. The time value is sent in the "Retry-After" header in the 503 response. Default value: 120 Minimum value: 1

<b>addRportVip</b>
Add the rport parameter to the VIA headers of SIP requests that virtual servers receive from clients or servers. Possible values: ENABLED, DISABLED Default value: ENABLED

<b>sip503RateThreshold</b>
Maximum number of 503 Service Unavailable responses to generate, once every 10 milliseconds, when a SIP virtual server becomes unavailable. Default value: 100 Minimum value: 0

<b>rnatsecuresrcport</b>
Port number with which to match the source port in server-initiated SIP over SSL traffic. The rport parameter is added, without a value, to SIP packets that have a matching source port number, and CALL-ID based persistence is implemented for the responses received by the virtual server. Default value: 0

<b>rnatsecuredstport</b>
Port number with which to match the destination port in server-initiated SIP over SSL traffic. The rport parameter is added, without a value, to SIP packets that have a matching destination port number, and CALL-ID based persistence is implemented for the responses received by the virtual server. Default value: 0



##Example

set sip parameter

##unset lb sipParameters

Use this command to remove lb sipParameters settings.Refer to the set lb sipParameters command for meanings of the arguments.


##Synopsys

unset lb sipParameters [-rnatSrcPort] [-rnatDstPort] [-retryDur] [-addRportVip] [-sip503RateThreshold] [-rnatsecuresrcport] [-rnatsecuredstport]


##show lb sipParameters

Displays the global SIP parameters.


##Synopsys

show lb sipParameters


##Outputs

<b>rnatSrcPort</b>
Port number with which to match the source port in server-initiated SIP traffic. The rport parameter is added, without a value, to SIP packets that have a matching source port number, and CALL-ID based persistence is implemented for the responses received by the virtual server.

<b>rnatDstPort</b>
Port number with which to match the destination port in server-initiated SIP traffic. The rport parameter is added, without a value, to SIP packets that have a matching destination port number, and CALL-ID based persistence is implemented for the responses received by the virtual server.

<b>retryDur</b>
Time, in seconds, for which a client must wait before initiating a connection after receiving a 503 Service Unavailable response from the SIP server. The time value is sent in the "Retry-After" header in the 503 response.

<b>addRportVip</b>
Add the rport parameter to the VIA headers of SIP requests that virtual servers receive from clients or servers.

<b>sip503RateThreshold</b>
Maximum number of 503 Service Unavailable responses to generate, once every 10 milliseconds, when a SIP virtual server becomes unavailable.

<b>rnatsecuresrcport</b>
Port number with which to match the source port in server-initiated SIP over SSL traffic. The rport parameter is added, without a value, to SIP packets that have a matching source port number, and CALL-ID based persistence is implemented for the responses received by the virtual server.

<b>rnatsecuredstport</b>
Port number with which to match the destination port in server-initiated SIP over SSL traffic. The rport parameter is added, without a value, to SIP packets that have a matching destination port number, and CALL-ID based persistence is implemented for the responses received by the virtual server.



##Example

show sip parameter

