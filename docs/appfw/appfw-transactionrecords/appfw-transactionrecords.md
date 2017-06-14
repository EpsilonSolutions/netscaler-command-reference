#appfw transactionRecords

The following operations can be performed on "appfw transactionRecords":


##show appfw transactionRecords

Display an application firewall transaction record.


##Synopsys

show appfw transactionRecords


##Outputs

<b>httpTransactionId</b>
The http transaction identifier.

<b>packetEngineId</b>
The packet engine identifier.

<b>AppFwSessionId</b>
The session identifier set by the Application Firewall to track the user session.

<b>profileName</b>
Application Firewall profile name.

<b>url</b>
Request URL

<b>clientip</b>
The IP address of client.

<b>destIP</b>
The IP address of destination.

<b>startTime</b>
Conveys time at which request processing started.

<b>endTime</b>
Conveys time at which request processing end.

<b>requestContentLength</b>
The content length of request.

<b>requestYields</b>
The number of times yielded during request processing to send heart beat packets.

<b>requestMaxProcessingTime</b>
The maximum processing time across yields during request processing.

<b>responseContentLength</b>
The content length of response.

<b>responseYields</b>
The number of times yielded during response processing to send heart beat packets.

<b>responseMaxProcessingTime</b>
The maximum processing time across yields during response processing.

<b>flag</b>
Record flags.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



