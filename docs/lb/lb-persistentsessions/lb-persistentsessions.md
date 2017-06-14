#lb persistentSessions

The following operations can be performed on "lb persistentSessions":


[show](#show-lb-persistentsessions) | [clear](#clear-lb-persistentsessions)

##show lb persistentSessions

Get all vserver persistent sessions


##Synopsys

show lb persistentSessions [&lt;vServer>]


##Arguments

<b>vServer</b>
The name of the virtual server.

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>type</b>
Type of Persistence.

<b>typestring</b>
Type of Persistence as String.

<b>srcIP</b>
SOURCE IP.

<b>srcIPv6</b>
SOURCE IPv6 ADDRESS.

<b>destIP</b>
DESTINATION IP.

<b>destIPv6</b>
DESTINATION IPv6 ADDRESS.

<b>flags</b>
IPv6 FLAGS.

<b>destPort</b>
Destination port.

<b>vServerName</b>
Virtual server name.

<b>timeout</b>
Persistent Session timeout.

<b>referenceCount</b>
Reference Count.

<b>sipCallID</b>
SIP CALLID.NOTE: This attribute is deprecated.Replaced by "persistenceParam" field

<b>persistenceParam</b>
Specific persistence information . Callid in case of SIP_CALLID persistence entry , RTSP session id in case of RTSP_SESSIONID persistence entry.

<b>cnamePersparam</b>
The cname that is selected incase of gslb service

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##clear lb persistentSessions

Use this command to clear/flush persistent sessions


##Synopsys

clear lb persistentSessions [&lt;vServer>] [-persistenceParameter &lt;string>]


##Arguments

<b>vServer</b>
The name of the LB vserver whose persistence sessions are to be flushed. If not specified, all persistence sessions will be flushed .

<b>persistenceParameter</b>
The persistence parameter whose persistence sessions are to be flushed.



