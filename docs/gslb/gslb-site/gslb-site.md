#gslb site

The following operations can be performed on "gslb site":


[add](#add-gslb-site) | [rm](#rm-gslb-site) | [set](#set-gslb-site) | [unset](#unset-gslb-site) | [show](#show-gslb-site) | [stat](#stat-gslb-site)

##add gslb site

Creates a global server load balancing site.


##Synopsys

add gslb site &lt;siteName> [&lt;siteType>] &lt;siteIPAddress> [-publicIP &lt;ip_addr|ipv6_addr|*>] [-metricExchange ( ENABLED | DISABLED )] [-nwMetricExchange ( ENABLED | DISABLED )] [-sessionExchange ( ENABLED | DISABLED )] [-triggerMonitor &lt;triggerMonitor>] [-parentSite &lt;string>] [-clip &lt;ip_addr|ipv6_addr|*>  [&lt;publicCLIP>]]


##Arguments

<b>siteName</b>
Name for the GSLB site. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the virtual server is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my gslbsite" or 'my gslbsite').

<b>siteType</b>
Type of site to create. If the type is not specified, the appliance automatically detects and sets the type on the basis of the IP address being assigned to the site. If the specified site IP address is owned by the appliance (for example, a MIP address or SNIP address), the site is a local site. Otherwise, it is a remote site.
Possible values: REMOTE, LOCAL
Default value: NS_NORMAL

<b>siteIPAddress</b>
IP address for the GSLB site. The GSLB site uses this IP address to communicate with other GSLB sites. For a local site, use any IP address that is owned by the appliance (for example, a SNIP or MIP address, or the IP address of the ADNS service).

<b>publicIP</b>
Public IP address for the local site. Required only if the appliance is deployed in a private address space and the site has a public IP address hosted on an external firewall or a NAT device.

<b>metricExchange</b>
Exchange metrics with other sites. Metrics are exchanged by using Metric Exchange Protocol (MEP). The appliances in the GSLB setup exchange health information once every second. 
If you disable metrics exchange, you can use only static load balancing methods (such as round robin, static proximity, or the hash-based methods), and if you disable metrics exchange when a dynamic load balancing method (such as least connection) is in operation, the appliance falls back to round robin. Also, if you disable metrics exchange, you must use a monitor to determine the state of GSLB services. Otherwise, the service is marked as DOWN.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>nwMetricExchange</b>
Exchange, with other GSLB sites, network metrics such as round-trip time (RTT), learned from communications with various local DNS (LDNS) servers used by clients. RTT information is used in the dynamic RTT load balancing method, and is exchanged every 5 seconds.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessionExchange</b>
Exchange persistent session entries with other GSLB sites every five seconds.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>triggerMonitor</b>
Specify the conditions under which the GSLB service must be monitored by a monitor, if one is bound. Available settings function as follows:
* ALWAYS - Monitor the GSLB service at all times.
* MEPDOWN - Monitor the GSLB service only when the exchange of metrics through the Metrics Exchange Protocol (MEP) is disabled.
MEPDOWN_SVCDOWN - Monitor the service in either of the following situations: 
* The exchange of metrics through MEP is disabled.
* The exchange of metrics through MEP is enabled but the status of the service, learned through metrics exchange, is DOWN.
Possible values: ALWAYS, MEPDOWN, MEPDOWN_SVCDOWN
Default value: NSGSLB_TRIGMON_ALWAYS

<b>parentSite</b>
Parent site of the GSLB site, in a parent-child topology.

<b>clip</b>
Cluster IP used to connect to remote cluster site for GSLB autosync



##Example

add site new_york  LOCAL  192.168.100.12 -publicIP  65.200.211.139

##rm gslb site

Removes a global server load balancing (GSLB) site and all its constituent GSLB services.


##Synopsys

rm gslb site &lt;siteName>


##Arguments

<b>siteName</b>
Name of the GSLB site to remove.



##Example

rm gslb site new_york

##set gslb site

Modifies the specified parameters of a global server load balancing (GSLB) site.


##Synopsys

set gslb site &lt;siteName> [-metricExchange ( ENABLED | DISABLED )] [-nwMetricExchange ( ENABLED | DISABLED )] [-sessionExchange ( ENABLED | DISABLED )] [-triggerMonitor &lt;triggerMonitor>]


##Arguments

<b>siteName</b>
Name of the GSLB site.

<b>metricExchange</b>
Exchange metrics with other sites. Metrics are exchanged by using Metric Exchange Protocol (MEP). The appliances in the GSLB setup exchange health information once every second. 
If you disable metrics exchange, you can use only static load balancing methods (such as round robin, static proximity, or the hash-based methods), and if you disable metrics exchange when a dynamic load balancing method (such as least connection) is in operation, the appliance falls back to round robin. Also, if you disable metrics exchange, you must use a monitor to determine the state of GSLB services. Otherwise, the service is marked as DOWN.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>nwMetricExchange</b>
Exchange, with other GSLB sites, network metrics such as round-trip time (RTT), learned from communications with various local DNS (LDNS) servers used by clients. RTT information is used in the dynamic RTT load balancing method, and is exchanged every 5 seconds.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>sessionExchange</b>
Exchange persistent session entries with other GSLB sites every five seconds.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>triggerMonitor</b>
Specify the conditions under which the GSLB service must be monitored by a monitor, if one is bound. Available settings function as follows:
* ALWAYS - Monitor the GSLB service at all times.
* MEPDOWN - Monitor the GSLB service only when the exchange of metrics through the Metrics Exchange Protocol (MEP) is disabled.
MEPDOWN_SVCDOWN - Monitor the service in either of the following situations: 
* The exchange of metrics through MEP is disabled.
* The exchange of metrics through MEP is enabled but the status of the service, learned through metrics exchange, is DOWN.
Possible values: ALWAYS, MEPDOWN, MEPDOWN_SVCDOWN
Default value: NSGSLB_TRIGMON_ALWAYS



##Example

set gslb site new_york - metricExchange DISABLED

##unset gslb site

Use this command to remove gslb site settings.Refer to the set gslb site command for meanings of the arguments.


##Synopsys

unset gslb site &lt;siteName> [-metricExchange] [-nwMetricExchange] [-sessionExchange] [-triggerMonitor]


##show gslb site

Displays the parameters of all the GSLB sites configured on the appliance, or the parameters of the specified GSLB site.


##Synopsys

show gslb site [&lt;siteName>]show gslb site stats - alias for 'stat gslb site'


##Arguments

<b>siteName</b>
Name of the GSLB site. If you specify a site name, details of all the site's constituent services are also displayed.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>siteType</b>
Specifies whether the site is LOCAL or REMOTE.

<b>siteIPAddress</b>
The IP address of the site.

<b>publicIP</b>
The Public IP of the gslb site.

<b>metricExchange</b>
Exchange metrics with other sites. Metrics are exchanged by using Metric Exchange Protocol (MEP). The appliances in the GSLB setup exchange health information once every second. 
If you disable metrics exchange, you can use only static load balancing methods (such as round robin, static proximity, or the hash-based methods), and if you disable metrics exchange when a dynamic load balancing method (such as least connection) is in operation, the appliance falls back to round robin. Also, if you disable metrics exchange, you must use a monitor to determine the state of GSLB services. Otherwise, the service is marked as DOWN.

<b>serviceName</b>
Service name.

<b>IPAddress</b>
IP Address of the gslb service.

<b>port</b>
Port number of the gslb service.

<b>state</b>
State of the gslb service.

<b>status</b>
Current metric exchange status.

<b>persistenceMEPStatus</b>
Network metric and persistence exchange MEP connection status

<b>serviceType</b>
Service type.

<b>nwMetricExchange</b>
Specifies whether the exchange of network metrics like RTT is enabled or disabled.

<b>sessionExchange</b>
Specifies whether the exchange of persistence session entries is enabled or disabled.

<b>triggerMonitor</b>
Specify the conditions under which the GSLB service must be monitored by a monitor, if one is bound. Available settings function as follows:
* ALWAYS - Monitor the GSLB service at all times.
* MEPDOWN - Monitor the GSLB service only when the exchange of metrics through the Metrics Exchange Protocol (MEP) is disabled.
MEPDOWN_SVCDOWN - Monitor the service in either of the following situations: 
* The exchange of metrics through MEP is disabled.
* The exchange of metrics through MEP is enabled but the status of the service, learned through metrics exchange, is DOWN.

<b>parentSite</b>
Parent site of the GSLB site, in a parent-child topology.

<b>cnameEntry</b>
The cname of the gslb service.

<b>stateflag</b>
stateflag

<b>version</b>
will be true if the remote site's version is ncore compatible with the local site.(>= 9.2)

<b>clip</b>
Cluster IP used to connect to remote cluster site for GSLB autosync

<b>publicCLIP</b>
Public cluster IP used to connect to remote cluster site for GSLB autosync if the remote cluster is behind a NAT

<b>devno</b>

<b>count</b>



##Example

show site new_york

##stat gslb site

Displays statistics for a GSLB site.


##Synopsys

stat gslb site [&lt;siteName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>siteName</b>
Name of the GSLB site for which to display detailed statistics. If a name is not specified, basic information about all GSLB sites is displayed.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Gslb Site Public IP address (Public IP)</b>
The public IP address of this GSLB site.

<b>Gslb Site private IP address (Private IP)</b>
The private IP address of this GSLB site.

<b>Metric Exchange State (MEPstate)</b>
Indicates the status of the Metric Exchange Policy at this GSLB site.

<b>Persistence Exchange (PersMEP)</b>
Indicates whether Persistence entries exchange is enabled or disabled at this GSLB site.

<b>Network Metric Exchange (NwMEP)</b>
Indicates whether network metric exchange is enabled or disabled at this GSLB site.

<b>Metric Exchange (MEP)</b>
Indicates whether metric exchange is enabled or disabled at this GSLB site.

<b>GSLB Site type (sitetype)</b>
Indicates whether this GSLB site is local or remote.

<b>Gslb Site public IP address (Public IP)</b>
The public IP address of this GSLB site.

<b>Site Metric Metric Exchange State (SiteMetricMEPstate)</b>
Indicates the status of the site metric Metric Exchange connection at this GSLB site.

<b>Netowrk Metric Metric Exchange State (NwMetricMEPstate)</b>
Indicates the status of the network metric Metric Exchange connection at this GSLB site.

<b>Request bytes (Reqb)</b>
Total number of request bytes received by the virtual servers represented by all GSLB services associated with this GSLB site.

<b>Response bytes (Rspb)</b>
Number of response bytes received by the virtual servers represented by all GSLB services associated with this GSLB site.

<b>Requests (Req)</b>
Total number of requests received by the virtual servers represented by all GSLB services associated with this GSLB site.

<b>Responses (Rsp)</b>
Number of responses received by the virtual servers represented by all GSLB services associated with this GSLB site.

<b>Current client connections (ClntConn)</b>
Number of current client connections to the virtual servers represented by all GSLB services associated with this GSLB site.

<b>Current server connections (SvrConn)</b>
Number of current connections to the real servers behind the virtual servers represented by all GSLB services associated with this GSLB site.



##Related Commands

<ul><li><a href="../../../tat-gslb-se/tat-gslb-se">stat gslb service</a></li><li><a href="../../../tat-gslb-vs/tat-gslb-vs">stat gslb vserver</a></li><li><a href="../../../at-gslb-d/at-gslb-d">stat gslb domain</a></li></ul>



