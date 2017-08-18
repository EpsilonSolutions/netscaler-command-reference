#lsn rtspalgsession

The following operations can be performed on "lsn rtspalgsession":


[show](#show-lsn-rtspalgsession) | [flush](#flush-lsn-rtspalgsession)

##show lsn rtspalgsession

Show LSN RTSP session.


##Synopsys

show lsn rtspalgsession [&lt;sessionId>]


##Arguments

<b>sessionId</b>
Session ID for the RTSP call.



##Outputs

<b>callflags</b>
Flags for the call entry.

<b>xlatip</b>
XLAT IP Address if its XLAT session.

<b>callrefcount</b>
Reference count for the call entry.

<b>calltimer</b>
Timer for the call entry.

<b>channelip</b>
IP address of the channel.

<b>channelnatip</b>
Natted IP address of the channel.

<b>channelport</b>
port for the channel.

<b>channelnatport</b>
Natted port for the channel.

<b>channelprotocol</b>
Channel transport protocol.

<b>channelflags</b>
Flags for the call entry.

<b>channeltimeout</b>
Timeout for the channel.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show lsn rtspalgsession

##flush lsn rtspalgsession

Flush RTSP session.


##Synopsys

flush lsn rtspalgsession &lt;sessionId>


##Arguments

<b>sessionId</b>
Session ID for the RTSP call.



##Example

flush lsn rtspalgsession

