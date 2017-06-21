#lb monitor

The following operations can be performed on "lb monitor":


[add](#add-lb-monitor) | [rm](#rm-lb-monitor) | [set](#set-lb-monitor) | [unset](#unset-lb-monitor) | [enable](#enable-lb-monitor) | [disable](#disable-lb-monitor) | [bind](#bind-lb-monitor) | [unbind](#unbind-lb-monitor) | [show](#show-lb-monitor)

##add lb monitor

Creates a monitor that you can bind to load balancing services. The monitor periodically sends probes to those services to test their availability.


##Synopsys

add lb monitor &lt;monitorName> &lt;type> [-action &lt;action>] [-respCode &lt;int[-int]> ...] [-httpRequest &lt;string>] [-rtspRequest &lt;string>] [-customHeaders &lt;string>] [-maxForwards &lt;positive_integer>] [-sipMethod &lt;sipMethod>] [-sipURI &lt;string>] [-sipregURI &lt;string>] [-send &lt;string>] [-recv &lt;string>] [-query &lt;string>] [-queryType &lt;queryType>] [-scriptName &lt;string>] [-scriptArgs &lt;string>] [-dispatcherIP &lt;ip_addr>] [-dispatcherPort &lt;port>] [-userName &lt;string>] {-password } {-secondaryPassword } [-logonpointName &lt;string>] [-lasVersion &lt;string>] {-radKey } [-radNASid &lt;string>] [-radNASip &lt;ip_addr>] [-radAccountType &lt;positive_integer>] [-radFramedIP &lt;ip_addr>] [-radAPN &lt;string>] [-radMSISDN &lt;string>] [-radAccountSession &lt;string>] [-LRTM ( ENABLED | DISABLED )] [-deviation &lt;positive_integer> [&lt;units>]] [-interval &lt;integer> [&lt;units>]] [-resptimeout &lt;integer> [&lt;units>]] [-resptimeoutThresh &lt;positive_integer>] [-retries &lt;integer>] [-failureRetries &lt;integer>] [-alertRetries &lt;integer>] [-successRetries &lt;integer>] [-downTime &lt;integer> [&lt;units>]] [-destIP &lt;ip_addr|ipv6_addr>] [-destPort &lt;port>] [-state ( ENABLED | DISABLED )] [-reverse ( YES | NO )] [-transparent ( YES | NO )] [-ipTunnel ( YES | NO )] [-tos ( YES | NO )] [-tosId &lt;positive_integer>] [-secure ( YES | NO )] [-validateCred ( YES | NO )] [-domain &lt;string>] [-IPAddress &lt;ip_addr|ipv6_addr|*> ...] [-group &lt;string>] [-fileName &lt;string>] [-baseDN &lt;string>] [-bindDN &lt;string>] [-filter &lt;string>] [-attribute &lt;string>] [-database &lt;string> | -oracleSid &lt;string>] [-sqlQuery &lt;text>] [-evalRule &lt;expression>] [-mssqlProtocolVersion &lt;mssqlProtocolVersion>] [-snmpOID &lt;string>] [-snmpCommunity &lt;string>] [-snmpThreshold &lt;string>] [-snmpVersion ( V1 | V2 )] [-metricTable &lt;string>] [-application &lt;string>] [-sitePath &lt;string>] [-storename &lt;string>] [-storefrontacctservice ( YES | NO )] [-netProfile &lt;string>] [-originHost &lt;string>] [-originRealm &lt;string>] [-hostIPAddress &lt;ip_addr|ipv6_addr|*>] [-vendorId &lt;positive_integer>] [-productName &lt;string>] [-firmwareRevision &lt;positive_integer>] [-authApplicationId &lt;positive_integer> ...] [-acctApplicationId &lt;positive_integer> ...] [-inbandSecurityId ( NO_INBAND_SECURITY | TLS )] [-supportedVendorIds &lt;positive_integer> ...] [-vendorSpecificVendorId &lt;positive_integer> [-vendorSpecificAuthApplicationIds &lt;positive_integer> ...] [-vendorSpecificAcctApplicationIds &lt;positive_integer> ...]] [-kcdAccount &lt;string>] [-storedb ( ENABLED | DISABLED )] [-storefrontcheckbackendservices ( YES | NO )] [-trofscode &lt;positive_integer>] [-trofsstring &lt;string>]


##Arguments

<b>monitorName</b>
Name for the monitor. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my monitor" or 'my monitor').

<b>type</b>
Type of monitor that you want to create. Possible values: PING, TCP, HTTP, TCP-ECV, HTTP-ECV, UDP-ECV, DNS, FTP, LDNS-PING, LDNS-TCP, LDNS-DNS, RADIUS, USER, HTTP-INLINE, SIP-UDP, SIP-TCP, LOAD, FTP-EXTENDED, SMTP, SNMP, NNTP, MYSQL, MYSQL-ECV, MSSQL-ECV, ORACLE-ECV, LDAP, POP3, CITRIX-XML-SERVICE, CITRIX-WEB-INTERFACE, DNS-TCP, RTSP, ARP, CITRIX-AG, CITRIX-AAC-LOGINPAGE, CITRIX-AAC-LAS, CITRIX-XD-DDC, ND6, CITRIX-WI-EXTENDED, DIAMETER, RADIUS_ACCOUNTING, STOREFRONT, APPC, SMPP, CITRIX-XNC-ECV, CITRIX-XDM

<b>action</b>
Action to perform when the response to an inline monitor (a monitor of type HTTP-INLINE) indicates that the service is down. A service monitored by an inline monitor is considered DOWN if the response code is not one of the codes that have been specified for the Response Code parameter. Available settings function as follows: * NONE - Do not take any action. However, the show service command and the show lb monitor command indicate the total number of responses that were checked and the number of consecutive error responses received after the last successful probe. * LOG - Log the event in NSLOG or SYSLOG. * DOWN - Mark the service as being down, and then do not direct any traffic to the service until the configured down time has expired. Persistent connections to the service are terminated as soon as the service is marked as DOWN. Also, log the event in NSLOG or SYSLOG. Possible values: NONE, LOG, DOWN Default value: DOWN

<b>respCode</b>
Response codes for which to mark the service as UP. For any other response code, the action performed depends on the monitor type. HTTP monitors and RADIUS monitors mark the service as DOWN, while HTTP-INLINE monitors perform the action indicated by the Action parameter.

<b>httpRequest</b>
HTTP request to send to the server (for example, "HEAD /file.html").

<b>rtspRequest</b>
RTSP request to send to the server (for example, "OPTIONS *").

<b>customHeaders</b>
Custom header string to include in the monitoring probes.

<b>maxForwards</b>
Maximum number of hops that the SIP request used for monitoring can traverse to reach the server. Applicable only to monitors of type SIP-UDP. Default value: 1 Minimum value: 0 Maximum value: 255

<b>sipMethod</b>
SIP method to use for the query. Applicable only to monitors of type SIP-UDP. Possible values: OPTIONS, INVITE, REGISTER

<b>sipURI</b>
SIP URI string to send to the service (for example, sip:sip.test). Applicable only to monitors of type SIP-UDP.

<b>sipregURI</b>
SIP user to be registered. Applicable only if the monitor is of type SIP-UDP and the SIP Method parameter is set to REGISTER.

<b>send</b>
String to send to the service. Applicable to TCP-ECV, HTTP-ECV, and UDP-ECV monitors.

<b>recv</b>
String expected from the server for the service to be marked as UP. Applicable to TCP-ECV, HTTP-ECV, and UDP-ECV monitors.

<b>query</b>
Domain name to resolve as part of monitoring the DNS service (for example, example.com).

<b>queryType</b>
Type of DNS record for which to send monitoring queries. Set to Address for querying A records, AAAA for querying AAAA records, and Zone for querying the SOA record. Possible values: Address, Zone, AAAA

<b>scriptName</b>
Path and name of the script to execute. The script must be available on the NetScaler appliance, in the /nsconfig/monitors/ directory.

<b>scriptArgs</b>
String of arguments for the script. The string is copied verbatim into the request.

<b>dispatcherIP</b>
IP address of the dispatcher to which to send the probe.

<b>dispatcherPort</b>
Port number on which the dispatcher listens for the monitoring probe.

<b>userName</b>
User name with which to probe the RADIUS, NNTP, FTP, FTP-EXTENDED, MYSQL, MSSQL, POP3, CITRIX-AG, CITRIX-XD-DDC, CITRIX-WI-EXTENDED, CITRIX-XNC or CITRIX-XDM server.

<b>password</b>
Password that is required for logging on to the RADIUS, NNTP, FTP, FTP-EXTENDED, MYSQL, MSSQL, POP3, CITRIX-AG, CITRIX-XD-DDC, CITRIX-WI-EXTENDED, CITRIX-XNC-ECV or CITRIX-XDM server. Used in conjunction with the user name specified for the User Name parameter.

<b>secondaryPassword</b>
Secondary password that users might have to provide to log on to the Access Gateway server. Applicable to CITRIX-AG monitors.

<b>logonpointName</b>
Name of the logon point that is configured for the Citrix Access Gateway Advanced Access Control software. Required if you want to monitor the associated login page or Logon Agent. Applicable to CITRIX-AAC-LAS and CITRIX-AAC-LOGINPAGE monitors.

<b>lasVersion</b>
Version number of the Citrix Advanced Access Control Logon Agent. Required by the CITRIX-AAC-LAS monitor.

<b>radKey</b>
Authentication key (shared secret text string) for RADIUS clients and servers to exchange. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radNASid</b>
NAS-Identifier to send in the Access-Request packet. Applicable to monitors of type RADIUS.

<b>radNASip</b>
Network Access Server (NAS) IP address to use as the source IP address when monitoring a RADIUS server. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radAccountType</b>
Account Type to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING. Default value: 1 Minimum value: 0 Maximum value: 15

<b>radFramedIP</b>
Source ip with which the packet will go out . Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAPN</b>
Called Station Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radMSISDN</b>
Calling Stations Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAccountSession</b>
Account Session ID to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>LRTM</b>
Calculate the least response times for bound services. If this parameter is not enabled, the appliance does not learn the response times of the bound services. Also used for LRTM load balancing. Possible values: ENABLED, DISABLED

<b>deviation</b>
Time value added to the learned average response time in dynamic response time monitoring (DRTM). When a deviation is specified, the appliance learns the average response time of bound services and adds the deviation to the average. The final value is then continually adjusted to accommodate response time variations over time. Specified in milliseconds, seconds, or minutes. Minimum value: 0 Maximum value: 20939000

<b>units</b>
Unit of measurement for the Down Time parameter. Cannot be changed after the monitor is created. Possible values: SEC, MSEC, MIN Default value: SEC

<b>interval</b>
Time interval between two successive probes. Must be greater than the value of Response Time-out. Default value: 5 Minimum value: 1 Maximum value: 20940000

<b>resptimeout</b>
Amount of time for which the appliance must wait before it marks a probe as FAILED. Must be less than the value specified for the Interval parameter. Note: For UDP-ECV monitors for which a receive string is not configured, response timeout does not apply. For UDP-ECV monitors with no receive string, probe failure is indicated by an ICMP port unreachable error received from the service. Default value: 2 Minimum value: 1 Maximum value: 20939000

<b>resptimeoutThresh</b>
Response time threshold, specified as a percentage of the Response Time-out parameter. If the response to a monitor probe has not arrived when the threshold is reached, the appliance generates an SNMP trap called monRespTimeoutAboveThresh. After the response time returns to a value below the threshold, the appliance generates a monRespTimeoutBelowThresh SNMP trap. For the traps to be generated, the "MONITOR-RTO-THRESHOLD" alarm must also be enabled. Minimum value: 0 Maximum value: 100

<b>retries</b>
Maximum number of probes to send to establish the state of a service for which a monitoring probe failed. Default value: 3 Minimum value: 1 Maximum value: 127

<b>failureRetries</b>
Number of retries that must fail, out of the number specified for the Retries parameter, for a service to be marked as DOWN. For example, if the Retries parameter is set to 10 and the Failure Retries parameter is set to 6, out of the ten probes sent, at least six probes must fail if the service is to be marked as DOWN. The default value of 0 means that all the retries must fail if the service is to be marked as DOWN. Maximum value: 32

<b>alertRetries</b>
Number of consecutive probe failures after which the appliance generates an SNMP trap called monProbeFailed. Maximum value: 32

<b>successRetries</b>
Number of consecutive successful probes required to transition a service's state from DOWN to UP. Default value: 1 Minimum value: 1 Maximum value: 32

<b>downTime</b>
Time duration for which to wait before probing a service that has been marked as DOWN. Expressed in milliseconds, seconds, or minutes. Default value: 30 Minimum value: 1 Maximum value: 20939000

<b>destIP</b>
IP address of the service to which to send probes. If the parameter is set to 0, the IP address of the server to which the monitor is bound is considered the destination IP address.

<b>destPort</b>
TCP or UDP port to which to send the probe. If the parameter is set to 0, the port number of the service to which the monitor is bound is considered the destination port. For a monitor of type USER, however, the destination port is the port number that is included in the HTTP request sent to the dispatcher. Does not apply to monitors of type PING.

<b>state</b>
State of the monitor. The DISABLED setting disables not only the monitor being configured, but all monitors of the same type, until the parameter is set to ENABLED. If the monitor is bound to a service, the state of the monitor is not taken into account when the state of the service is determined. Possible values: ENABLED, DISABLED Default value: ENABLED

<b>reverse</b>
Mark a service as DOWN, instead of UP, when probe criteria are satisfied, and as UP instead of DOWN when probe criteria are not satisfied. Possible values: YES, NO Default value: NO

<b>transparent</b>
The monitor is bound to a transparent device such as a firewall or router. The state of a transparent device depends on the responsiveness of the services behind it. If a transparent device is being monitored, a destination IP address must be specified. The probe is sent to the specified IP address by using the MAC address of the transparent device. Possible values: YES, NO Default value: NO

<b>ipTunnel</b>
Send the monitoring probe to the service through an IP tunnel. A destination IP address must be specified. Possible values: YES, NO Default value: NO

<b>tos</b>
Probe the service by encoding the destination IP address in the IP TOS (6) bits. Possible values: YES, NO

<b>tosId</b>
The TOS ID of the specified destination IP. Applicable only when the TOS parameter is set. Minimum value: 1 Maximum value: 63

<b>secure</b>
Use a secure SSL connection when monitoring a service. Applicable only to TCP based monitors. The secure option cannot be used with a CITRIX-AG monitor, because a CITRIX-AG monitor uses a secure connection by default. Possible values: YES, NO Default value: NO

<b>validateCred</b>
Validate the credentials of the Xen Desktop DDC server user. Applicable to monitors of type CITRIX-XD-DDC. Possible values: YES, NO Default value: NO

<b>domain</b>
Domain in which the XenDesktop Desktop Delivery Controller (DDC) servers or Web Interface servers are present. Required by CITRIX-XD-DDC and CITRIX-WI-EXTENDED monitors for logging on to the DDC servers and Web Interface servers, respectively.

<b>IPAddress</b>
Set of IP addresses expected in the monitoring response from the DNS server, if the record type is A or AAAA. Applicable to DNS monitors.

<b>group</b>
Name of a newsgroup available on the NNTP service that is to be monitored. The appliance periodically generates an NNTP query for the name of the newsgroup and evaluates the response. If the newsgroup is found on the server, the service is marked as UP. If the newsgroup does not exist or if the search fails, the service is marked as DOWN. Applicable to NNTP monitors.

<b>fileName</b>
Name of a file on the FTP server. The appliance monitors the FTP service by periodically checking the existence of the file on the server. Applicable to FTP-EXTENDED monitors.

<b>baseDN</b>
The base distinguished name of the LDAP service, from where the LDAP server can begin the search for the attributes in the monitoring query. Required for LDAP service monitoring.

<b>bindDN</b>
The distinguished name with which an LDAP monitor can perform the Bind operation on the LDAP server. Optional. Applicable to LDAP monitors.

<b>filter</b>
Filter criteria for the LDAP query. Optional.

<b>attribute</b>
Attribute to evaluate when the LDAP server responds to the query. Success or failure of the monitoring probe depends on whether the attribute exists in the response. Optional.

<b>database</b>
Name of the database to connect to during authentication.

<b>oracleSid</b>
Name of the service identifier that is used to connect to the Oracle database during authentication.

<b>sqlQuery</b>
SQL query for a MYSQL-ECV or MSSQL-ECV monitor. Sent to the database server after the server authenticates the connection.

<b>evalRule</b>
Default syntax expression that evaluates the database server's response to a MYSQL-ECV or MSSQL-ECV monitoring query. Must produce a Boolean result. The result determines the state of the server. If the expression returns TRUE, the probe succeeds. For example, if you want the appliance to evaluate the error message to determine the state of the server, use the rule MYSQL.RES.ROW(10) .TEXT_ELEM(2).EQ("MySQL").

<b>mssqlProtocolVersion</b>
Version of MSSQL server that is to be monitored. Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012, 2014 Default value: 70

<b>snmpOID</b>
SNMP OID for SNMP monitors.

<b>snmpCommunity</b>
Community name for SNMP monitors.

<b>snmpThreshold</b>
Threshold for SNMP monitors.

<b>snmpVersion</b>
SNMP version to be used for SNMP monitors. Possible values: V1, V2

<b>metricTable</b>
Metric table to which to bind metrics.

<b>application</b>
Name of the application used to determine the state of the service. Applicable to monitors of type CITRIX-XML-SERVICE.

<b>sitePath</b>
URL of the logon page. For monitors of type CITRIX-WEB-INTERFACE, to monitor a dynamic page under the site path, terminate the site path with a slash (/). Applicable to CITRIX-WEB-INTERFACE, CITRIX-WI-EXTENDED and CITRIX-XDM monitors.

<b>storename</b>
Store Name. For monitors of type STOREFRONT, STORENAME is an optional argument defining storefront service store name. Applicable to STOREFRONT monitors.

<b>storefrontacctservice</b>
Enable/Disable probing for Account Service. Applicable only to Store Front monitors. For multi-tenancy configuration users my skip account service Possible values: YES, NO Default value: YES

<b>netProfile</b>
Name of the network profile.

<b>originHost</b>
Origin-Host value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>originRealm</b>
Origin-Realm value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>hostIPAddress</b>
Host-IP-Address value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. If Host-IP-Address is not specified, the appliance inserts the mapped IP (MIP) address or subnet IP (SNIP) address from which the CER request (the monitoring probe) is sent.

<b>vendorId</b>
Vendor-Id value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Minimum value: 0

<b>productName</b>
Product-Name value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>firmwareRevision</b>
Firmware-Revision value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Minimum value: 0

<b>authApplicationId</b>
List of Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring CER message. Minimum value: 0 Maximum value: 4294967295

<b>acctApplicationId</b>
List of Acct-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>inbandSecurityId</b>
Inband-Security-Id for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Possible values: NO_INBAND_SECURITY, TLS

<b>supportedVendorIds</b>
List of Supported-Vendor-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum eight of these AVPs are supported in a monitoring message. Minimum value: 1 Maximum value: 4294967295

<b>vendorSpecificVendorId</b>
Vendor-Id to use in the Vendor-Specific-Application-Id grouped attribute-value pair (AVP) in the monitoring CER message. To specify Auth-Application-Id or Acct-Application-Id in Vendor-Specific-Application-Id, use vendorSpecificAuthApplicationIds or vendorSpecificAcctApplicationIds, respectively. Only one Vendor-Id is supported for all the Vendor-Specific-Application-Id AVPs in a CER monitoring message. Minimum value: 1

<b>vendorSpecificAuthApplicationIds</b>
List of Vendor-Specific-Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>vendorSpecificAcctApplicationIds</b>
List of Vendor-Specific-Acct-Application-Id attribute value pairs (AVPs) to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>kcdAccount</b>
KCD Account used by MSSQL monitor

<b>storedb</b>
Store the database list populated with the responses to monitor probes. Used in database specific load balancing if MSSQL-ECV/MYSQL-ECV monitor is configured. Possible values: ENABLED, DISABLED Default value: DISABLED

<b>storefrontcheckbackendservices</b>
This option will enable monitoring of services running on storefront server. Storefront services are monitored by probing to a Windows service that runs on the Storefront server and exposes details of which storefront services are running. Possible values: YES, NO Default value: NO

<b>trofscode</b>
Code expected when the server is under maintenance Minimum value: 0

<b>trofsstring</b>
String expected from the server for the service to be marked as trofs. Applicable to HTTP-ECV/TCP-ECV monitors.



##Example

add monitor http_mon http

##rm lb monitor

Removes a monitor or a response code for an HTTP monitor. If you do not specify any response codes, the monitor is removed. If you provide any or all of the HTTP response codes that are configured for the monitor, only those specified response codes are removed; the monitor is not removed. Built-in monitors cannot be removed.


##Synopsys

rm lb monitor &lt;monitorName> &lt;type> [-respCode &lt;int[-int]> ...]


##Arguments

<b>monitorName</b>
Name of the monitor.

<b>type</b>
Type of monitor that you want to create. Possible values: PING, TCP, HTTP, TCP-ECV, HTTP-ECV, UDP-ECV, DNS, FTP, LDNS-PING, LDNS-TCP, LDNS-DNS, RADIUS, USER, HTTP-INLINE, SIP-UDP, SIP-TCP, LOAD, FTP-EXTENDED, SMTP, SNMP, NNTP, MYSQL, MYSQL-ECV, MSSQL-ECV, ORACLE-ECV, LDAP, POP3, CITRIX-XML-SERVICE, CITRIX-WEB-INTERFACE, DNS-TCP, RTSP, ARP, CITRIX-AG, CITRIX-AAC-LOGINPAGE, CITRIX-AAC-LAS, CITRIX-XD-DDC, ND6, CITRIX-WI-EXTENDED, DIAMETER, RADIUS_ACCOUNTING, STOREFRONT, APPC, SMPP, CITRIX-XNC-ECV, CITRIX-XDM

<b>respCode</b>
Response codes to delete from the response code list configured for the HTTP monitor.



##Example

rm monitor http_mon http

##set lb monitor

Modifies the specified parameters of a monitor.


##Synopsys

set lb monitor &lt;monitorName> &lt;type> [-action &lt;action>] [-respCode &lt;int[-int]> ...] [-httpRequest &lt;string>] [-rtspRequest &lt;string>] [-customHeaders &lt;string>] [-maxForwards &lt;positive_integer>] [-sipMethod &lt;sipMethod>] [-sipregURI &lt;string>] [-sipURI &lt;string>] [-send &lt;string>] [-recv &lt;string>] [-query &lt;string>] [-queryType &lt;queryType>] [-userName &lt;string>] {-password } {-secondaryPassword } [-logonpointName &lt;string>] [-lasVersion &lt;string>] {-radKey } [-radNASid &lt;string>] [-radNASip &lt;ip_addr>] [-radAccountType &lt;positive_integer>] [-radFramedIP &lt;ip_addr>] [-radAPN &lt;string>] [-radMSISDN &lt;string>] [-radAccountSession &lt;string>] [-LRTM ( ENABLED | DISABLED )] [-deviation &lt;positive_integer> [&lt;units>]] [-scriptName &lt;string>] [-scriptArgs &lt;string>] [-validateCred ( YES | NO )] [-domain &lt;string>] [-dispatcherIP &lt;ip_addr>] [-dispatcherPort &lt;port>] [-interval &lt;integer> [&lt;units>]] [-resptimeout &lt;integer> [&lt;units>]] [-resptimeoutThresh &lt;positive_integer>] [-retries &lt;integer>] [-failureRetries &lt;integer>] [-alertRetries &lt;integer>] [-successRetries &lt;integer>] [-downTime &lt;integer> [&lt;units>]] [-destIP &lt;ip_addr|ipv6_addr>] [-destPort &lt;port>] [-state ( ENABLED | DISABLED )] [-reverse ( YES | NO )] [-transparent ( YES | NO )] [-ipTunnel ( YES | NO )] [-tos ( YES | NO )] [-tosId &lt;positive_integer>] [-secure ( YES | NO )] [-IPAddress &lt;ip_addr|ipv6_addr|*> ...] [-group &lt;string>] [-fileName &lt;string>] [-baseDN &lt;string>] [-bindDN &lt;string>] [-filter &lt;string>] [-attribute &lt;string>] [-database &lt;string> | -oracleSid &lt;string>] [-sqlQuery &lt;text>] [-evalRule &lt;expression>] [-snmpOID &lt;string>] [-snmpCommunity &lt;string>] [-snmpThreshold &lt;string>] [-snmpVersion ( V1 | V2 )] [-metricTable &lt;string>] [-metric &lt;string> [-metricThreshold &lt;positive_integer>] [-metricWeight &lt;positive_integer>]] [-application &lt;string>] [-sitePath &lt;string>] [-storename &lt;string>] [-storefrontacctservice ( YES | NO )] [-storefrontcheckbackendservices ( YES | NO )] [-netProfile &lt;string>] [-mssqlProtocolVersion &lt;mssqlProtocolVersion>] [-originHost &lt;string>] [-originRealm &lt;string>] [-hostIPAddress &lt;ip_addr|ipv6_addr|*>] [-vendorId &lt;positive_integer>] [-productName &lt;string>] [-firmwareRevision &lt;positive_integer>] [-authApplicationId &lt;positive_integer> ...] [-acctApplicationId &lt;positive_integer> ...] [-inbandSecurityId ( NO_INBAND_SECURITY | TLS )] [-supportedVendorIds &lt;positive_integer> ...] [-vendorSpecificVendorId &lt;positive_integer> [-vendorSpecificAuthApplicationIds &lt;positive_integer> ...] [-vendorSpecificAcctApplicationIds &lt;positive_integer> ...]] [-kcdAccount &lt;string>] [-storedb ( ENABLED | DISABLED )] [-trofscode &lt;positive_integer>] [-trofsstring &lt;string>]


##Arguments

<b>monitorName</b>
Name of the monitor.

<b>type</b>
Type of monitor that you want to create. Possible values: PING, TCP, HTTP, TCP-ECV, HTTP-ECV, UDP-ECV, DNS, FTP, LDNS-PING, LDNS-TCP, LDNS-DNS, RADIUS, USER, HTTP-INLINE, SIP-UDP, SIP-TCP, LOAD, FTP-EXTENDED, SMTP, SNMP, NNTP, MYSQL, MYSQL-ECV, MSSQL-ECV, ORACLE-ECV, LDAP, POP3, CITRIX-XML-SERVICE, CITRIX-WEB-INTERFACE, DNS-TCP, RTSP, ARP, CITRIX-AG, CITRIX-AAC-LOGINPAGE, CITRIX-AAC-LAS, CITRIX-XD-DDC, ND6, CITRIX-WI-EXTENDED, DIAMETER, RADIUS_ACCOUNTING, STOREFRONT, APPC, SMPP, CITRIX-XNC-ECV, CITRIX-XDM

<b>action</b>
Action to perform when the response to an inline monitor (a monitor of type HTTP-INLINE) indicates that the service is down. A service monitored by an inline monitor is considered DOWN if the response code is not one of the codes that have been specified for the Response Code parameter. Available settings function as follows: * NONE - Do not take any action. However, the show service command and the show lb monitor command indicate the total number of responses that were checked and the number of consecutive error responses received after the last successful probe. * LOG - Log the event in NSLOG or SYSLOG. * DOWN - Mark the service as being down, and then do not direct any traffic to the service until the configured down time has expired. Persistent connections to the service are terminated as soon as the service is marked as DOWN. Also, log the event in NSLOG or SYSLOG. Possible values: NONE, LOG, DOWN Default value: DOWN

<b>respCode</b>
Response codes for which to mark the service as UP. For any other response code, the action performed depends on the monitor type. HTTP monitors and RADIUS monitors mark the service as DOWN, while HTTP-INLINE monitors perform the action indicated by the Action parameter.

<b>httpRequest</b>
HTTP request to send to the server (for example, "HEAD /file.html").

<b>rtspRequest</b>
RTSP request to send to the server (for example, "OPTIONS *").

<b>customHeaders</b>
Custom header string to include in the monitoring probes.

<b>maxForwards</b>
Maximum number of hops that the SIP request used for monitoring can traverse to reach the server. Applicable only to monitors of type SIP-UDP. Default value: 1 Minimum value: 0 Maximum value: 255

<b>sipMethod</b>
SIP method to use for the query. Applicable only to monitors of type SIP-UDP. Possible values: OPTIONS, INVITE, REGISTER

<b>sipregURI</b>
SIP user to be registered. Applicable only if the monitor is of type SIP-UDP and the SIP Method parameter is set to REGISTER.

<b>sipURI</b>
SIP URI string to send to the service (for example, sip:sip.test). Applicable only to monitors of type SIP-UDP.

<b>send</b>
String to send to the service. Applicable to TCP-ECV, HTTP-ECV, and UDP-ECV monitors.

<b>recv</b>
String expected from the server for the service to be marked as UP. Applicable to TCP-ECV, HTTP-ECV, and UDP-ECV monitors.

<b>query</b>
Domain name to resolve as part of monitoring the DNS service (for example, example.com).

<b>queryType</b>
Type of DNS record for which to send monitoring queries. Set to Address for querying A records, AAAA for querying AAAA records, and Zone for querying the SOA record. Possible values: Address, Zone, AAAA

<b>userName</b>
User name with which to probe the RADIUS, NNTP, FTP, FTP-EXTENDED, MYSQL, MSSQL, POP3, CITRIX-AG, CITRIX-XD-DDC, CITRIX-WI-EXTENDED, CITRIX-XNC or CITRIX-XDM server.

<b>password</b>
Password that is required for logging on to the RADIUS, NNTP, FTP, FTP-EXTENDED, MYSQL, MSSQL, POP3, CITRIX-AG, CITRIX-XD-DDC, CITRIX-WI-EXTENDED, CITRIX-XNC-ECV or CITRIX-XDM server. Used in conjunction with the user name specified for the User Name parameter.

<b>secondaryPassword</b>
Secondary password that users might have to provide to log on to the Access Gateway server. Applicable to CITRIX-AG monitors.

<b>logonpointName</b>
Name of the logon point that is configured for the Citrix Access Gateway Advanced Access Control software. Required if you want to monitor the associated login page or Logon Agent. Applicable to CITRIX-AAC-LAS and CITRIX-AAC-LOGINPAGE monitors.

<b>lasVersion</b>
Version number of the Citrix Advanced Access Control Logon Agent. Required by the CITRIX-AAC-LAS monitor.

<b>radKey</b>
Authentication key (shared secret text string) for RADIUS clients and servers to exchange. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radNASid</b>
NAS-Identifier to send in the Access-Request packet. Applicable to monitors of type RADIUS.

<b>radNASip</b>
Network Access Server (NAS) IP address to use as the source IP address when monitoring a RADIUS server. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radAccountType</b>
Account Type to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING. Default value: 1 Minimum value: 0 Maximum value: 15

<b>radFramedIP</b>
Source ip with which the packet will go out . Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAPN</b>
Called Station Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radMSISDN</b>
Calling Stations Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAccountSession</b>
Account Session ID to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>LRTM</b>
Calculate the least response times for bound services. If this parameter is not enabled, the appliance does not learn the response times of the bound services. Also used for LRTM load balancing. Possible values: ENABLED, DISABLED

<b>deviation</b>
Time value added to the learned average response time in dynamic response time monitoring (DRTM). When a deviation is specified, the appliance learns the average response time of bound services and adds the deviation to the average. The final value is then continually adjusted to accommodate response time variations over time. Specified in milliseconds, seconds, or minutes. Minimum value: 0 Maximum value: 20939000

<b>units</b>
Unit of measurement for the Down Time parameter. Cannot be changed after the monitor is created. Possible values: SEC, MSEC, MIN Default value: SEC

<b>scriptName</b>
Path and name of the script to execute. The script must be available on the NetScaler appliance, in the /nsconfig/monitors/ directory.

<b>scriptArgs</b>
String of arguments for the script. The string is copied verbatim into the request.

<b>validateCred</b>
Validate the credentials of the Xen Desktop DDC server user. Applicable to monitors of type CITRIX-XD-DDC. Possible values: YES, NO Default value: NO

<b>domain</b>
Domain in which the XenDesktop Desktop Delivery Controller (DDC) servers or Web Interface servers are present. Required by CITRIX-XD-DDC and CITRIX-WI-EXTENDED monitors for logging on to the DDC servers and Web Interface servers, respectively.

<b>dispatcherIP</b>
IP address of the dispatcher to which to send the probe.

<b>dispatcherPort</b>
Port number on which the dispatcher listens for the monitoring probe.

<b>interval</b>
Time interval between two successive probes. Must be greater than the value of Response Time-out. Default value: 5 Minimum value: 1 Maximum value: 20940000

<b>resptimeout</b>
Amount of time for which the appliance must wait before it marks a probe as FAILED. Must be less than the value specified for the Interval parameter. Note: For UDP-ECV monitors for which a receive string is not configured, response timeout does not apply. For UDP-ECV monitors with no receive string, probe failure is indicated by an ICMP port unreachable error received from the service. Default value: 2 Minimum value: 1 Maximum value: 20939000

<b>resptimeoutThresh</b>
Response time threshold, specified as a percentage of the Response Time-out parameter. If the response to a monitor probe has not arrived when the threshold is reached, the appliance generates an SNMP trap called monRespTimeoutAboveThresh. After the response time returns to a value below the threshold, the appliance generates a monRespTimeoutBelowThresh SNMP trap. For the traps to be generated, the "MONITOR-RTO-THRESHOLD" alarm must also be enabled. Minimum value: 0 Maximum value: 100

<b>retries</b>
Maximum number of probes to send to establish the state of a service for which a monitoring probe failed. Default value: 3 Minimum value: 1 Maximum value: 127

<b>failureRetries</b>
Number of retries that must fail, out of the number specified for the Retries parameter, for a service to be marked as DOWN. For example, if the Retries parameter is set to 10 and the Failure Retries parameter is set to 6, out of the ten probes sent, at least six probes must fail if the service is to be marked as DOWN. The default value of 0 means that all the retries must fail if the service is to be marked as DOWN. Maximum value: 32

<b>alertRetries</b>
Number of consecutive probe failures after which the appliance generates an SNMP trap called monProbeFailed. Maximum value: 32

<b>successRetries</b>
Number of consecutive successful probes required to transition a service's state from DOWN to UP. Default value: 1 Minimum value: 1 Maximum value: 32

<b>downTime</b>
Time duration for which to wait before probing a service that has been marked as DOWN. Expressed in milliseconds, seconds, or minutes. Default value: 30 Minimum value: 1 Maximum value: 20939000

<b>destIP</b>
IP address of the service to which to send probes. If the parameter is set to 0, the IP address of the server to which the monitor is bound is considered the destination IP address.

<b>destPort</b>
TCP or UDP port to which to send the probe. If the parameter is set to 0, the port number of the service to which the monitor is bound is considered the destination port. For a monitor of type USER, however, the destination port is the port number that is included in the HTTP request sent to the dispatcher. Does not apply to monitors of type PING.

<b>state</b>
State of the monitor. The DISABLED setting disables not only the monitor being configured, but all monitors of the same type, until the parameter is set to ENABLED. If the monitor is bound to a service, the state of the monitor is not taken into account when the state of the service is determined. Possible values: ENABLED, DISABLED Default value: ENABLED

<b>reverse</b>
Mark a service as DOWN, instead of UP, when probe criteria are satisfied, and as UP instead of DOWN when probe criteria are not satisfied. Possible values: YES, NO Default value: NO

<b>transparent</b>
The monitor is bound to a transparent device such as a firewall or router. The state of a transparent device depends on the responsiveness of the services behind it. If a transparent device is being monitored, a destination IP address must be specified. The probe is sent to the specified IP address by using the MAC address of the transparent device. Possible values: YES, NO Default value: NO

<b>ipTunnel</b>
Send the monitoring probe to the service through an IP tunnel. A destination IP address must be specified. Possible values: YES, NO Default value: NO

<b>tos</b>
Probe the service by encoding the destination IP address in the IP TOS (6) bits. Possible values: YES, NO

<b>tosId</b>
The TOS ID of the specified destination IP. Applicable only when the TOS parameter is set. Minimum value: 1 Maximum value: 63

<b>secure</b>
Use a secure SSL connection when monitoring a service. Applicable only to TCP based monitors. The secure option cannot be used with a CITRIX-AG monitor, because a CITRIX-AG monitor uses a secure connection by default. Possible values: YES, NO Default value: NO

<b>IPAddress</b>
Set of IP addresses expected in the monitoring response from the DNS server, if the record type is A or AAAA. Applicable to DNS monitors.

<b>group</b>
Name of a newsgroup available on the NNTP service that is to be monitored. The appliance periodically generates an NNTP query for the name of the newsgroup and evaluates the response. If the newsgroup is found on the server, the service is marked as UP. If the newsgroup does not exist or if the search fails, the service is marked as DOWN. Applicable to NNTP monitors.

<b>fileName</b>
Name of a file on the FTP server. The appliance monitors the FTP service by periodically checking the existence of the file on the server. Applicable to FTP-EXTENDED monitors.

<b>baseDN</b>
The base distinguished name of the LDAP service, from where the LDAP server can begin the search for the attributes in the monitoring query. Required for LDAP service monitoring.

<b>bindDN</b>
The distinguished name with which an LDAP monitor can perform the Bind operation on the LDAP server. Optional. Applicable to LDAP monitors.

<b>filter</b>
Filter criteria for the LDAP query. Optional.

<b>attribute</b>
Attribute to evaluate when the LDAP server responds to the query. Success or failure of the monitoring probe depends on whether the attribute exists in the response. Optional.

<b>database</b>
Name of the database to connect to during authentication.

<b>oracleSid</b>
Name of the service identifier that is used to connect to the Oracle database during authentication.

<b>sqlQuery</b>
SQL query for a MYSQL-ECV or MSSQL-ECV monitor. Sent to the database server after the server authenticates the connection.

<b>evalRule</b>
Default syntax expression that evaluates the database server's response to a MYSQL-ECV or MSSQL-ECV monitoring query. Must produce a Boolean result. The result determines the state of the server. If the expression returns TRUE, the probe succeeds. For example, if you want the appliance to evaluate the error message to determine the state of the server, use the rule MYSQL.RES.ROW(10) .TEXT_ELEM(2).EQ("MySQL").

<b>snmpOID</b>
SNMP OID for SNMP monitors.

<b>snmpCommunity</b>
Community name for SNMP monitors.

<b>snmpThreshold</b>
Threshold for SNMP monitors.

<b>snmpVersion</b>
SNMP version to be used for SNMP monitors. Possible values: V1, V2

<b>metricTable</b>
Metric table to which to bind metrics.

<b>metric</b>
Metric name in the metric table, whose setting is changed. A value zero disables the metric and it will not be used for load calculation

<b>metricThreshold</b>
Threshold to be used for that metric. Minimum value: 0

<b>metricWeight</b>
The weight for the specified service metric with respect to others. Minimum value: 1 Maximum value: 100

<b>application</b>
Name of the application used to determine the state of the service. Applicable to monitors of type CITRIX-XML-SERVICE.

<b>sitePath</b>
URL of the logon page. For monitors of type CITRIX-WEB-INTERFACE, to monitor a dynamic page under the site path, terminate the site path with a slash (/). Applicable to CITRIX-WEB-INTERFACE, CITRIX-WI-EXTENDED and CITRIX-XDM monitors.

<b>storename</b>
Store Name. For monitors of type STOREFRONT, STORENAME is an optional argument defining storefront service store name. Applicable to STOREFRONT monitors.

<b>storefrontacctservice</b>
Enable/Disable probing for Account Service. Applicable only to Store Front monitors. For multi-tenancy configuration users my skip account service Possible values: YES, NO Default value: YES

<b>storefrontcheckbackendservices</b>
This option will enable monitoring of services running on storefront server. Storefront services are monitored by probing to a Windows service that runs on the Storefront server and exposes details of which storefront services are running. Possible values: YES, NO Default value: NO

<b>netProfile</b>
Name of the network profile.

<b>mssqlProtocolVersion</b>
Version of MSSQL server that is to be monitored. Possible values: 70, 2000, 2000SP1, 2005, 2008, 2008R2, 2012, 2014 Default value: 70

<b>originHost</b>
Origin-Host value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>originRealm</b>
Origin-Realm value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>hostIPAddress</b>
Host-IP-Address value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. If Host-IP-Address is not specified, the appliance inserts the mapped IP (MIP) address or subnet IP (SNIP) address from which the CER request (the monitoring probe) is sent.

<b>vendorId</b>
Vendor-Id value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Minimum value: 0

<b>productName</b>
Product-Name value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>firmwareRevision</b>
Firmware-Revision value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Minimum value: 0

<b>authApplicationId</b>
List of Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring CER message. Minimum value: 0 Maximum value: 4294967295

<b>acctApplicationId</b>
List of Acct-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>inbandSecurityId</b>
Inband-Security-Id for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. Possible values: NO_INBAND_SECURITY, TLS

<b>supportedVendorIds</b>
List of Supported-Vendor-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum eight of these AVPs are supported in a monitoring message. Minimum value: 1 Maximum value: 4294967295

<b>vendorSpecificVendorId</b>
Vendor-Id to use in the Vendor-Specific-Application-Id grouped attribute-value pair (AVP) in the monitoring CER message. To specify Auth-Application-Id or Acct-Application-Id in Vendor-Specific-Application-Id, use vendorSpecificAuthApplicationIds or vendorSpecificAcctApplicationIds, respectively. Only one Vendor-Id is supported for all the Vendor-Specific-Application-Id AVPs in a CER monitoring message. Minimum value: 1

<b>vendorSpecificAuthApplicationIds</b>
List of Vendor-Specific-Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>vendorSpecificAcctApplicationIds</b>
List of Vendor-Specific-Acct-Application-Id attribute value pairs (AVPs) to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message. Minimum value: 0 Maximum value: 4294967295

<b>kcdAccount</b>
KCD Account used by MSSQL monitor

<b>storedb</b>
Store the database list populated with the responses to monitor probes. Used in database specific load balancing if MSSQL-ECV/MYSQL-ECV monitor is configured. Possible values: ENABLED, DISABLED Default value: DISABLED

<b>trofscode</b>
Code expected when the server is under maintenance Minimum value: 0

<b>trofsstring</b>
String expected from the server for the service to be marked as trofs. Applicable to HTTP-ECV/TCP-ECV monitors.



##Example

set monitor http_mon http -respcode 100

##unset lb monitor

Removes the specified parameter settings from the specified monitor. Attributes for which a default value is available revert to their default values..Refer to the set lb monitor command for meanings of the arguments.


##Synopsys

unset lb monitor &lt;monitorName> &lt;type> [-IPAddress &lt;ip_addr|ipv6_addr|*> ...] [-scriptName] [-destPort] [-netProfile] [-action] [-respCode] [-httpRequest] [-rtspRequest] [-customHeaders] [-maxForwards] [-sipMethod] [-sipregURI] [-send] [-recv] [-query] [-queryType] [-userName] [-password] [-secondaryPassword] [-logonpointName] [-lasVersion] [-radKey] [-radNASid] [-radNASip] [-radAccountType] [-radFramedIP] [-radAPN] [-radMSISDN] [-radAccountSession] [-LRTM] [-deviation] [-scriptArgs] [-validateCred] [-domain] [-dispatcherIP] [-dispatcherPort] [-interval] [-resptimeout] [-resptimeoutThresh] [-retries] [-failureRetries] [-alertRetries] [-successRetries] [-downTime] [-destIP] [-state] [-reverse] [-transparent] [-ipTunnel] [-tos] [-tosId] [-secure] [-group] [-fileName] [-baseDN] [-bindDN] [-filter] [-attribute] [-database] [-oracleSid] [-sqlQuery] [-snmpOID] [-snmpCommunity] [-snmpThreshold] [-snmpVersion] [-metricTable] [-mssqlProtocolVersion] [-originHost] [-originRealm] [-hostIPAddress] [-vendorId] [-productName] [-firmwareRevision] [-authApplicationId] [-acctApplicationId] [-inbandSecurityId] [-supportedVendorIds] [-vendorSpecificVendorId] [-vendorSpecificAuthApplicationIds] [-vendorSpecificAcctApplicationIds] [-kcdAccount] [-storedb] [-trofscode] [-trofsstring]


##Example

set monitor dns_mon dns -ipaddress 10.102.27.230

##enable lb monitor

Enable the monitor that is bound to a specific service. If no monitor name is specified, all monitors bound to the service are enabled.


##Synopsys

enable lb monitor (&lt;serviceName>@ | &lt;serviceGroupName>@) [&lt;monitorName>]


##Arguments

<b>serviceName</b>
The name of the service to which the monitor is bound.

<b>serviceGroupName</b>
The name of the service group to which the monitor is to be bound.

<b>monitorName</b>
Name for the monitor. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my monitor" or 'my monitor').



##Example

enable monitor http_svc http_mon To enable monitor for multiple services use the following command: enable monitor http_svc[1-3] http_mon

##disable lb monitor

Disable the monitor for a service. If the monitor name is not specified, all monitors bound to the service are disabled.


##Synopsys

disable lb monitor (&lt;serviceName>@ | &lt;serviceGroupName>@) [&lt;monitorName>]


##Arguments

<b>serviceName</b>
The name of the service being monitored.

<b>serviceGroupName</b>
The name of the service group being monitored.

<b>monitorName</b>
Name for the monitor. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my monitor" or 'my monitor').



##Example

disable monitor http_svc http_mon To disable a monitor on multiple services use the following command: disable monitor http_svc[1-3] http_mon

##bind lb monitor

Binds a monitor to a service or service group. Multiple monitors can be bound to a service or service group.


##Synopsys

bind lb monitor &lt;monitorName> [-state ( ENABLED | DISABLED )] [-weight &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-weight &lt;positive_integer>] [-metric &lt;string> -metricThreshold &lt;positive_integer> [-metricWeight &lt;positive_integer>] ]


##Arguments

<b>monitorName</b>
Name of the monitor.

<b>metric</b>
Name of the metric to be polled by the monitor.

<b>metricThreshold</b>
Threshold for the specified metric. A value of zero disables the metric (the metric will not be used in load calculations). Minimum value: 0

<b>metricWeight</b>
Weight to assign to the specified metric. A higher number specifies greater weight. Default value: 1 Minimum value: 1 Maximum value: 100



##Example

bind monitor http_mon http_svc To bind a monitor to multiple services use the following command: bind monitor http_mon http_svc[1-3]

##unbind lb monitor

Unbinds a monitor from a service or service group.


##Synopsys

unbind lb monitor &lt;monitorName> -metric &lt;string>


##Arguments

<b>monitorName</b>
Name of the monitor.

<b>metric</b>
Name of the metric to be polled by the monitor.



##Example

unbind monitor http_mon http_svc To unbind a monitor to multiple services use the following command: unbind monitor http_mon http_svc[1-3]

##show lb monitor

Displays the parameters of all the monitors configured on the appliance, or the parameters of the specified monitor.


##Synopsys

show lb monitor [&lt;monitorName>] [&lt;type>] show lb monitor bindings - alias for 'show lb monbindings'


##Arguments

<b>monitorName</b>
Name of the monitor.

<b>type</b>
Type of monitor that you want to create. Possible values: PING, TCP, HTTP, TCP-ECV, HTTP-ECV, UDP-ECV, DNS, FTP, LDNS-PING, LDNS-TCP, LDNS-DNS, RADIUS, USER, HTTP-INLINE, SIP-UDP, SIP-TCP, LOAD, FTP-EXTENDED, SMTP, SNMP, NNTP, MYSQL, MYSQL-ECV, MSSQL-ECV, ORACLE-ECV, LDAP, POP3, CITRIX-XML-SERVICE, CITRIX-WEB-INTERFACE, DNS-TCP, RTSP, ARP, CITRIX-AG, CITRIX-AAC-LOGINPAGE, CITRIX-AAC-LAS, CITRIX-XD-DDC, ND6, CITRIX-WI-EXTENDED, DIAMETER, RADIUS_ACCOUNTING, STOREFRONT, APPC, SMPP, CITRIX-XNC-ECV, CITRIX-XDM



##Outputs

<b>interval</b>
The frequency at which the probe is sent to the service.

<b>units</b>
Giving the unit of the metric

<b>resptimeout</b>
The interval for which the system waits before it marks the probe as FAILED.

<b>resptimeoutThresh</b>
Response time threshold, specified as a percentage of the Response Time-out parameter. If the response to a monitor probe has not arrived when the threshold is reached, the appliance generates an SNMP trap called monRespTimeoutAboveThresh. After the response time returns to a value below the threshold, the appliance generates a monRespTimeoutBelowThresh SNMP trap. For the traps to be generated, the "MONITOR-RTO-THRESHOLD" alarm must also be enabled.

<b>retries</b>
Maximum number of probes to send to establish the state of a service for which a monitoring probe failed.

<b>failureRetries</b>
Number of retries that must fail, out of the number specified for the Retries parameter, for a service to be marked as DOWN. For example, if the Retries parameter is set to 10 and the Failure Retries parameter is set to 6, out of the ten probes sent, at least six probes must fail if the service is to be marked as DOWN. The default value of 0 means that all the retries must fail if the service is to be marked as DOWN.

<b>alertRetries</b>
The number of failures after which the system generates a SNMP trap.

<b>successRetries</b>
Number of consecutive successful probes required to transition a service's state from DOWN to UP.

<b>downTime</b>
The duration in seconds for which the system waits to make the next probe once the service is marked as DOWN.

<b>destIP</b>
The IP address to which the probe is sent.

<b>destPort</b>
The TCP/UDP port to which the probe is sent.

<b>state</b>

<b>reverse</b>
Mark a service as DOWN, instead of UP, when probe criteria are satisfied, and as UP instead of DOWN when probe criteria are not satisfied.

<b>transparent</b>
The state of the monitor for transparent devices.

<b>ipTunnel</b>
The state of the monitor for tunneled devices.

<b>tos</b>
TOS setting.

<b>tosId</b>
TOS ID

<b>secure</b>
The state of the secure monitoring of services.

<b>action</b>
Action to perform when the response to an inline monitor (a monitor of type HTTP-INLINE) indicates that the service is down. A service monitored by an inline monitor is considered DOWN if the response code is not one of the codes that have been specified for the Response Code parameter. Available settings function as follows: * NONE - Do not take any action. However, the show service command and the show lb monitor command indicate the total number of responses that were checked and the number of consecutive error responses received after the last successful probe. * LOG - Log the event in NSLOG or SYSLOG. * DOWN - Mark the service as being down, and then do not direct any traffic to the service until the configured down time has expired. Persistent connections to the service are terminated as soon as the service is marked as DOWN. Also, log the event in NSLOG or SYSLOG.

<b>respCode</b>
The response codes.

<b>httpRequest</b>
The HTTP request that is sent to the server.

<b>rtspRequest</b>
The RTSP request that is sent to the server.

<b>send</b>
The string that is sent to the service.

<b>recv</b>
The string that is expected from the server to mark the server as UP.

<b>query</b>
Domain name to resolve as part of monitoring the DNS service (for example, example.com).

<b>queryType</b>
Type of DNS record for which to send monitoring queries. Set to Address for querying A records, AAAA for querying AAAA records, and Zone for querying the SOA record.

<b>userName</b>
Username on the RADIUS/NNTP/FTP/FTP-EXTENDED/MYSQL/POP3/CITRIX-XD-DDC/CITRIX-WI-EXTENDED/CITRIX-XNC-ECV/CITRIX-XDM server. This user name is used in the probe.

<b>password</b>
Password used in RADIUS/NNTP/FTP/FTP-EXTENDED/MYSQL/POP3/LDAP/CITRIX-XD-DDC/CITRIX-WI-EXTENDED/CITRIX-XNC-ECV/CITRIX-XDM server monitoring.

<b>secondaryPassword</b>
Secondary password that users might have to provide to log on to the Access Gateway server. Applicable to CITRIX-AG monitors.

<b>logonpointName</b>
Logonpoint name used in Citrix AAC login page monitoring.

<b>lasVersion</b>
Version number of the Citrix Advanced Access Control Logon Agent. Required by the CITRIX-AAC-LAS monitor.

<b>validateCred</b>
Validate the credentials of the Xen Desktop DDC server user. Applicable to monitors of type CITRIX-XD-DDC.

<b>domain</b>
Domain in which the XenDesktop Desktop Delivery Controller (DDC) servers or Web Interface servers are present. Required by CITRIX-XD-DDC and CITRIX-WI-EXTENDED monitors for logging on to the DDC servers and Web Interface servers, respectively.

<b>radKey</b>
Authentication key (shared secret text string) for RADIUS clients and servers to exchange. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radNASid</b>
NAS-Identifier to send in the Access-Request packet. Applicable to monitors of type RADIUS.

<b>radNASip</b>
Network Access Server (NAS) IP address to use as the source IP address when monitoring a RADIUS server. Applicable to monitors of type RADIUS and RADIUS_ACCOUNTING.

<b>radAccountType</b>
Account Type to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radFramedIP</b>
Source ip with which the packet will go out . Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAPN</b>
Called Station Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radMSISDN</b>
Calling Stations Id to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>radAccountSession</b>
Account Session ID to be used in Account Request Packet. Applicable to monitors of type RADIUS_ACCOUNTING.

<b>LRTM</b>
Calculate the least response times for bound services. If this parameter is not enabled, the appliance does not learn the response times of the bound services. Also used for LRTM load balancing.

<b>lrtmConf</b>
State of LRTM configuration on the monitor.

<b>lrtmConfStr</b>
State of LRTM configuration on the monitor as STRING.

<b>deviation</b>
Deviation from the learnt response time for Dynamic Response Time monitoring.

<b>dynamicResponseTimeout</b>
Response timeout of the DRTM enabled monitor , calculated dynamically based on the history and current response time.

<b>dynamicInterval</b>
Interval between monitoring probes for DRTM enabled monitor , calculated dynamically based monitor response time.

<b>scriptName</b>
Path and name of the script to execute. The script must be available on the NetScaler appliance, in the /nsconfig/monitors/ directory.

<b>scriptArgs</b>
String of arguments for the script. The string is copied verbatim into the request.

<b>dispatcherIP</b>
IP address of the dispatcher to which to send the probe.

<b>dispatcherPort</b>
Port number on which the dispatcher listens for the monitoring probe.

<b>sipURI</b>
SIP URI string to send to the service (for example, sip:sip.test). Applicable only to monitors of type SIP-UDP.

<b>sipMethod</b>
Specifies SIP method to be used for the query

<b>maxForwards</b>
Maximum number of hops a sip monitor packet can go.

<b>sipregURI</b>
Specifies SIP user to be registered

<b>customHeaders</b>
The string that is sent to the service. Applicable to HTTP ,HTTP-ECV and RTSP monitor types.

<b>IPAddress</b>
Set of IP addresses expected in the monitoring response from the DNS server, if the record type is A or AAAA. Applicable to DNS monitors.

<b>group</b>
Name of a newsgroup available on the NNTP service that is to be monitored. The appliance periodically generates an NNTP query for the name of the newsgroup and evaluates the response. If the newsgroup is found on the server, the service is marked as UP. If the newsgroup does not exist or if the search fails, the service is marked as DOWN. Applicable to NNTP monitors.

<b>fileName</b>
Name of a file on the FTP server. The appliance monitors the FTP service by periodically checking the existence of the file on the server. Applicable to FTP-EXTENDED monitors.

<b>baseDN</b>
The base distinguished name of the LDAP service, from where the LDAP server can begin the search for the attributes in the monitoring query. Required for LDAP service monitoring.

<b>bindDN</b>
The distinguished name with which an LDAP monitor can perform the Bind operation on the LDAP server. Optional. Applicable to LDAP monitors.

<b>filter</b>
Filter criteria for the LDAP query. Optional.

<b>attribute</b>
Attribute to evaluate when the LDAP server responds to the query. Success or failure of the monitoring probe depends on whether the attribute exists in the response. Optional.

<b>database</b>
Name of the database to connect to during authentication.

<b>oracleSid</b>
Name of the service identifier that is used to connect to the Oracle database during authentication.

<b>sqlQuery</b>
SQL query for a MYSQL-ECV or MSSQL-ECV monitor. Sent to the database server after the server authenticates the connection.

<b>evalRule</b>
Default syntax expression that evaluates the database server's response to a MYSQL-ECV or MSSQL-ECV monitoring query. Must produce a Boolean result. The result determines the state of the server. If the expression returns TRUE, the probe succeeds. For example, if you want the appliance to evaluate the error message to determine the state of the server, use the rule MYSQL.RES.ROW(10) .TEXT_ELEM(2).EQ("MySQL").

<b>snmpOID</b>
SNMP OID for SNMP monitors.

<b>snmpCommunity</b>
Community name for SNMP monitors.

<b>snmpThreshold</b>
Threshold for SNMP monitors.

<b>snmpVersion</b>
SNMP version to be used for SNMP monitoring.

<b>metric</b>
Metric name in the metric table, whose setting is changed

<b>metricTable</b>
Metric table, whose setting is changed

<b>multimetrictable</b>
Metric table to which to bind metrics, to be used only for output purposes.

<b>metricThreshold</b>
Threshold to be used for that metric.

<b>metricWeight</b>
The weight for the specified service metric with respect to others.

<b>stateflag</b>
Flags controlling the display.

<b>flags</b>
Used by build-in monitors.

<b>application</b>
Name of the application used to determine the state of the service. Applicable to monitors of type CITRIX-XML-SERVICE.

<b>sitePath</b>
URL of the logon page. For monitors of type CITRIX-WEB-INTERFACE, to monitor a dynamic page under the site path, terminate the site path with a slash (/). Applicable to CITRIX-WEB-INTERFACE, CITRIX-WI-EXTENDED and CITRIX-XDM monitors.

<b>storename</b>
Store Name. For monitors of type STOREFRONT, STORENAME is an optional argument defining storefront service store name. Applicable to STOREFRONT monitors.

<b>storefrontacctservice</b>
Enable/Disable probing for Account Service. Applicable only to Store Front monitors. For multi-tenancy configuration users my skip account service

<b>storefrontcheckbackendservices</b>
This option will enable monitoring of services running on storefront server. Storefront services are monitored by probing to a Windows service that runs on the Storefront server and exposes details of which storefront services are running.

<b>hostName</b>
Hostname in the FQDN format (Example: porche.cars.org). Applicable to STOREFRONT monitors.

<b>netProfile</b>
Name of the network profile.

<b>mssqlProtocolVersion</b>
Version of MSSQL server that is to be monitored.

<b>originHost</b>
Origin-Host value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>originRealm</b>
Origin-Realm value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>hostIPAddress</b>
Host-IP-Address value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. If Host-IP-Address is not specified, the appliance inserts the mapped IP (MIP) address or subnet IP (SNIP) address from which the CER request (the monitoring probe) is sent.

<b>vendorId</b>
Vendor-Id value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>productName</b>
Product-Name value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>firmwareRevision</b>
Firmware-Revision value for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>authApplicationId</b>
List of Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring CER message.

<b>acctApplicationId</b>
List of Acct-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message.

<b>inbandSecurityId</b>
Inband-Security-Id for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers.

<b>supportedVendorIds</b>
List of Supported-Vendor-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum eight of these AVPs are supported in a monitoring message.

<b>vendorSpecificVendorId</b>
Vendor-Id to use in the Vendor-Specific-Application-Id grouped attribute-value pair (AVP) in the monitoring CER message. To specify Auth-Application-Id or Acct-Application-Id in Vendor-Specific-Application-Id, use vendorSpecificAuthApplicationIds or vendorSpecificAcctApplicationIds, respectively. Only one Vendor-Id is supported for all the Vendor-Specific-Application-Id AVPs in a CER monitoring message.

<b>vendorSpecificAuthApplicationIds</b>
List of Vendor-Specific-Auth-Application-Id attribute value pairs (AVPs) for the Capabilities-Exchange-Request (CER) message to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message.

<b>vendorSpecificAcctApplicationIds</b>
List of Vendor-Specific-Acct-Application-Id attribute value pairs (AVPs) to use for monitoring Diameter servers. A maximum of eight of these AVPs are supported in a monitoring message. The specified value is combined with the value of vendorSpecificVendorId to obtain the Vendor-Specific-Application-Id AVP in the CER monitoring message.

<b>serviceName</b>

<b>weight</b>

<b>serviceGroupName</b>

<b>kcdAccount</b>
KCD Account used by MSSQL monitor

<b>storedb</b>
Store the database list populated with the responses to monitor probes. Used in database specific load balancing if MSSQL-ECV/MYSQL-ECV monitor is configured.

<b>trofscode</b>
Code expected when the server is under maintenance

<b>trofsstring</b>
String expected from the server for the service to be marked as trofs. Applicable to HTTP-ECV/TCP-ECV monitors.

<b>devno</b>

<b>count</b>



##Example

An example of the show monitor command output is as follows: 8 configured monitors: 1) Name.......: ping Type......: PING State....ENABLED 2) Name.......: tcp Type......: TCP State....ENABLED 3) Name.......: http Type......: HTTP State....ENABLED 4) Name.......: tcp-ecv Type......: TCP-ECV State....ENABLED 5) Name.......: http-ecv Type......: HTTP-ECV State....ENABLED 6) Name.......: udp-ecv Type......: UDP-ECV State....ENABLED 7) Name.......: dns Type......: DNS State....ENABLED 8) Name.......: ftp Type......: FTP State....ENABLED

