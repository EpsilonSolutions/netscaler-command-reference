#lsn sipalgcall

The following operations can be performed on "lsn sipalgcall":


[show](#show-lsn-sipalgcall) | [flush](#flush-lsn-sipalgcall)

##show lsn sipalgcall

Show LSN sipalgcall.


##Synopsys

show lsn sipalgcall [-callid &lt;string>]


##Arguments

<b>callid</b>
Call ID for the SIP call.



##Outputs

<b>callflags</b>
Flags for the call entry.

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

show lsn sipalgcall

##flush lsn sipalgcall

Flush LSN Session.


##Synopsys

flush lsn sipalgcall [-callid &lt;string>]


##Arguments

<b>callid</b>
Call ID for the SIP call.



##Example

flush lsn session

