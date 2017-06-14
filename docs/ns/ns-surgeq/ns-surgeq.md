#ns surgeQ

The following operations can be performed on "ns surgeQ":


##flush ns surgeQ

Flushes the connections that are waiting in SurgeQ. SurgeQ contains the client connections waiting for a server connection.


##Synopsys

flush ns surgeQ [-name &lt;string>  [-serverName &lt;string>  &lt;port>]]


##Arguments

<b>name</b>
Name of a virtual server, service or service group for which the SurgeQ must be flushed.

<b>serverName</b>
Name of a service group member. This argument is needed when you want to flush the SurgeQ of a service group.



##Example

To flush the surgeQ system wide, use the command: flush ns SurgeQ.To flush the surgeQ specific to a vserver/service/svcgrp use the command: flush ns SurgeQ -name &lt;name&gt;To flush the surgeQ  specific to a svcgrp member, use the command: flush ns surgeQ [-name &lt;string&gt;  [-serverName &lt;string&gt;  &lt;port&gt;]]

