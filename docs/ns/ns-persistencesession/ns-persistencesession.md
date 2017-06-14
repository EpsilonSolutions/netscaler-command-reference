#ns persistencesession

The following operations can be performed on "ns persistencesession":


[show](#show-ns-persistencesession) | [clear](#clear-ns-persistencesession)

##show ns persistencesession

Get all Sessions corresponding to a Vserver NOTE: This command is deprecated.Moved to LB command group


##Synopsys




##Arguments

<b>name</b>
The name of the virtual server.

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>type</b>
The netmask of this IP.

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

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show ns persistencesession vipname

##clear ns persistencesession

Use this command to clear/flush persistence sessions NOTE: This command is deprecated.Moved to LB command group


##Synopsys




##Arguments

<b>vServer</b>
The name of the LB vserver whose persistence sessions are to be flushed. If not specified, all persistence sessions will be flushed .



##Example

clear persistenceSessions -vserver vip1

