#ns

The following operations can be performed on "ns":


[config](#config-ns) | [stat](#stat-ns)

##config ns

Displays a menu to configure the basic parameters of a NetScaler appliance.Note: The appliance must be rebooted for these changes to take effect.


##Synopsys

config ns


##stat ns

Displays generic statistics of the NetScaler appliance.


##Synopsys

stat ns [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

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

<b>Average CPU usage (%) (CPU)</b>
Average CPU utilization percentage. Not applicable for a single-CPU system.

<b>CPU usage (%) (CPU)</b>
CPU utilization percentage.

<b>Maximum memory(KB) Deprecated (MaxMem)</b>
Largest amount of memory the NetScaler can dedicate to caching, up to 50% of available memory. A 0 value disables caching, but the caching module continues to run.

<b>Delta compression ratio (DlCmpRt)</b>
Ratio of compressible data received to compressed data transmitted.If this ratio is one (uncmp:1.0) that means compression is disabled or we are not able to compress even a single compressible packet.

<b>Average CPU usage (CPU)</b>
Shows average CPU utilization percentage if more than 1 CPU is present.

<b>CPU usage (CPU)</b>
CPU utilization: percentage * 10.

<b>Memory usage (MemUsage)</b>
Percentage of memory utilization on NetScaler.

<b>Total HTTP compression ratio</b>
Ratio of total HTTP data received to total HTTP data transmitted.

<b>HTTP compression ratio</b>
Ratio of the compressible data received from the server to the compressed data sent to the client.

<b>Utilized memory(KB) (UtiMem)</b>
Amount of memory the integrated cache is currently using.

<b>Maximum memory active value(KB) (MaxMemActive)</b>
Currently active value of maximum memory

<b>Maximum memory(KB) (Max64Mem)</b>
Largest amount of memory the NetScaler can dedicate to caching, up to 50% of available memory. A 0 value disables caching, but the caching module continues to run.

<b>Origin bandwidth saved(%) (POrBan)</b>
Percentage of origin bandwidth saved, expressed as number of bytes served from the integrated cache divided by all bytes served. The assumption is that all compression is done in the NetScaler.

<b>Misses (TotMiss)</b>
Intercepted HTTP requests requiring fetches from origin server.

<b>Hits (TotHit)</b>
Responses served from the integrated cache. These responses match a policy with a CACHE action.

<b># SSL cards UP (SSLCardUP)</b>
Number of SSL cards that are UP. If the number of cards UP is lower than a threshold, a failover is initiated.

<b>InUse Memory (%) (MemUsage)</b>
Percentage of memory utilization on NetScaler.

<b>Memory usage (MB) (MemUseMB)</b>
Main memory currently in use, in megabytes.

<b>Management CPU usage (%) (CPU)</b>
Average Management CPU utilization percentage.

<b>Packet CPU usage (%) (CPU)</b>
Average CPU utilization percentage for all packet engines excluding management PE.

<b>Up since (Since)</b>
Time when the NetScaler appliance was last started.

<b>Last Transition time (TransTime)</b>
Time when the last master state transition occurred. You can use this statistic for debugging.

<b>System state (HAState)</b>
State of the HA node, based on its health, in a high availability setup. Possible values are: 
UP - Indicates that the node is accessible and can function as either a primary or secondary node.
DISABLED - Indicates that the high availability status of the node has been manually disabled. Synchronization and propagation cannot take place between the peer nodes.
INIT - Indicates that the node is in the process of becoming part of the high availability configuration. 
PARTIALFAIL - Indicates that one of the high availability monitored interfaces has failed because of a card or link failure. This state triggers a failover.
COMPLETEFAIL - Indicates that all the interfaces of the node are unusable, because the interfaces on which high availability monitoring is enabled are not connected or are manually disabled. This state triggers a failover.
DUMB - Indicates that the node is in listening mode. It does not participate in high availability transitions or transfer configuration from the peer node. This is a configured value, not a statistic.
PARTIALFAILSSL - Indicates that the SSL card has failed. This state triggers a failover.
ROUTEMONITORFAIL - Indicates that the route monitor has failed. This state triggers a failover.

<b>Master state (mastate)</b>
Indicates the high availability state of the node. Possible values are: 
STAYSECONDARY - Indicates that the selected node remains the secondary node in a high availability setup. In this case a forced failover does not change the state but, instead, returns an appropriate error message. This is a configured value and not a statistic.
PRIMARY - Indicates that the selected node is the primary node in a high availability setup. 
SECONDARY - Indicates that the selected node is the secondary node in a high availability setup. 
CLAIMING - Indicates that the secondary node is in the process of taking over as the primary node. This is the intermediate state in the transition of the secondary node to primary status. 
FORCE CHANGE - Indicates that the secondary node is forcibly changing its status to primary due to a forced failover issued on the secondary node.

<b># SSL cards present (SSLCards)</b>
Number of SSL crypto cards present on the NetScaler appliance.

<b>/flash Used (%) (disk0PerUsage)</b>
Used space in /flash partition of the disk, as a percentage. This is a critical counter.
				You can configure /flash Used (%) by using the Set snmp alarm DISK-USAGE-HIGH command.

<b>/var Used (%) (disk1PerUsage)</b>
Used space in /var partition of the disk, as a percentage. This is a critical counter. You can configure /var Used (%) by using the Set snmp alarm DISK-USAGE-HIGH command.

<b>/flash Available (MB) (disk0Avail)</b>
Available space in /flash partition of the hard disk.

<b>/var Available (MB) (disk1Avail)</b>
Available space in /var partition of the hard disk.

<b>Megabits received (RxMb)</b>
Number of megabytes received by the NetScaler appliance.

<b>Megabits transmitted (TxMb)</b>
Number of megabytes transmitted by the NetScaler appliance.

<b>All client connections (CltCx)</b>
Client connections, including connections in the Opening, Established, and Closing state.

<b>Established client connections (CltCxE)</b>
Current client connections in the Established state, which indicates that data transfer can occur between the NetScaler and the client.

<b>All server connections (SvrCx)</b>
Server connections, including connections in the Opening, Established, and Closing state.

<b>Established server connections (SvrCxE)</b>
Current server connections in the Established state, which indicates that data transfer can occur between the NetScaler and the server.

<b>Total requests (HTReqRx)</b>
Total number of HTTP requests received.

<b>Total responses (HTRspRx)</b>
Total number of HTTP responses sent.

<b>Request bytes received (HTReqbRx)</b>
Total number of bytes of HTTP request data received.

<b>Response bytes received (HTRspbRx)</b>
Total number of bytes of HTTP response data received.

<b>SSL transactions (SSLTrn)</b>
Number of SSL transactions on the NetScaler appliance.

<b>SSL session hits (SeHit)</b>
Number of SSL session reuse hits on the NetScaler appliance.

<b>requests (reqs)</b>
HTTP/HTTPS requests sent to your protected web servers via the Application Firewall.

<b>responses (resps)</b>
HTTP/HTTPS responses sent by your protected web servers via the Application Firewall.

<b>aborts</b>
Incomplete HTTP/HTTPS requests aborted by the client before the Application Firewall could finish processing them.

<b>redirects (redirect)</b>
HTTP/HTTPS requests redirected by the Application Firewall to a different Web page or web server. (HTTP 302)

<b>Misc. Counter 0 (misc0)</b>
Miscellaneous Counter 0.

<b>Misc. Counter 1 (misc1)</b>
Miscellaneous Counter 1.

<b>Management CPU usage (CPU)</b>
Management CPU utilization: percentage * 10.

<b>SSL crypto card status (SSLCardSt)</b>
Status of the SSL card(s). The value should be interpreted in binary form, with each set bit indicates a card as UP.

<b>304 hits (304Hit)</b>
Object not modified responses served from the cache. (Status code 304 served instead of the full response.)

<b>Non-304 hits (Non304Hit)</b>
Total number of full (non-304) responses served from the cache. A 304 status code indicates that a response has not been modified since the last time it was served

<b>sql hits (sqlHit)</b>
sql response served from cache

<b>Requests (CacReq)</b>
Total cache hits plus total cache misses.

<b>Compressed bytes transmitted</b>
Number of bytes the NetScaler sends to the client after compressing the response from the server.

<b>Compressible bytes received</b>
Number of bytes that can be compressed, which the NetScaler receives from the server. This gives the content length of the response that the NetScaler receives from server.

<b>Compressible bytes received (DlCmpRxB)</b>
Total number of delta-compressible bytes received by NetScaler.

<b>Compressed bytes transmitted (DlCmpTxB)</b>
Total number of delta-compressed bytes transmitted by NetScaler.



##Related Commands

<ul><li><a href="../../../ml#stat-ns-limitident/ml#stat-ns-limitident">stat ns limitIdentifier</a></li><li><a href="../../..//">stat ns acl</a></li><li><a href="../../..//">stat ns acl6</a></li><li><a href="../../../t-ns-simp/t-ns-simp">stat ns simpleacl</a></li><li><a href="../../../at-ns-simpl/at-ns-simpl">stat ns simpleacl6</a></li><li><a href="../../..//">stat ns pbr</a></li><li><a href="../../../s-m/s-m">stat ns memory</a></li><li><a href="../../..//">stat ns pbr6</a></li><li><a href="../../../#stat-ns-trafficd/#stat-ns-trafficd">stat ns trafficDomain</a></li><li><a href="../../../t-ns-part/t-ns-part">stat ns partition</a></li></ul>



