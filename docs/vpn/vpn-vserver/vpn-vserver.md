#vpn vserver

The following operations can be performed on "vpn vserver":


[add](#add-vpn-vserver) | [rm](#rm-vpn-vserver) | [set](#set-vpn-vserver) | [unset](#unset-vpn-vserver) | [bind](#bind-vpn-vserver) | [unbind](#unbind-vpn-vserver) | [enable](#enable-vpn-vserver) | [disable](#disable-vpn-vserver) | [show](#show-vpn-vserver) | [stat](#stat-vpn-vserver) | [rename](#rename-vpn-vserver) | [check](#check-vpn-vserver)

##add vpn vserver

Creates a NetScaler Gateway virtual server to allow authenticated users to access intranet resources, such as XenApp, XenDesktop, and web servers.


##Synopsys

add vpn vserver &lt;name> &lt;serviceType> [&lt;IPAddress>  [-range &lt;positive_integer>]] [&lt;port>] [-state ( ENABLED | DISABLED )] [-authentication ( ON | OFF )] [-doubleHop ( ENABLED | DISABLED )] [-maxAAAUsers &lt;positive_integer>] [-icaOnly ( ON | OFF )] [-icaProxySessionMigration ( ON | OFF )] [-dtls ( ON | OFF )] [-loginOnce ( ON | OFF )] [-deviceCert ( ON | OFF )  [-certkeyNames &lt;string>]] [-downStateFlush ( ENABLED | DISABLED )] [-Listenpolicy &lt;expression>  [-Listenpriority &lt;positive_integer>]] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )] [-netProfile &lt;string>] [-cginfraHomePageRedirect ( ENABLED | DISABLED )] [-maxLoginAttempts &lt;positive_integer>  [-failedLoginTimeout &lt;mins>]] [-l2Conn ( ON | OFF )] [-deploymentType &lt;deploymentType>] [-rdpServerProfileName &lt;string>] [-WindowsEPAPluginUpgrade &lt;WindowsEPAPluginUpgrade>] [-LinuxEPAPluginUpgrade &lt;LinuxEPAPluginUpgrade>] [-MacEPAPluginUpgrade &lt;MacEPAPluginUpgrade>] [-userDomains &lt;string>]


##Arguments

<b>name</b>
Name for the NetScaler Gateway virtual server. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the virtual server is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my server" or 'my server').

<b>serviceType</b>
Protocol used by the NetScaler Gateway virtual server.
Possible values: SSL
Default value: SSL

<b>IPAddress</b>
IPv4 or IPv6 address of the NetScaler Gateway virtual server. Usually a public IP address. User devices send connection requests to this IP address.

<b>range</b>
Range of NetScaler Gateway virtual server IP addresses. The consecutively numbered range of IP addresses begins with the address specified by the IP Address parameter. 
In the configuration utility, select Network VServer to enter a range.
Default value: 1
Minimum value: 1

<b>port</b>
TCP port on which the virtual server listens.

<b>state</b>
State of the virtual server. If the virtual server is disabled, requests are not processed.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>authentication</b>
Require authentication for users connecting to NetScaler Gateway.
Possible values: ON, OFF
Default value: ON

<b>doubleHop</b>
Use the NetScaler Gateway appliance in a double-hop configuration. A double-hop deployment provides an extra layer of security for the internal network by using three firewalls to divide the DMZ into two stages. Such a deployment can have one appliance in the DMZ and one appliance in the secure network.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>maxAAAUsers</b>
Maximum number of concurrent user sessions allowed on this virtual server. The actual number of users allowed to log on to this virtual server depends on the total number of user licenses.
Minimum value: 0

<b>icaOnly</b>
- When set to ON, it implies Basic mode where the user can log on using either Citrix Receiver or a browser and get access to the published apps configured at the XenApp/XenDEsktop environment pointed out by the WIHome parameter. Users are not allowed to connect using the NetScaler Gateway Plug-in and end point scans cannot be configured. Number of users that can log in and access the apps are not limited by the license in this mode.
- When set to OFF, it implies Smart Access mode where the user can log on using either Citrix Receiver or a browser or a NetScaler Gateway Plug-in. The admin can configure end point scans to be run on the client systems and then use the results to control access to the published apps. In this mode, the client can connect to the gateway in other client modes namely VPN and CVPN. Number of users that can log in and access the resources are limited by the CCU licenses in this mode.
Possible values: ON, OFF
Default value: OFF

<b>icaProxySessionMigration</b>
This option determines if an existing ICA Proxy session is transferred when the user logs on from another device.
Possible values: ON, OFF
Default value: OFF

<b>dtls</b>
This option starts/stops the turn service on the vserver
Possible values: ON, OFF
Default value: OFF

<b>loginOnce</b>
This option enables/disables seamless SSO for this Vserver.
Possible values: ON, OFF
Default value: OFF

<b>deviceCert</b>
Indicates whether device certificate check as a part of EPA is on or off.
Possible values: ON, OFF
Default value: OFF

<b>certkeyNames</b>
Name of the certificate key that was bound to the corresponding SSL virtual server as the Certificate Authority for the device certificate

<b>downStateFlush</b>
Close existing connections when the virtual server is marked DOWN, which means the server might have timed out. Disconnecting existing connections frees resources and in certain cases speeds recovery of overloaded load balancing setups. Enable this setting on servers in which the connections can safely be closed when they are marked DOWN.  Do not enable DOWN state flush on servers that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>Listenpolicy</b>
String specifying the listen policy for the NetScaler Gateway virtual server. Can be either a named expression or a default syntax expression. The NetScaler Gateway virtual server processes only the traffic for which the expression evaluates to true.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server, the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Minimum value: 0
Maximum value: 100

<b>tcpProfileName</b>
Name of the TCP profile to assign to this virtual server.

<b>httpProfileName</b>
Name of the HTTP profile to assign to this virtual server.
Default value: "nshttp_default_strict_validation"

<b>comment</b>
Any comments associated with the virtual server.

<b>appflowLog</b>
Log AppFlow records that contain standard NetFlow or IPFIX information, such as time stamps for the beginning and end of a flow, packet count, and byte count. Also log records that contain application-level information, such as HTTP web addresses, HTTP request methods and response status codes, server response time, and latency.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If this parameter is set to ACTIVE, respond only if the virtual server is available. With the PASSIVE setting, respond even if the virtual server is not available.
Possible values: PASSIVE, ACTIVE
Default value: PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers.
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: PASSIVE

<b>netProfile</b>
The name of the network profile.

<b>cginfraHomePageRedirect</b>
When client requests ShareFile resources and NetScaler Gateway detects that the user is unauthenticated or the user session has expired, disabling this option takes the user to the originally requested ShareFile resource after authentication (instead of taking the user to the default VPN home page)
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxLoginAttempts</b>
Maximum number of logon attempts
Minimum value: 1
Maximum value: 255

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts
Minimum value: 1

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP&gt;:&lt;source port&gt;::&lt;destination IP&gt;:&lt;destination port&gt;) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to coexist on the NetScaler appliance.
Possible values: ON, OFF

<b>deploymentType</b>

<b>rdpServerProfileName</b>
Name of the RDP server profile associated with the vserver.

<b>WindowsEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win
Possible values: Always, Essential, Never

<b>LinuxEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux
Possible values: Always, Essential, Never

<b>MacEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac
Possible values: Always, Essential, Never

<b>userDomains</b>
List of user domains specified as comma seperated value



##Example

The following example creates a VPN virtual server named myvpnvip which supports SSL protocols and with AAA functionality enabled: vserver myvpnvip SSL 65.219.17.34 443 -aaa ON

##rm vpn vserver

Removes a NetScaler Gateway virtual server. Policies that are bound to the virtual server are automatically unbound.


##Synopsys

rm vpn vserver &lt;name>@ ...


##Arguments

<b>name</b>
Name of the virtual server to remove.



##Example

rm vserver vpn_vip

##set vpn vserver

Modifies the specified parameters of a NetScaler Gateway virtual server.


##Synopsys

set vpn vserver &lt;name> [-IPAddress &lt;ip_addr|ipv6_addr|*>] [-authentication ( ON | OFF )] [-doubleHop ( ENABLED | DISABLED )] [-icaOnly ( ON | OFF )] [-icaProxySessionMigration ( ON | OFF )] [-dtls ( ON | OFF )] [-loginOnce ( ON | OFF )] [-deviceCert ( ON | OFF )  [-certkeyNames &lt;string>]] [-maxAAAUsers &lt;positive_integer>] [-downStateFlush ( ENABLED | DISABLED )] [-Listenpolicy &lt;expression>] [-Listenpriority &lt;positive_integer>] [-tcpProfileName &lt;string>] [-httpProfileName &lt;string>] [-comment &lt;string>] [-appflowLog ( ENABLED | DISABLED )] [-icmpVsrResponse ( PASSIVE | ACTIVE )] [-RHIstate ( PASSIVE | ACTIVE )] [-netProfile &lt;string>] [-cginfraHomePageRedirect ( ENABLED | DISABLED )] [-maxLoginAttempts &lt;positive_integer>] [-rdpServerProfileName &lt;string>] [-failedLoginTimeout &lt;mins>] [-l2Conn ( ON | OFF )] [-WindowsEPAPluginUpgrade &lt;WindowsEPAPluginUpgrade>] [-MacEPAPluginUpgrade &lt;MacEPAPluginUpgrade>] [-LinuxEPAPluginUpgrade &lt;LinuxEPAPluginUpgrade>] [-userDomains &lt;string>]


##Arguments

<b>name</b>
Name of the virtual server to modify.

<b>IPAddress</b>
IPv4 or IPv6 address of the NetScaler Gateway virtual server. Usually a public IP address. User devices send connection requests to this IP address.

<b>authentication</b>
Require authentication for users connecting to NetScaler Gateway.
Possible values: ON, OFF
Default value: ON

<b>doubleHop</b>
Use the NetScaler Gateway appliance in a double-hop configuration. A double-hop deployment provides an extra layer of security for the internal network by using three firewalls to divide the DMZ into two stages. Such a deployment can have one appliance in the DMZ and one appliance in the secure network.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>icaOnly</b>
- When set to ON, it implies Basic mode where the user can log on using either Citrix Receiver or a browser and get access to the published apps configured at the XenApp/XenDEsktop environment pointed out by the WIHome parameter. Users are not allowed to connect using the NetScaler Gateway Plug-in and end point scans cannot be configured. Number of users that can log in and access the apps are not limited by the license in this mode.
- When set to OFF, it implies Smart Access mode where the user can log on using either Citrix Receiver or a browser or a NetScaler Gateway Plug-in. The admin can configure end point scans to be run on the client systems and then use the results to control access to the published apps. In this mode, the client can connect to the gateway in other client modes namely VPN and CVPN. Number of users that can log in and access the resources are limited by the CCU licenses in this mode.
Possible values: ON, OFF
Default value: OFF

<b>icaProxySessionMigration</b>
This option determines if an existing ICA Proxy session is transferred when the user logs on from another device.
Possible values: ON, OFF
Default value: OFF

<b>dtls</b>
This option starts/stops the turn service on the vserver
Possible values: ON, OFF
Default value: OFF

<b>loginOnce</b>
This option enables/disables seamless SSO for this Vserver.
Possible values: ON, OFF
Default value: OFF

<b>deviceCert</b>
Indicates whether device certificate check as a part of EPA is enabled or not.
Possible values: ON, OFF
Default value: OFF

<b>certkeyNames</b>
Name of the certkey which was bound to the corresponding SSL virtual server as the Certificate Authority for the device certificate

<b>maxAAAUsers</b>
Maximum number of concurrent user sessions allowed on this virtual server. The actual number of users allowed to log on to this virtual server depends on the total number of user licenses.
Minimum value: 0

<b>downStateFlush</b>
Close existing connections when the virtual server is marked DOWN, which means the server might have timed out. Disconnecting existing connections frees resources and in certain cases speeds recovery of overloaded load balancing setups. Enable this setting on servers in which the connections can safely be closed when they are marked DOWN.  Do not enable DOWN state flush on servers that must complete their transactions.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>Listenpolicy</b>
String specifying the listen policy for the NetScaler Gateway virtual server. Can be either a named expression or a default syntax expression. The NetScaler Gateway virtual server processes only the traffic for which the expression evaluates to true.
Default value: "none"

<b>Listenpriority</b>
Integer specifying the priority of the listen policy. A higher number specifies a lower priority. If a request matches the listen policies of more than one virtual server, the virtual server whose listen policy has the highest priority (the lowest priority number) accepts the request.
Default value: 101
Minimum value: 0
Maximum value: 100

<b>tcpProfileName</b>
Name of the TCP profile to assign to this virtual server.

<b>httpProfileName</b>
Name of the HTTP profile to assign to this virtual server.
Default value: "nshttp_default_strict_validation"

<b>comment</b>
Any comments associated with the virtual server.

<b>appflowLog</b>
Log AppFlow records that contain standard NetFlow or IPFIX information, such as time stamps for the beginning and end of a flow, packet count, and byte count. Also log records that contain application-level information, such as HTTP web addresses, HTTP request methods and response status codes, server response time, and latency.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If this parameter is set to ACTIVE, respond only if the virtual server is available. With the PASSIVE setting, respond even if the virtual server is not available.
Possible values: PASSIVE, ACTIVE
Default value: PASSIVE

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers.
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance injects even if one virtual server set to ACTIVE is UP.
Possible values: PASSIVE, ACTIVE
Default value: PASSIVE

<b>netProfile</b>
The name of the network profile.

<b>cginfraHomePageRedirect</b>
When client requests ShareFile resources and NetScaler Gateway detects that the user is unauthenticated or the user session has expired, disabling this option takes the user to the originally requested ShareFile resource after authentication (instead of taking the user to the default VPN home page)
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>maxLoginAttempts</b>
Maximum number of logon attempts
Minimum value: 1
Maximum value: 255

<b>rdpServerProfileName</b>
Name of the RDP server profile associated with the vserver.

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts
Minimum value: 1

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP&gt;:&lt;source port&gt;::&lt;destination IP&gt;:&lt;destination port&gt;) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to coexist on the NetScaler appliance.
Possible values: ON, OFF

<b>WindowsEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win
Possible values: Always, Essential, Never

<b>MacEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac
Possible values: Always, Essential, Never

<b>LinuxEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux
Possible values: Always, Essential, Never

<b>userDomains</b>
List of user domains specified as comma seperated value



##unset vpn vserver

Use this command to remove vpn vserver settings.Refer to the set vpn vserver command for meanings of the arguments.


##Synopsys

unset vpn vserver &lt;name> [-authentication] [-doubleHop] [-icaOnly] [-icaProxySessionMigration] [-dtls] [-loginOnce] [-deviceCert] [-certkeyNames] [-maxAAAUsers] [-downStateFlush] [-Listenpolicy] [-Listenpriority] [-tcpProfileName] [-httpProfileName] [-comment] [-appflowLog] [-icmpVsrResponse] [-RHIstate] [-netProfile] [-cginfraHomePageRedirect] [-maxLoginAttempts] [-rdpServerProfileName] [-l2Conn] [-WindowsEPAPluginUpgrade] [-MacEPAPluginUpgrade] [-LinuxEPAPluginUpgrade] [-userDomains]


##bind vpn vserver

Binds attributes to the specified NetScaler Gateway virtual server.


##Synopsys

bind vpn vserver &lt;name> [-policy &lt;string>  [-priority &lt;positive_integer>]  [-secondary]  [-groupExtraction]  [-gotoPriorityExpression &lt;expression>]  [-type &lt;type>]] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask> ] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>] [-staServer &lt;URL>  [-staAddressType ( IPV4 | IPV6 )]] [-appController &lt;URL>] [-sharefile &lt;string>] [-portaltheme &lt;string>] [-eula &lt;string>]


##Arguments

<b>name</b>
Name of the virtual server.

<b>policy</b>
Name of a policy to bind to the virtual server (for example, the name of an authentication, session, or endpoint analysis policy).

<b>priority</b>
Integer specifying the policy's priority. The lower the number, the higher the priority. Policies are evaluated in the order of their priority numbers.
Minimum value: 0

<b>secondary</b>
Binds the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only via a primary authentication method but also via a secondary authentication method. User groups are aggregated across both. The user name must be exactly the same for both authentication methods, but they can require different passwords.

<b>groupExtraction</b>
Binds the authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called if primary and/or secondary authentication has succeeded.

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
*  If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
Bind point to which to bind the policy. Applies only to rewrite and cache policies. If you do not set this parameter, the policy is bound to REQ_DEFAULT or RES_DEFAULT, depending on whether the policy rule is a response-time or a request-time expression.
Possible values: REQUEST, RESPONSE, ICA_REQUEST, OTHERTCP_REQUEST

<b>intranetApplication</b>
Name of the application to bind to the virtual server. Intranet applications are used to enable access to selected applications located in the internal network. They are required for any user connecting with the NetScaler Gateway Plug-in for Java.

<b>nextHopServer</b>
Name of the next hop server to bind to the virtual server.

<b>urlName</b>
Web address of the next hop virtual server to bind to the virtual server.

<b>intranetIP</b>
The network ID for the range of intranet IP addresses or individual intranet IP addresses to be bound to the virtual server.

<b>netmask</b>
A range of IP addresses in an address pool, bound to a virtual server.  When users log on, NetScaler Gateway assigns an IP address from the pool.

<b>intranetIP6</b>
The network id for the range of intranet IP6 addresses or individual intranet ip to be bound to the vserver.

<b>numaddr</b>
A range of IP addresses in an address pool, bound to a virtual server.  When users log on, Access Gateway assigns an IP address from the pool.
Minimum value: 1

<b>staServer</b>
Web address of the Secure Ticket Authority (STA) server, in the following format: 'http(s)://FQDN/URLPATH'

<b>staAddressType</b>
Type of the STA server address(ipv4/v6).
Possible values: IPV4, IPV6

<b>appController</b>
App Controller server, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server, in the format 'IP:PORT / FQDN:PORT'

<b>portaltheme</b>
Portal theme applicable to vpn vserver

<b>eula</b>
Eula applicable to vpn vserver



##unbind vpn vserver

Unbinds the specified attributes from a virtual server.


##Synopsys

unbind vpn vserver &lt;name> [-policy &lt;string>  [-secondary]  [-groupExtraction]  [-type &lt;type>]] [-intranetApplication &lt;string>] [-nextHopServer &lt;string>] [-urlName &lt;string>] [-intranetIP &lt;ip_addr>  &lt;netmask>] [-intranetIP6 &lt;ip_addr|ipv6_addr|*>  &lt;numaddr>] [-staServer &lt;URL>] [-appController &lt;URL>] [-sharefile &lt;string>] [-portaltheme &lt;string>] [-eula &lt;string>]


##Arguments

<b>name</b>
Name of the virtual server from which to unbind an attribute.

<b>policy</b>
Name of the policy to unbind from the virtual server.

<b>secondary</b>
Binds the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only via a primary authentication method but also via a secondary authentication method. User groups are aggregated across both. The user name must be exactly the same for both authentication methods, but they can require different passwords.

<b>groupExtraction</b>
Binds the authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called if primary and/or secondary authentication has succeeded.

<b>type</b>
Bind point from which to unbind the policy.
Possible values: REQUEST, RESPONSE, ICA_REQUEST, OTHERTCP_REQUEST

<b>intranetApplication</b>
Name of intranet application to unbind from the virtual server.

<b>nextHopServer</b>
Name of the next hop server to remove.

<b>urlName</b>
Web address of the next hop virtual server to unbind.

<b>intranetIP</b>
The range of IP addresses to unbind from the virtual server.

<b>netmask</b>
The netmask of the intranet IP address or range.

<b>intranetIP6</b>
The range of IP addresses to unbind from the virtual server.

<b>numaddr</b>
The number of ipv6 addresses
Minimum value: 1

<b>staServer</b>
Web address of the Secure Ticket Authority (STA) server to remove, in the following format: 'http(s)://FQDN/URLPATH'

<b>appController</b>
App Controller server to be removed, in the format 'http(s)://IP/FQDN'

<b>sharefile</b>
ShareFile server to be removed, in the format 'IP:PORT / FQDN:PORT'

<b>portaltheme</b>
Name of the Theme to be unbound to vpn vserver

<b>eula</b>
Name of the Theme to be unbound to vpn vserver



##enable vpn vserver

Enables a NetScaler Gateway virtual server.Note: Virtual servers, when added, are enabled by default.


##Synopsys

enable vpn vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server to be enabled.



##Example

enable vserver vpn1

##disable vpn vserver

Disables a NetScaler Gateway virtual server. The virtual server is taken out of service.


##Synopsys

disable vpn vserver &lt;name>@


##Arguments

<b>name</b>
Name of the virtual server to be disabled. The NetScaler Gateway still responds to ARP and/or PING requests for the IP address of the virtual server. You can enable the NetScaler Gateway virtual server again at any time, because the virtual server is still configured.



##Example

disable vserver lb_vip

##show vpn vserver

Displays information about all the configured NetScaler Gateway virtual servers, or displays detailed information about the specified NetScaler Gateway virtual server.


##Synopsys

show vpn vserver [&lt;name>]show vpn vserver stats - alias for 'stat vpn vserver'


##Arguments

<b>name</b>
Name of the NetScaler Gateway virtual server for which to show detailed information.



##Outputs

<b>IPAddress</b>
The IP address of the virtual server.

<b>value</b>
Indicates whether or not the certificate is bound or if SSL offload is disabled.

<b>port</b>
The virtual TCP port of the VPN virtual server.

<b>range</b>
The range of VPN virtual server IP addresses. The new range of VPN virtual servers will have IP addresses consecutively numbered, starting with the primary address specified with the &lt;ipaddress> argument.

<b>serviceType</b>
The VPN virtual server's protocol type. Currently, the only possible value is SSL.

<b>type</b>
Bindpoint to which the policy is bound.

<b>state</b>
State of the virtual server. If the virtual server is disabled, requests are not processed.

<b>status</b>
Whether or not this virtual server responds to ARPs and whether or not round-robin selection is temporarily in effect.

<b>cacheType</b>
Virtual server cache type. The options are: TRANSPARENT, REVERSE, and FORWARD.

<b>redirect</b>
The cache redirect policy.
The valid redirect policies are:
l.        CACHE - Directs all requests to the cache.
2.        POLICY - Applies cache redirection policy to determine whether the request should be directed to the cache or origin. This is the default setting.
3.        ORIGIN - Directs all requests to the origin server.

<b>precedence</b>
This argument is used only when configuring content switching on the specified virtual server. This is applicable only
if both the URL and RULE-based policies have been configured on the same virtual server.
It specifies the type of policy (URL or RULE) that takes precedence on the content switching virtual server. The default setting is RULE.
l        URL - In this case, the incoming request is matched against the URL-based policies before the rule-based policies.
l        RULE - In this case, the incoming request is matched against the rule-based policies before the URL-based policies.
For all URL-based policies, the precedence hierarchy is:
1.        Domain and exact URL
2.        Domain, prefix, and suffix
3.        Domain and suffix
4.        Domain and prefix
5.        Domain only
6.        Exact URL
7.        Prefix and suffix
8.        Suffix only
9.        Prefix only
10.        Default

<b>redirectURL</b>
The URL where traffic is redirected if the virtual server in system becomes unavailable. WARNING!        Make sure that the domain you specify in the URL does not match the domain specified in the -d domainName argument of the ###add cs policy### command. If the same domain is specified in both arguments, the request will be continuously redirected to the same unavailable virtual server in the system. If so, the user may not get the requested content.

<b>authentication</b>
Indicates whether or not authentication is being applied to incoming users to the VPN.

<b>doubleHop</b>
Indicates whether double-hop functionality is enabled or not.

<b>icaOnly</b>
Indicates whether an ICA only license feature is enabled or not.

<b>icaProxySessionMigration</b>
This option determines if an existing ICA Proxy session is transferred when the user logs on from another device.

<b>dtls</b>
This option starts/stops Turn service on the vserver

<b>loginOnce</b>
This option enables/disables seamless SSO for this Vserver.

<b>advancedEpa</b>
Indicates whether advanced EPA feature is enabled or not.

<b>deviceCert</b>
Indicates whether device certificate check as a part of EPA is enabled or not.

<b>certkeyNames</b>
Name of the certificate key which was bound to the corresponding SSL virtual server as the Certificate Authority for the device certificate

<b>maxAAAUsers</b>
The maximum number of concurrent users allowed to log on into this virtual server at a time.

<b>curAAAUsers</b>
The number of current users logged on to this virtual server.

<b>curTotalUsers</b>
The total number of current users connected through this virtual server.

<b>domain</b>
The domain name of the server for which a service needs to be added. If the IP address has been specified, the domain name does not need to be specified.

<b>rule</b>
The name of the rule, or expression, if any, that policy for the VPN server is to use. Rules are combinations of expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide. The default rule is ns_true.

<b>policyName</b>
The name of the policy, if any, bound to the VPN virtual server.

<b>policy</b>
The name of the policy, if any, bound to the VPN virtual server.

<b>serviceName</b>
The name of the service, if any, to which the virtual server policy is bound.

<b>weight</b>
Weight for this service, if any. This weight is used when the system performs load balancing, giving greater priority to a specific service. It is useful when the services bound to a virtual server are of different capacity.

<b>cacheVserver</b>
The name of the default target cache virtual server, if any, to which requests are redirected.

<b>backupVServer</b>
The name of the backup VPN virtual server for this VPN virtual server.

<b>priority</b>
The priority, if any, of the VPN virtual server policy.

<b>cltTimeout</b>
The idle time, if any, in seconds after which the client connection is terminated.

<b>soMethod</b>
VPN client applications are allocated from a block of intranet IP addresses.
That block may be exhausted after a certain number of connections. This switch specifies the
method used to determine whether or not a new connection will spill over, or exhaust, the allocated block of
intranet IP addresses for that application. Possible values are CONNECTION or DYNAMICCONNECTION.
CONNECTION means that a static integer value is the hard limit for the spillover threshold. The spillover
threshold is described below. DYNAMICCONNECTION means that the spillover threshold is set according to
the maximum number of connections defined for the VPN virtual server.

<b>soThreshold</b>
VPN client applications are allocated from a block of intranet IP addresses.
That block may be exhausted after a certain number of connections.
The value of this option is the number of client connections after which the mapped IP address is used
as the client source IP address instead of an address from the allocated block of intranet IP addresses.

<b>soPersistence</b>
Whether or not cookie-based site persistance is enabled for this VPN vserver. Possible values are 'ConnectionProxy', HTTPRedirect, or NONE

<b>soPersistenceTimeOut</b>
The timeout, if any, for cookie-based site persistance of this VPN vserver.

<b>actType</b>

<b>intranetApplication</b>
The intranet VPN application.

<b>nextHopServer</b>
The name of the next hop server bound to the VPN virtual server.

<b>urlName</b>
The intranet URL.

<b>intranetIP</b>
The network ID for the range of intranet IP addresses or individual intranet IP addresses to be bound to the virtual server.

<b>netmask</b>
The netmask of the intranet IP address or range.

<b>intranetIP6</b>
The network id for the range of intranet IP6 addresses or individual intranet ip to be bound to the vserver.

<b>numaddr</b>
The number of ipv6 addresses

<b>staServer</b>
Configured Secure Ticketing Authority (STA) server.

<b>staAddressType</b>
Type of the STA server address(ipv4/v6).

<b>staAuthID</b>
Authority ID of the STA Server. Authority ID is used to match incoming STA tickets in the SOCKS/CGP protocol with the right STA server.

<b>appController</b>
Configured App Controller server in XenMobile deployment.

<b>sharefile</b>
Configured ShareFile server in XenMobile deployment. Format IP:PORT / FQDN:PORT

<b>useMIP</b>
Deprecated. See 'map' below.

<b>map</b>
Whether or not mapped IP addresses are ON or OFF. Mapped IP addresses are source IP addresses
for the virtual servers running on the NetScaler. Mapped IP addresses are used by the system to connect to the backend servers.

<b>downStateFlush</b>
Close existing connections when the virtual server is marked DOWN, which means the server might have timed out. Disconnecting existing connections frees resources and in certain cases speeds recovery of overloaded load balancing setups. Enable this setting on servers in which the connections can safely be closed when they are marked DOWN.  Do not enable DOWN state flush on servers that must complete their transactions.

<b>gotoPriorityExpression</b>
Next priority expression.

<b>disablePrimaryOnDown</b>
Tells whether traffic will continue reaching backup virtual servers even after the primary virtual server comes UP from DOWN state.

<b>Listenpolicy</b>
The string is listenpolicy configured for VPN vserver

<b>Listenpriority</b>
This parameter is the priority for listen policy of VPN Vserver.

<b>tcpProfileName</b>
Name of the TCP profile to assign to this virtual server.

<b>httpProfileName</b>
Name of the HTTP profile to assign to this virtual server.

<b>policySubType</b>

<b>stateflag</b>

<b>flags</b>

<b>comment</b>
Any comments associated with the virtual server.

<b>appflowLog</b>
Log AppFlow records that contain standard NetFlow or IPFIX information, such as time stamps for the beginning and end of a flow, packet count, and byte count. Also log records that contain application-level information, such as HTTP web addresses, HTTP request methods and response status codes, server response time, and latency.

<b>icmpVsrResponse</b>
Criterion for responding to PING requests sent to this virtual server. If this parameter is set to ACTIVE, respond only if the virtual server is available. With the PASSIVE setting, respond even if the virtual server is not available.

<b>RHIstate</b>
A host route is injected according to the setting on the virtual servers.
            * If set to PASSIVE on all the virtual servers that share the IP address, the appliance always injects the hostroute.
            * If set to ACTIVE on all the virtual servers that share the IP address, the appliance injects even if one virtual server is UP.
            * If set to ACTIVE on some virtual servers and PASSIVE on the others, the appliance injects even if one virtual server set to ACTIVE is UP.

<b>netProfile</b>
The name of the network profile.

<b>cginfraHomePageRedirect</b>
When client requests ShareFile resources and NetScaler Gateway detects that the user is unauthenticated or the user session has expired, disabling this option takes the user to the originally requested ShareFile resource after authentication (instead of taking the user to the default VPN home page)

<b>maxLoginAttempts</b>
Maximum number of logon attempts

<b>failedLoginTimeout</b>
Number of minutes an account will be locked if user exceeds maximum permissible attempts

<b>secondary</b>
Binds the authentication policy as the secondary policy to use in a two-factor configuration. A user must then authenticate not only via a primary authentication method but also via a secondary authentication method. User groups are aggregated across both. The user name must be exactly the same for both authentication methods, but they can require different passwords.

<b>groupExtraction</b>
Binds the authentication policy to a tertiary chain which will be used only for group extraction.  The user will not authenticate against this server, and this will only be called if primary and/or secondary authentication has succeeded.

<b>deploymentType</b>

<b>WindowsEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win

<b>LinuxEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux

<b>MacEPAPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac

<b>epaprofile</b>
Advanced EPA profile to bind

<b>epaprofileoptional</b>
Mark the EPA profile optional for preauthentication EPA profile. User would be shown a logon page even if the EPA profile fails to evaluate.

<b>rdpServerProfileName</b>
Name of the RDP server profile associated with the vserver.

<b>ngname</b>
Node group devno to which this authentication virtual sever belongs

<b>vstype</b>
Virtual Server Type, such as Load Balancing, Content Switch, Cache Redirection

<b>l2Conn</b>
Use Layer 2 parameters (channel number, MAC address, and VLAN ID) in addition to the 4-tuple (&lt;source IP>:&lt;source port>::&lt;destination IP>:&lt;destination port>) that is used to identify a connection. Allows multiple TCP and non-TCP connections with the same 4-tuple to coexist on the NetScaler appliance.

<b>portaltheme</b>
Theme for gateway portal

<b>eula</b>
EULA for VPN vserver

<b>userDomains</b>
List of user domains specified as comma seperated value

<b>csVserver</b>
Name of the CS vserver to which the VPN vserver is bound

<b>devno</b>

<b>count</b>



##Example

show vpn vserver

##stat vpn vserver

Displays statistics for all NetScaler Gateway virtual servers, or displays detailed statistics for the specified NetScaler Gateway virtual server.


##Synopsys

stat vpn vserver [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the virtual server for which to show detailed statistics.

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

<b>IP address (IP)</b>
The IP address on which the service is running.

<b>Port (port)</b>
The port on which the service is running.

<b>Vserver protocol (Protocol)</b>
Protocol associated with the vserver

<b>State</b>
Current state of the server. Possible values are UP, DOWN, UNKNOWN, OFS(Out of Service), TROFS(Transition Out of Service), TROFS_DOWN(Down When going Out of Service)

<b>Requests (Req)</b>
Total number of requests received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Responses (Rsp)</b>
Number of responses received on this service or virtual server. (This applies to HTTP/SSL services and servers.)

<b>Request bytes (Reqb)</b>
Total number of request bytes received on this service or virtual server.

<b>Response bytes (Rspb)</b>
Number of response bytes received by this service or virtual server.



##Related Commands

<ul><li><a href="../../..//">stat vpn</a></li></ul>



##rename vpn vserver

Renames a NetScaler Gateway virtual server.


##Synopsys

rename vpn vserver &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Name of the NetScaler Gateway virtual server.

<b>newName</b>
New name for the NetScaler Gateway virtual server. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my server" or 'my server').



##Example

rename vpn vserver vpn1 vpn1new

##check vpn vserver

Invokes Cerebro executable for connectivity checks for the servers bound to a VPN virtual server


##Synopsys

check vpn vserver &lt;name>


##Arguments

<b>name</b>
Name of the NetScaler Gateway virtual server.



##Outputs

<b>response</b>



##Example

check vpn vserver &lt;vserver name&gt;

