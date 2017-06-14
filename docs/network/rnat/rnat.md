#rnat

The following operations can be performed on "rnat":


[clear](#clear-rnat) | [set](#set-rnat) | [unset](#unset-rnat) | [stat](#stat-rnat) | [show](#show-rnat)

##clear rnat

Removes an RNAT rule from the NetScaler appliance.


##Synopsys

clear rnat ((&lt;network>  [&lt;netmask>]) | (&lt;aclname>  [-redirectPort])) [-natIP &lt;ip_addr|*>@ ...] [-td &lt;positive_integer>]


##Arguments

<b>network</b>
The network address defined for the RNAT entry.

<b>netmask</b>
The subnet mask for the network address.

<b>aclname</b>
An extended ACL defined for the RNAT entry.

<b>redirectPort</b>
The port number to which the packets are redirected.

<b>natIP</b>
The NAT IP address defined for the RNAT entry.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.
Minimum value: 0
Maximum value: 4094



##set rnat

Modifies parameters of an RNAT rule.


##Synopsys

set rnat ((&lt;network>  [&lt;netmask>]  [-natIP &lt;ip_addr|*>@ ...]) | (&lt;aclname>  [-redirectPort &lt;port>]  [-natIP &lt;ip_addr|*>@ ...])) [-td &lt;positive_integer>] [-srcippersistency ( ENABLED | DISABLED )]


##Arguments

<b>network</b>
IPv4 network address on whose traffic you want the NetScaler appliance to do RNAT processing.

<b>aclname</b>
Name of any configured extended ACL whose action is ALLOW. The condition specified in the extended ACL rule isused as the condition for the RNAT6 rule.

<b>srcippersistency</b>
Enables the NetScaler appliance to use the same NAT IP address for all RNAT sessions initiated from a particular server.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##unset rnat

Use this command to modify the parameters of  configured Reverse NAT on the system..Refer to the set  rnat command for meanings of the arguments.


##Synopsys

unset rnat ((&lt;network>  [&lt;netmask>]) | (&lt;aclname>  [-redirectPort])) [-td &lt;positive_integer>] [-natIP &lt;ip_addr|*>@ ...] [-srcippersistency]


##stat rnat

Display statistics for rnat sessions.


##Synopsys

stat rnat [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>Bytes Received (rnatRxBytes)</b>
Bytes received during RNAT sessions.

<b>Bytes Sent (rnatTxBytes)</b>
Bytes sent during RNAT sessions.

<b>Packets Received (rnatRxPkts)</b>
Packets received during RNAT sessions.

<b>Packets Sent (rnatTxPkts)</b>
Packets sent during RNAT sessions.

<b>Syn Sent (rnatTxSyn)</b>
Requests for connections sent during RNAT sessions.

<b>Current RNAT sessions (rnatSessions)</b>
Currently active RNAT sessions.



##Example

stat rnat

##show rnat

Display the Reverse NAT configuration.


##Synopsys

show rnat


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>network</b>
The network address.

<b>netmask</b>
Subnet mask associated with the network address.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>natIP</b>
Nat IP Address.

<b>aclname</b>
Name of any configured extended ACL whose action is ALLOW. The condition specified in the extended ACL rule isused as the condition for the RNAT6 rule.

<b>redirectPort</b>
The port number to which the packets are redirected.

<b>srcippersistency</b>
Enables the NetScaler appliance to use the same NAT IP address for all RNAT sessions initiated from a particular server.

<b>cfgflags</b>
This contains the flags for RNAT in DB

<b>devno</b>

<b>count</b>

<b>stateflag</b>



