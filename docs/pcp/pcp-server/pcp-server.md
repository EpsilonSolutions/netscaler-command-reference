#pcp server

The following operations can be performed on "pcp server":


[add](#add-pcp-server) | [rm](#rm-pcp-server) | [set](#set-pcp-server) | [unset](#unset-pcp-server) | [show](#show-pcp-server) | [stat](#stat-pcp-server)

##add pcp server

Creates a pcp server.


##Synopsys

add pcp server &lt;name> &lt;IPAddress> [-port &lt;port|*>] [-pcpProfile &lt;string>]


##Arguments

<b>name</b>
Name for the PCP server. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my pcpServer" or my pcpServer).

<b>IPAddress</b>
The IP address of the PCP server.

<b>port</b>
Port number for the PCP server.
Default value: 5351

<b>pcpProfile</b>
pcp profile name



##Example

add pcp server pcp_svr 10.102.1.10

##rm pcp server

Removes a  pcp server from the NetScaler appliance.


##Synopsys

rm pcp server &lt;name> ...


##Arguments

<b>name</b>
Name of the pcp server.



##Example

rm pcp server pcp_svr

##set pcp server

Modifies the specified parameters of a  pcp server.


##Synopsys

set pcp server &lt;name> [-port &lt;port|*>] [-pcpProfile &lt;string>]


##Arguments

<b>name</b>
Name of the pcp server.

<b>port</b>
Port number for the PCP server.
Default value: 5351

<b>pcpProfile</b>
pcp profile name



##Example

set pcp server pcp_svr  -port  5000 -profile profile_1

##unset pcp server

Use this command to remove pcp server settings.Refer to the set pcp server command for meanings of the arguments.


##Synopsys

unset pcp server &lt;name> [-port] [-pcpProfile]


##show pcp server

Displays the  pcp server information.


##Synopsys

show pcp server [&lt;name>]


##Arguments

<b>name</b>
Name of the pcp server.



##Outputs

<b>IPAddress</b>
The IP address of the PCP server.

<b>port</b>
Port number for the PCP server.

<b>pcpProfile</b>
pcp profile name

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##stat pcp server

DIsplay pcp statistics.


##Synopsys

stat pcp server [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
PCP Statistics per Server

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Total PCP Requests received (requests)</b>
PCP Request received.

<b>Total Responses sent (responses)</b>
Number PCP responces sent.

<b>Total PCP MAP Rquests rcvd (peerReq)</b>
PCP MAP Requests received.

<b>Total PCP PEER Requests rcvd (mapRqsts)</b>
PCP PEER Requests received.

<b>Total requests with errors (errInReq)</b>
total PCP request with error.

<b>Total responses with errors (errInRes)</b>
Total PCP responses with errors.

<b>Total unsupported version request (unsuppVers)</b>
PCP request with unsupported version.

<b>Total Malformed Requests (malformedReq)</b>
total PCP request having malformed PCP packets.

<b>Total Unsupported OPCODES (unsupOpcode)</b>
total Unsupproted OPCODES received Requests.

<b>Total Unsupported OPTIONS (unsupOption)</b>
total Unsupproted OPTIONS received in requests.

<b>Total malformed OPTIONS (malformedOption)</b>
total malformed OPTIONS received in requests.

<b>Total Network Failures (ntwrkFail)</b>
Total Network Failures.

<b>Total No resources reponse (noResource)</b>
no resources

<b>Total Unsupported Protocols requests (unsupProto)</b>
Total Unsupported Protocols requests.

<b>Total User Ex Qouta (userExqouta)</b>
Total user ex quota.

<b>Total cannot provide extrnl resp (noExternal)</b>
Total responses with opcode can not provide external.

<b>Total address mismatch rqsts (addrMismatch)</b>
Total address mismatch.

<b>Total Excess Remote Peers (excessPeers)</b>
Total responses with opcode excessive remote peers.



