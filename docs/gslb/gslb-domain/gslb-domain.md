#gslb domain

The following operations can be performed on "gslb domain":


[show](#show-gslb-domain) | [stat](#stat-gslb-domain)

##show gslb domain

Displays the bounded attributes of the domain.


##Synopsys

show gslb domain [&lt;name>]


##Arguments

<b>name</b>
Name of the Domain



##Outputs

<b>serviceType</b>
The type GSLB service

<b>state</b>
The state of the vserver

<b>dnsRecordType</b>
The IP type for this GSLB vserver.

<b>stateChangeTimeSec</b>
Time since last state change

<b>lbMethod</b>
The load balancing method set for the virtual server

<b>backupLBMethod</b>
Indicates the backup method in case the primary fails

<b>persistenceType</b>
Indicates if persistence is set on the gslb vserver

<b>persistenceId</b>
Persistence id of the gslb vserver

<b>serviceName</b>
The service name.

<b>vServerName</b>

<b>siteName</b>
Name of the site to which the service belongs.

<b>cip</b>
Indicates if Client IP option is enabled

<b>sitePersistence</b>
Indicates the type of cookie persistence set

<b>sitePrefix</b>
The site prefix string.

<b>gslbthreshold</b>
The threshold value of the service

<b>httpRequest</b>
HTTP request to the backend server

<b>ipTunnel</b>
The state of the monitor for tunneled devices.

<b>customHeaders</b>
The string that is sent to the service. Applicable to HTTP ,HTTP-ECV and RTSP monitor types.

<b>respCode</b>
The response codes.

<b>monitorName</b>
Monitor name

<b>netmask</b>
Netmask

<b>v6netmasklen</b>
Number of bits to consider, in an IPv6 source IP address, for creating the hash that is required by the SOURCEIPHASH load balancing method.

<b>EDR</b>
Send clients an empty DNS response when the GSLB virtual server is DOWN.

<b>MIR</b>

<b>dynamicWeight</b>
Dynamic weight method of the vserver

<b>persistMask</b>
The optional IPv4 network mask applied to IPv4 addresses to establish source IP address based persistence.

<b>v6persistmasklen</b>
Number of bits to consider in an IPv6 source IP address when creating source IP address based persistence sessions.

<b>IPAddress</b>
The Ip address of the service

<b>port</b>
Port Number

<b>weight</b>
weight assigned

<b>dynamicConfWt</b>
dynamic weight

<b>cumulativeWeight</b>
cumlative weight

<b>svrEffGslbState</b>
GSLB server state

<b>cnameEntry</b>
The cname of the gslb service

<b>monState</b>
Monitor state

<b>monitorTotalProbes</b>
Total monitor probes

<b>monitorTotalFailedProbes</b>
Total probes failed

<b>monitorCurrentFailedProbes</b>
Total number of current failed probes

<b>monStatCode</b>
The code indicating the monitor response.

<b>monStatParam1</b>
First parameter for use with message code.

<b>monStatParam2</b>
Second parameter for use with message code.

<b>monStatParam3</b>
Third parameter for use with message code.

<b>responseTime</b>
Response time of this monitor.

<b>lastresponse</b>
The string form of monstatcode.

<b>stateflag</b>
stateflag

<b>devno</b>

<b>count</b>



##stat gslb domain

Displays the statistics associated with a global server load balancing (GSLB) domain.


##Synopsys

stat gslb domain [&lt;name>  [-dnsRecordType &lt;dnsRecordType>]] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the GSLB domain for which to display statistics. If you do not specify a name, statistics are shown for all configured GSLB
 domains.

<b>dnsRecordType</b>

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

<b>domainHits (Hits)</b>
Total number of DNS queries received.

<b>Dns Record Type (Rec_Type)</b>
Type of DNS record returned



##Related Commands

<ul><li><a href="../../../-gslb/-gslb">stat gslb site</a></li><li><a href="../../../tat-gslb-se/tat-gslb-se">stat gslb service</a></li><li><a href="../../../tat-gslb-vs/tat-gslb-vs">stat gslb vserver</a></li></ul>



