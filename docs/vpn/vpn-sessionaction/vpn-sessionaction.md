#vpn sessionAction

The following operations can be performed on "vpn sessionAction":


[add](#add-vpn-sessionaction) | [rm](#rm-vpn-sessionaction) | [set](#set-vpn-sessionaction) | [unset](#unset-vpn-sessionaction) | [show](#show-vpn-sessionaction)

##add vpn sessionAction

Adds a session profile (action) to bind to a session policy that is applied to a user session if the policy expression conditions are met.


##Synopsys

add vpn sessionAction &lt;name> [-userAccounting &lt;string>] [-httpPort &lt;port> ...] [-winsIP &lt;ip_addr>] [-dnsVserverName &lt;string>] [-splitDns &lt;splitDns>] [-sessTimeout &lt;mins>] [-clientSecurity &lt;expression>  [-clientSecurityGroup &lt;string>]  [-clientSecurityMessage &lt;string>]] [-clientSecurityLog ( ON | OFF )] [-splitTunnel &lt;splitTunnel>] [-localLanAccess ( ON | OFF )] [-rfc1918 ( ON | OFF )] [-killConnections ( ON | OFF )] [-transparentInterception ( ON | OFF )] [-defaultAuthorizationAction ( ALLOW | DENY )] [-authorizationGroup &lt;string>] [-Smartgroup &lt;string>] [-clientIdleTimeout &lt;mins>] [-proxy &lt;proxy>] [-allProtocolProxy &lt;string> | -httpProxy &lt;string> | -ftpProxy &lt;string> | -socksProxy &lt;string> | -gopherProxy &lt;string> | -sslProxy &lt;string>] [-proxyException &lt;string>] [-proxyLocalBypass ( ENABLED | DISABLED )] [-clientCleanupPrompt ( ON | OFF )] [-forceCleanup &lt;forceCleanup> ...] [-clientOptions &lt;clientOptions> ...] [-clientConfiguration &lt;clientConfiguration> ...] [-SSO ( ON | OFF )] [-ssoCredential ( PRIMARY | SECONDARY )] [-windowsAutoLogon ( ON | OFF )] [-useMIP ( NS | OFF )] [-useIIP &lt;useIIP>] [-clientDebug &lt;clientDebug>] [-loginScript &lt;input_filename>] [-logoutScript &lt;input_filename>] [-homePage &lt;URL>] [-icaProxy ( ON | OFF )] [-wihome &lt;URL>  [-wihomeAddressType ( IPV4 | IPV6 )]] [-citrixReceiverHome &lt;URL>] [-wiPortalMode ( NORMAL | COMPACT )] [-ClientChoices ( ON | OFF )] [-iipDnsSuffix &lt;string>] [-forcedTimeout &lt;mins>] [-forcedTimeoutWarning &lt;mins>] [-ntDomain &lt;string>] [-clientlessVpnMode &lt;clientlessVpnMode>] [-emailHome &lt;URL>] [-clientlessModeUrlEncoding &lt;clientlessModeUrlEncoding>] [-clientlessPersistentCookie &lt;clientlessPersistentCookie>] [-allowedLoginGroups &lt;string>] [-SecureBrowse ( ENABLED | DISABLED )] [-storefronturl &lt;string>] [-kcdAccount &lt;string>] [-rdpClientProfileName &lt;string>] [-WindowsPluginUpgrade &lt;WindowsPluginUpgrade>] [-MacPluginUpgrade &lt;MacPluginUpgrade>] [-LinuxPluginUpgrade &lt;LinuxPluginUpgrade>] [-iconWithReceiver ( ON | OFF )]


##Arguments

<b>name</b>
Name for the NetScaler Gateway profile (action). Must begin with an ASCII alphabetic or underscore (_) character, and must consist only of ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the profile is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').

<b>userAccounting</b>
The name of the radiusPolicy to use for RADIUS user accounting info on the session.

<b>httpPort</b>
Destination port numbers other than port 80, added as a comma-separated list. Traffic to these ports is processed as HTTP traffic, which allows functionality, such as HTTP authorization and single sign-on to a web application to work.
Minimum value: 1

<b>winsIP</b>
WINS server IP address to add to NetScaler Gateway for name resolution.

<b>dnsVserverName</b>
Name of the DNS virtual server for the user session.

<b>splitDns</b>
Route the DNS requests to the local DNS server configured on the user device, or NetScaler Gateway (remote), or both.
Possible values: LOCAL, REMOTE, BOTH

<b>sessTimeout</b>
Number of minutes after which the session times out.
Minimum value: 1

<b>clientSecurity</b>
Specify the client security check for the user device to permit a NetScaler Gateway session. The web address or IP address is not included in the expression for the client security check.

<b>clientSecurityGroup</b>
The client security group that will be assigned on failure of the client security check. Users can in general be organized into Groups. In this case, the Client Security Group may have a more restrictive security policy.

<b>clientSecurityMessage</b>
The client security message that will be displayed on failure of the client security check.

<b>clientSecurityLog</b>
Set the logging of client security checks.
Possible values: ON, OFF

<b>splitTunnel</b>
Send, through the tunnel, traffic only for intranet applications that are defined in NetScaler Gateway. Route all other traffic directly to the Internet. The OFF setting routes all traffic through NetScaler Gateway. With the REVERSE setting, intranet applications define the network traffic that is not intercepted. All network traffic directed to internal IP addresses bypasses the VPN tunnel, while other traffic goes through NetScaler Gateway. Reverse split tunneling can be used to log all non-local LAN traffic. For example, if users have a home network and are logged on through the NetScaler Gateway Plug-in, network traffic destined to a printer or another device within the home network is not intercepted.
Possible values: ON, OFF, REVERSE

<b>localLanAccess</b>
Set local LAN access. If split tunneling is OFF, and you set local LAN access to ON, the local client can route traffic to its local interface. When the local area network switch is specified, this combination of switches is useful. The client can allow local LAN access to devices that commonly have non-routable addresses, such as local printers or local file servers.
Possible values: ON, OFF

<b>rfc1918</b>
As defined in the local area network, allow only the following local area network addresses to bypass the VPN tunnel when the local LAN access feature is enabled:
* 10.*.*.*,
* 172.16.*.*,
* 192.168.*.*
Possible values: ON, OFF

<b>killConnections</b>
Specify whether the NetScaler Gateway Plug-in should disconnect all preexisting connections, such as the connections existing before the user logged on to NetScaler Gateway, and prevent new incoming connections on the NetScaler Gateway Plug-in for Windows and MAC when the user is connected to NetScaler Gateway and split tunneling is disabled.
Possible values: ON, OFF

<b>transparentInterception</b>
Allow access to network resources by using a single IP address and subnet mask or a range of IP addresses. The OFF setting sets the mode to proxy, in which you configure destination and source IP addresses and port numbers. If you are using the NetScaler Gateway Plug-in for Windows, set this parameter to ON, in which the mode is set to transparent. If you are using the NetScaler Gateway Plug-in for Java, set this parameter to OFF.
Possible values: ON, OFF

<b>defaultAuthorizationAction</b>
Specify the network resources that users have access to when they log on to the internal network. The default setting for authorization is to deny access to all network resources. Citrix recommends using the default global setting and then creating authorization policies to define the network resources users can access. If you set the default authorization policy to DENY, you must explicitly authorize access to any network resource, which improves security.
Possible values: ALLOW, DENY

<b>authorizationGroup</b>
Comma-separated list of groups in which the user is placed when none of the groups that the user is a part of is configured on NetScaler Gateway. The authorization policy can be bound to these groups to control access to the resources.

<b>Smartgroup</b>
This is the group in which the user is placed when the sessionpolicy associated with this sessionaction succeeds. The vpn session policy will do the post auth EPA check and if the check succeeds the user is placed in the group specified with smartgroup. The is_member_of (http.req.user.is_member_of) expression can then be used with policies to check if EPA has passed on the user belonging to this smartgroup
Maximum value: 64

<b>clientIdleTimeout</b>
Time, in minutes, after which to time out the user session if NetScaler Gateway does not detect mouse or keyboard activity.
Minimum value: 1
Maximum value: 9999

<b>proxy</b>
Set options to apply proxy for accessing the internal resources. Available settings function as follows:
* BROWSER - Proxy settings are configured only in Internet Explorer and Firefox browsers.
* NS - Proxy settings are configured on the NetScaler appliance.
* OFF - Proxy settings are not configured.
Possible values: BROWSER, NS, OFF

<b>allProtocolProxy</b>
IP address of the proxy server to use for all protocols supported by NetScaler Gateway.

<b>httpProxy</b>
IP address of the proxy server to be used for HTTP access for all subsequent connections to the internal network.

<b>ftpProxy</b>
IP address of the proxy server to be used for FTP access for all subsequent connections to the internal network.

<b>socksProxy</b>
IP address of the proxy server to be used for SOCKS access for all subsequent connections to the internal network.

<b>gopherProxy</b>
IP address of the proxy server to be used for GOPHER access for all subsequent connections to the internal network.

<b>sslProxy</b>
IP address of the proxy server to be used for SSL access for all subsequent connections to the internal network.

<b>proxyException</b>
Proxy exception string that will be configured in the browser for bypassing the previously configured proxies. Allowed only if proxy type is Browser.

<b>proxyLocalBypass</b>
Bypass proxy server for local addresses option in Internet Explorer and Firefox proxy server settings.
Possible values: ENABLED, DISABLED

<b>clientCleanupPrompt</b>
Prompt for client-side cache clean-up when a client-initiated session closes.
Possible values: ON, OFF

<b>forceCleanup</b>
Force cache clean-up when the user closes a session. You can specify all, none, or any combination of the client-side items.

<b>clientOptions</b>
Display only the configured menu options when you select the "Configure NetScaler Gateway" option in the NetScaler Gateway Plug-in system tray icon for Windows.

<b>clientConfiguration</b>
Display only the configured tabs when you select the "Configure NetSCaler Gateway" option in the NetScaler Gateway Plug-in system tray icon for Windows.

<b>SSO</b>
Set single sign-on (SSO) for the session. When the user accesses a server, the user's logon credentials are passed to the server for authentication.
Possible values: ON, OFF

<b>ssoCredential</b>
Specify whether to use the primary or secondary authentication credentials for single sign-on to the server.
Possible values: PRIMARY, SECONDARY

<b>windowsAutoLogon</b>
Enable or disable the Windows Auto Logon for the session. If a VPN session is established after this setting is enabled, the user is automatically logged on by using Windows credentials after the system is restarted.
Possible values: ON, OFF

<b>useMIP</b>
Enable or disable the use of a unique IP address alias, or a mapped IP address, as the client IP address for each client session. Allow NetScaler Gateway to use the mapped IP address as an intranet IP address when all other IP addresses are not available. 
When IP pooling is configured and the mapped IP is used as an intranet IP address, the mapped IP address is used when an intranet IP address cannot be assigned.
Possible values: NS, OFF

<b>useIIP</b>
Define IP address pool options. Available settings function as follows: 
* SPILLOVER - When an address pool is configured and the mapped IP is used as an intranet IP address, the mapped IP address is used when an intranet IP address cannot be assigned. 
* NOSPILLOVER - When intranet IP addresses are enabled and the mapped IP address is not used, the Transfer Login page appears for users who have used all available intranet IP addresses. 
* OFF - Address pool is not configured.
Possible values: NOSPILLOVER, SPILLOVER, OFF

<b>clientDebug</b>
Set the trace level on NetScaler Gateway. Technical support technicians use these debug logs for in-depth debugging and troubleshooting purposes. Available settings function as follows: 
* DEBUG - Detailed debug messages are collected and written into the specified file.
* STATS - Application audit level error messages and debug statistic counters are written into the specified file. 
* EVENTS - Application audit-level error messages are written into the specified file. 
* OFF - Only critical events are logged into the Windows Application Log.
Possible values: debug, stats, events, OFF

<b>loginScript</b>
Path to the logon script that is run when a session is established. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>logoutScript</b>
Path to the logout script. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>homePage</b>
Web address of the home page that appears when users log on. Otherwise, users receive the default home page for NetScaler Gateway, which is the Access Interface.

<b>icaProxy</b>
Enable ICA proxy to configure secure Internet access to servers running Citrix XenApp or XenDesktop by using Citrix Receiver instead of the NetScaler Gateway Plug-in.
Possible values: ON, OFF

<b>wihome</b>
Web address of the Web Interface server, such as http://&lt;ipAddress&gt;/Citrix/XenApp, or Receiver for Web, which enumerates the virtualized resources, such as XenApp, XenDesktop, and cloud applications. This web address is used as the home page in ICA proxy mode. 
If Client Choices is ON, you must configure this setting. Because the user can choose between FullClient and ICAProxy, the user may see a different home page. An Internet web site may appear if the user gets the FullClient option, or a Web Interface site if the user gets the ICAProxy option. If the setting is not configured, the XenApp option does not appear as a client choice.

<b>wihomeAddressType</b>
Type of the wihome address(IPV4/V6)
Possible values: IPV4, IPV6

<b>citrixReceiverHome</b>
Web address for the Citrix Receiver home page. Configure NetScaler Gateway so that when users log on to the appliance, the NetScaler Gateway Plug-in opens a web browser that allows single sign-on to the Citrix Receiver home page.

<b>wiPortalMode</b>
Layout on the Access Interface. The COMPACT value indicates the use of small icons.
Possible values: NORMAL, COMPACT

<b>ClientChoices</b>
Provide users with multiple logon options. With client choices, users have the option of logging on by using the NetScaler Gateway Plug-in for Windows, NetScaler Gateway Plug-in for Java, the Web Interface, or clientless access from one location. Depending on how NetScaler Gateway is configured, users are presented with up to three icons for logon choices. The most common are the NetScaler Gateway Plug-in for Windows, Web Interface, and clientless access.
Possible values: ON, OFF

<b>iipDnsSuffix</b>
An intranet IP DNS suffix. When a user logs on to NetScaler Gateway and is assigned an IP address, a DNS record for the user name and IP address combination is added to the NetScaler Gateway DNS cache. You can configure a DNS suffix to append to the user name when the DNS record is added to the cache. You can reach to the host from where the user is logged on by using the user's name, which can be easier to remember than an IP address. When the user logs off from NetScaler Gateway, the record is removed from the DNS cache.

<b>forcedTimeout</b>
Force a disconnection from the NetScaler Gateway Plug-in with NetScaler Gateway after a specified number of minutes. If the session closes, the user must log on again.
Minimum value: 1
Maximum value: 65535

<b>forcedTimeoutWarning</b>
Number of minutes to warn a user before the user session is disconnected.
Minimum value: 1
Maximum value: 255

<b>ntDomain</b>
Single sign-on domain to use for single sign-on to applications in the internal network. This setting can be overwritten by the domain that users specify at the time of logon or by the domain that the authentication server returns.

<b>clientlessVpnMode</b>
Enable clientless access for web, XenApp or XenDesktop, and FileShare resources without installing the NetScaler Gateway Plug-in. Available settings function as follows: 
* ON - Allow only clientless access. 
* OFF - Allow clientless access after users log on with the NetScaler Gateway Plug-in. 
* DISABLED - Do not allow clientless access.
Possible values: ON, OFF, DISABLED

<b>emailHome</b>
Web address for the web-based email, such as Outlook Web Access.

<b>clientlessModeUrlEncoding</b>
When clientless access is enabled, you can choose to encode the addresses of internal web applications or to leave the address as clear text. Available settings function as follows: 
* OPAQUE - Use standard encoding mechanisms to make the domain and protocol part of the resource unclear to users. 
* CLEAR - Do not encode the web address and make it visible to users. 
* ENCRYPT - Allow the domain and protocol to be encrypted using a session key. When the web address is encrypted, the URL is different for each user session for the same web resource. If users bookmark the encoded web address, save it in the web browser and then log off, they cannot connect to the web address when they log on and use the bookmark. If users save the encrypted bookmark in the Access Interface during their session, the bookmark works each time the user logs on.
Possible values: TRANSPARENT, OPAQUE, ENCRYPT

<b>clientlessPersistentCookie</b>
State of persistent cookies in clientless access mode. Persistent cookies are required for accessing certain features of SharePoint, such as opening and editing Microsoft Word, Excel, and PowerPoint documents hosted on the SharePoint server. A persistent cookie remains on the user device and is sent with each HTTP request. NetScaler Gateway encrypts the persistent cookie before sending it to the plug-in on the user device, and refreshes the cookie periodically as long as the session exists. The cookie becomes stale if the session ends. Available settings function as follows: 
* ALLOW - Enable persistent cookies. Users can open and edit Microsoft documents stored in SharePoint. 
* DENY - Disable persistent cookies. Users cannot open and edit Microsoft documents stored in SharePoint. 
* PROMPT - Prompt users to allow or deny persistent cookies during the session. Persistent cookies are not required for clientless access if users do not connect to SharePoint.
Possible values: ALLOW, DENY, PROMPT

<b>allowedLoginGroups</b>
Specify groups that have permission to log on to NetScaler Gateway. Users who do not belong to this group or groups are denied access even if they have valid credentials.

<b>SecureBrowse</b>
Allow users to connect through NetScaler Gateway to network resources from iOS and Android mobile devices with Citrix Receiver. Users do not need to establish a full VPN tunnel to access resources in the secure network.
Possible values: ENABLED, DISABLED

<b>storefronturl</b>
Web address for StoreFront to be used in this session for enumeration of resources from XenApp or XenDesktop.

<b>kcdAccount</b>
The kcd account details to be used in SSO

<b>rdpClientProfileName</b>
Name of the RDP profile associated with the vserver.

<b>WindowsPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win
Possible values: Always, Essential, Never

<b>MacPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac
Possible values: Always, Essential, Never

<b>LinuxPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux
Possible values: Always, Essential, Never

<b>iconWithReceiver</b>
Option to decide whether to show plugin icon along with receiver
Possible values: ON, OFF



##rm vpn sessionAction

Removes an action that was previously added to a session policy.


##Synopsys

rm vpn sessionAction &lt;name>


##Arguments

<b>name</b>
Name of the action to remove.



##set vpn sessionAction

Modifies an action that was previously added to a session policy that is applied to a user session if the policy expression conditions are met.


##Synopsys

set vpn sessionAction &lt;name> [-userAccounting &lt;string>] [-httpPort &lt;port> ...] [-winsIP &lt;ip_addr>] [-dnsVserverName &lt;string>] [-splitDns &lt;splitDns>] [-sessTimeout &lt;mins>] [-clientSecurity &lt;expression>  [-clientSecurityGroup &lt;string>]  [-clientSecurityMessage &lt;string>]] [-clientSecurityLog ( ON | OFF )] [-splitTunnel &lt;splitTunnel>] [-localLanAccess ( ON | OFF )] [-rfc1918 ( ON | OFF )] [-killConnections ( ON | OFF )] [-transparentInterception ( ON | OFF )] [-defaultAuthorizationAction ( ALLOW | DENY )] [-authorizationGroup &lt;string>] [-Smartgroup &lt;string>] [-clientIdleTimeout &lt;mins>] [-proxy &lt;proxy>] [-allProtocolProxy &lt;string> | -httpProxy &lt;string> | -ftpProxy &lt;string> | -socksProxy &lt;string> | -gopherProxy &lt;string> | -sslProxy &lt;string>] [-proxyException &lt;string>] [-proxyLocalBypass ( ENABLED | DISABLED )] [-clientCleanupPrompt ( ON | OFF )] [-forceCleanup &lt;forceCleanup> ...] [-clientOptions &lt;clientOptions> ...] [-clientConfiguration &lt;clientConfiguration> ...] [-SSO ( ON | OFF )] [-ssoCredential ( PRIMARY | SECONDARY )] [-windowsAutoLogon ( ON | OFF )] [-useMIP ( NS | OFF )] [-useIIP &lt;useIIP>] [-clientDebug &lt;clientDebug>] [-loginScript &lt;input_filename>] [-logoutScript &lt;input_filename>] [-homePage &lt;URL>] [-icaProxy ( ON | OFF )] [-wihome &lt;URL>  [-wihomeAddressType ( IPV4 | IPV6 )]] [-citrixReceiverHome &lt;URL>] [-wiPortalMode ( NORMAL | COMPACT )] [-ClientChoices ( ON | OFF )] [-iipDnsSuffix &lt;string>] [-forcedTimeout &lt;mins>] [-forcedTimeoutWarning &lt;mins>] [-ntDomain &lt;string>] [-clientlessVpnMode &lt;clientlessVpnMode>] [-emailHome &lt;URL>] [-clientlessModeUrlEncoding &lt;clientlessModeUrlEncoding>] [-clientlessPersistentCookie &lt;clientlessPersistentCookie>] [-allowedLoginGroups &lt;string>] [-SecureBrowse ( ENABLED | DISABLED )] [-storefronturl &lt;string>] [-kcdAccount &lt;string>] [-rdpClientProfileName &lt;string>] [-WindowsPluginUpgrade &lt;WindowsPluginUpgrade>] [-MacPluginUpgrade &lt;MacPluginUpgrade>] [-LinuxPluginUpgrade &lt;LinuxPluginUpgrade>] [-iconWithReceiver ( ON | OFF )]


##Arguments

<b>name</b>
The name of the vpn session action.

<b>userAccounting</b>
Name of RADIUS Policy to use for user accounting

<b>httpPort</b>
Destination port numbers other than port 80, added as a comma-separated list. Traffic to these ports is processed as HTTP traffic, which allows functionality, such as HTTP authorization and single sign-on to a web application to work.
Minimum value: 1

<b>winsIP</b>
The WINS server ip address.

<b>dnsVserverName</b>
Name of the DNS virtual server for the user session.

<b>splitDns</b>
Route the DNS requests to the local DNS server configured on the user device, or NetScaler Gateway (remote), or both.
Possible values: LOCAL, REMOTE, BOTH

<b>sessTimeout</b>
Number of minutes after which the session times out.
Minimum value: 1

<b>clientSecurity</b>
Specify the client security check for the user device to permit a NetScaler Gateway session. The web address or IP address is not included in the expression for the client security check.

<b>clientSecurityGroup</b>
The client security group that will be assigned on failure of the client security check. Users can in general be organized into Groups. In this case, the Client Security Group may have a more restrictive security policy.

<b>clientSecurityMessage</b>
The client security message that will be displayed on failure of the client security check.

<b>clientSecurityLog</b>
Set the logging of client security checks.
Possible values: ON, OFF

<b>splitTunnel</b>
Send, through the tunnel, traffic only for intranet applications that are defined in NetScaler Gateway. Route all other traffic directly to the Internet. The OFF setting routes all traffic through NetScaler Gateway. With the REVERSE setting, intranet applications define the network traffic that is not intercepted. All network traffic directed to internal IP addresses bypasses the VPN tunnel, while other traffic goes through NetScaler Gateway. Reverse split tunneling can be used to log all non-local LAN traffic. For example, if users have a home network and are logged on through the NetScaler Gateway Plug-in, network traffic destined to a printer or another device within the home network is not intercepted.
Possible values: ON, OFF, REVERSE

<b>localLanAccess</b>
Set local LAN access. If split tunneling is OFF, and you set local LAN access to ON, the local client can route traffic to its local interface. When the local area network switch is specified, this combination of switches is useful. The client can allow local LAN access to devices that commonly have non-routable addresses, such as local printers or local file servers.
Possible values: ON, OFF

<b>rfc1918</b>
As defined in the local area network, allow only the following local area network addresses to bypass the VPN tunnel when the local LAN access feature is enabled:
* 10.*.*.*,
* 172.16.*.*,
* 192.168.*.*
Possible values: ON, OFF

<b>killConnections</b>
Specify whether the NetScaler Gateway Plug-in should disconnect all preexisting connections, such as the connections existing before the user logged on to NetScaler Gateway, and prevent new incoming connections on the NetScaler Gateway Plug-in for Windows and MAC when the user is connected to NetScaler Gateway and split tunneling is disabled.
Possible values: ON, OFF

<b>transparentInterception</b>
Allow access to network resources by using a single IP address and subnet mask or a range of IP addresses. The OFF setting sets the mode to proxy, in which you configure destination and source IP addresses and port numbers. If you are using the NetScaler Gateway Plug-in for Windows, set this parameter to ON, in which the mode is set to transparent. If you are using the NetScaler Gateway Plug-in for Java, set this parameter to OFF.
Possible values: ON, OFF

<b>defaultAuthorizationAction</b>
Specify the network resources that users have access to when they log on to the internal network. The default setting for authorization is to deny access to all network resources. Citrix recommends using the default global setting and then creating authorization policies to define the network resources users can access. If you set the default authorization policy to DENY, you must explicitly authorize access to any network resource, which improves security.
Possible values: ALLOW, DENY

<b>authorizationGroup</b>
Comma-separated list of groups in which the user is placed when none of the groups that the user is a part of is configured on NetScaler Gateway. The authorization policy can be bound to these groups to control access to the resources.

<b>Smartgroup</b>
This is the group in which the user is placed when the sessionpolicy associated with this sessionaction succeeds. The vpn session policy will do the post auth EPA check and if the check succeeds the user is placed in the group specified with smartgroup. The is_member_of (http.req.user.is_member_of) expression can then be used with policies to check if EPA has passed on the user belonging to this smartgroup
Maximum value: 64

<b>clientIdleTimeout</b>
Time, in minutes, after which to time out the user session if NetScaler Gateway does not detect mouse or keyboard activity.
Minimum value: 1
Maximum value: 9999

<b>proxy</b>
Set options to apply proxy for accessing the internal resources. Available settings function as follows:
* BROWSER - Proxy settings are configured only in Internet Explorer and Firefox browsers.
* NS - Proxy settings are configured on the NetScaler appliance.
* OFF - Proxy settings are not configured.
Possible values: BROWSER, NS, OFF

<b>allProtocolProxy</b>
IP address of the proxy server to use for all protocols supported by NetScaler Gateway.

<b>httpProxy</b>
IP address of the proxy server to be used for HTTP access for all subsequent connections to the internal network.

<b>ftpProxy</b>
IP address of the proxy server to be used for FTP access for all subsequent connections to the internal network.

<b>socksProxy</b>
IP address of the proxy server to be used for SOCKS access for all subsequent connections to the internal network.

<b>gopherProxy</b>
IP address of the proxy server to be used for GOPHER access for all subsequent connections to the internal network.

<b>sslProxy</b>
IP address of the proxy server to be used for SSL access for all subsequent connections to the internal network.

<b>proxyException</b>
Proxy exception string that will be configured in the browser for bypassing the previously configured proxies. Allowed only if proxy type is Browser.

<b>proxyLocalBypass</b>
Bypass proxy server for local addresses option in Internet Explorer and Firefox proxy server settings.
Possible values: ENABLED, DISABLED

<b>clientCleanupPrompt</b>
Prompt for client-side cache clean-up when a client-initiated session closes.
Possible values: ON, OFF

<b>forceCleanup</b>
Force cache clean-up when the user closes a session. You can specify all, none, or any combination of the client-side items.

<b>clientOptions</b>
Display only the configured menu options when you select the "Configure NetScaler Gateway" option in the NetScaler Gateway Plug-in system tray icon for Windows.

<b>clientConfiguration</b>
Display only the configured tabs when you select the "Configure NetSCaler Gateway" option in the NetScaler Gateway Plug-in system tray icon for Windows.

<b>SSO</b>
Set single sign-on (SSO) for the session. When the user accesses a server, the user's logon credentials are passed to the server for authentication.
Possible values: ON, OFF

<b>ssoCredential</b>
Specify whether to use the primary or secondary authentication credentials for single sign-on to the server.
Possible values: PRIMARY, SECONDARY

<b>windowsAutoLogon</b>
Enable or disable the Windows Auto Logon for the session. If a VPN session is established after this setting is enabled, the user is automatically logged on by using Windows credentials after the system is restarted.
Possible values: ON, OFF

<b>useMIP</b>
Enable or disable the use of a unique IP address alias, or a mapped IP address, as the client IP address for each client session. Allow NetScaler Gateway to use the mapped IP address as an intranet IP address when all other IP addresses are not available. 
When IP pooling is configured and the mapped IP is used as an intranet IP address, the mapped IP address is used when an intranet IP address cannot be assigned.
Possible values: NS, OFF

<b>useIIP</b>
Define IP address pool options. Available settings function as follows: 
* SPILLOVER - When an address pool is configured and the mapped IP is used as an intranet IP address, the mapped IP address is used when an intranet IP address cannot be assigned. 
* NOSPILLOVER - When intranet IP addresses are enabled and the mapped IP address is not used, the Transfer Login page appears for users who have used all available intranet IP addresses. 
* OFF - Address pool is not configured.
Possible values: NOSPILLOVER, SPILLOVER, OFF

<b>clientDebug</b>
Set the trace level on NetScaler Gateway. Technical support technicians use these debug logs for in-depth debugging and troubleshooting purposes. Available settings function as follows: 
* DEBUG - Detailed debug messages are collected and written into the specified file.
* STATS - Application audit level error messages and debug statistic counters are written into the specified file. 
* EVENTS - Application audit-level error messages are written into the specified file. 
* OFF - Only critical events are logged into the Windows Application Log.
Possible values: debug, stats, events, OFF

<b>loginScript</b>
Path to the logon script that is run when a session is established. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>logoutScript</b>
Path to the logout script. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>homePage</b>
Web address of the home page that appears when users log on. Otherwise, users receive the default home page for NetScaler Gateway, which is the Access Interface.

<b>icaProxy</b>
Enable ICA proxy to configure secure Internet access to servers running Citrix XenApp or XenDesktop by using Citrix Receiver instead of the NetScaler Gateway Plug-in.
Possible values: ON, OFF
Default value: OFF

<b>wihome</b>
Web address of the Web Interface server, such as http://&lt;ipAddress&gt;/Citrix/XenApp, or Receiver for Web, which enumerates the virtualized resources, such as XenApp, XenDesktop, and cloud applications. This web address is used as the home page in ICA proxy mode. 
If Client Choices is ON, you must configure this setting. Because the user can choose between FullClient and ICAProxy, the user may see a different home page. An Internet web site may appear if the user gets the FullClient option, or a Web Interface site if the user gets the ICAProxy option. If the setting is not configured, the XenApp option does not appear as a client choice.

<b>wihomeAddressType</b>
Type of the wihome address(IPV4/V6)
Possible values: IPV4, IPV6

<b>citrixReceiverHome</b>
Web address for the Citrix Receiver home page. Configure NetScaler Gateway so that when users log on to the appliance, the NetScaler Gateway Plug-in opens a web browser that allows single sign-on to the Citrix Receiver home page.

<b>wiPortalMode</b>
Layout on the Access Interface. The COMPACT value indicates the use of small icons.
Possible values: NORMAL, COMPACT

<b>ClientChoices</b>
Provide users with multiple logon options. With client choices, users have the option of logging on by using the NetScaler Gateway Plug-in for Windows, NetScaler Gateway Plug-in for Java, the Web Interface, or clientless access from one location. Depending on how NetScaler Gateway is configured, users are presented with up to three icons for logon choices. The most common are the NetScaler Gateway Plug-in for Windows, Web Interface, and clientless access.
Possible values: ON, OFF

<b>iipDnsSuffix</b>
An intranet IP DNS suffix. When a user logs on to NetScaler Gateway and is assigned an IP address, a DNS record for the user name and IP address combination is added to the NetScaler Gateway DNS cache. You can configure a DNS suffix to append to the user name when the DNS record is added to the cache. You can reach to the host from where the user is logged on by using the user's name, which can be easier to remember than an IP address. When the user logs off from NetScaler Gateway, the record is removed from the DNS cache.

<b>forcedTimeout</b>
Force a disconnection from the NetScaler Gateway Plug-in with NetScaler Gateway after a specified number of minutes. If the session closes, the user must log on again.
Minimum value: 1
Maximum value: 65535

<b>forcedTimeoutWarning</b>
Number of minutes to warn a user before the user session is disconnected.
Minimum value: 1
Maximum value: 255

<b>ntDomain</b>
Single sign-on domain to use for single sign-on to applications in the internal network. This setting can be overwritten by the domain that users specify at the time of logon or by the domain that the authentication server returns.

<b>clientlessVpnMode</b>
Enable clientless access for web, XenApp or XenDesktop, and FileShare resources without installing the NetScaler Gateway Plug-in. Available settings function as follows: 
* ON - Allow only clientless access. 
* OFF - Allow clientless access after users log on with the NetScaler Gateway Plug-in. 
* DISABLED - Do not allow clientless access.
Possible values: ON, OFF, DISABLED
Default value: OFF

<b>emailHome</b>
Web address for the web-based email, such as Outlook Web Access.

<b>clientlessModeUrlEncoding</b>
When clientless access is enabled, you can choose to encode the addresses of internal web applications or to leave the address as clear text. Available settings function as follows: 
* OPAQUE - Use standard encoding mechanisms to make the domain and protocol part of the resource unclear to users. 
* CLEAR - Do not encode the web address and make it visible to users. 
* ENCRYPT - Allow the domain and protocol to be encrypted using a session key. When the web address is encrypted, the URL is different for each user session for the same web resource. If users bookmark the encoded web address, save it in the web browser and then log off, they cannot connect to the web address when they log on and use the bookmark. If users save the encrypted bookmark in the Access Interface during their session, the bookmark works each time the user logs on.
Possible values: TRANSPARENT, OPAQUE, ENCRYPT

<b>clientlessPersistentCookie</b>
State of persistent cookies in clientless access mode. Persistent cookies are required for accessing certain features of SharePoint, such as opening and editing Microsoft Word, Excel, and PowerPoint documents hosted on the SharePoint server. A persistent cookie remains on the user device and is sent with each HTTP request. NetScaler Gateway encrypts the persistent cookie before sending it to the plug-in on the user device, and refreshes the cookie periodically as long as the session exists. The cookie becomes stale if the session ends. Available settings function as follows: 
* ALLOW - Enable persistent cookies. Users can open and edit Microsoft documents stored in SharePoint. 
* DENY - Disable persistent cookies. Users cannot open and edit Microsoft documents stored in SharePoint. 
* PROMPT - Prompt users to allow or deny persistent cookies during the session. Persistent cookies are not required for clientless access if users do not connect to SharePoint.
Possible values: ALLOW, DENY, PROMPT
Default value: DENY

<b>allowedLoginGroups</b>
Specify groups that have permission to log on to NetScaler Gateway. Users who do not belong to this group or groups are denied access even if they have valid credentials.

<b>SecureBrowse</b>
Allow users to connect through NetScaler Gateway to network resources from iOS and Android mobile devices with Citrix Receiver. Users do not need to establish a full VPN tunnel to access resources in the secure network.
Possible values: ENABLED, DISABLED

<b>storefronturl</b>
Web address for StoreFront to be used in this session for enumeration of resources from XenApp or XenDesktop.

<b>kcdAccount</b>
The kcd account details to be used in SSO

<b>rdpClientProfileName</b>
Name of the RDP profile associated with the vserver.

<b>WindowsPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win
Possible values: Always, Essential, Never

<b>MacPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac
Possible values: Always, Essential, Never

<b>LinuxPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux
Possible values: Always, Essential, Never

<b>iconWithReceiver</b>
Option to decide whether to show plugin icon along with receiver
Possible values: ON, OFF



##unset vpn sessionAction

Use this command to remove vpn sessionAction settings.Refer to the set vpn sessionAction command for meanings of the arguments.


##Synopsys

unset vpn sessionAction &lt;name> [-userAccounting] [-httpPort] [-winsIP] [-dnsVserverName] [-splitDns] [-sessTimeout] [-clientSecurity] [-clientSecurityGroup] [-clientSecurityMessage] [-clientSecurityLog] [-splitTunnel] [-localLanAccess] [-rfc1918] [-killConnections] [-transparentInterception] [-defaultAuthorizationAction] [-authorizationGroup] [-Smartgroup] [-clientIdleTimeout] [-proxy] [-allProtocolProxy] [-httpProxy] [-ftpProxy] [-socksProxy] [-gopherProxy] [-sslProxy] [-proxyException] [-proxyLocalBypass] [-clientCleanupPrompt] [-forceCleanup] [-clientOptions] [-clientConfiguration] [-SSO] [-ssoCredential] [-windowsAutoLogon] [-useMIP] [-useIIP] [-clientDebug] [-loginScript] [-logoutScript] [-homePage] [-icaProxy] [-wihome] [-citrixReceiverHome] [-wiPortalMode] [-ClientChoices] [-iipDnsSuffix] [-forcedTimeout] [-forcedTimeoutWarning] [-ntDomain] [-clientlessVpnMode] [-emailHome] [-clientlessModeUrlEncoding] [-clientlessPersistentCookie] [-allowedLoginGroups] [-SecureBrowse] [-storefronturl] [-kcdAccount] [-rdpClientProfileName] [-WindowsPluginUpgrade] [-MacPluginUpgrade] [-LinuxPluginUpgrade] [-iconWithReceiver]


##show vpn sessionAction

Displays a session action that is applied to a user session if the policy expression conditions are met.


##Synopsys

show vpn sessionAction [&lt;name>]


##Arguments

<b>name</b>
Name of the session action to display.



##Outputs

<b>userAccounting</b>
RADIUS policy to use for user accounting

<b>httpPort</b>
The HTTP port for this session action

<b>winsIP</b>
The WINS server IP address for this session action.

<b>dnsVserverName</b>
The name of the DNS vserver configured by the session action.

<b>splitDns</b>
The VPN client SplitDns state.

<b>sessTimeout</b>
The session timeout, in minutes, set by the action.

<b>clientSecurity</b>
The client security check string being applied. This is in the form of an expression. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide.

<b>clientSecurityGroup</b>
The client security group that will be assigned on failure of the client security check. Users can in general be organized into Groups. In this case, the Client Security Group may have a more restrictive security policy.

<b>clientSecurityMessage</b>
The client security message that will be displayed on failure of the client security check.

<b>clientSecurityLog</b>
Set the logging of client security checks.

<b>splitTunnel</b>
Send, through the tunnel, traffic only for intranet applications that are defined in NetScaler Gateway. Route all other traffic directly to the Internet. The OFF setting routes all traffic through NetScaler Gateway. With the REVERSE setting, intranet applications define the network traffic that is not intercepted. All network traffic directed to internal IP addresses bypasses the VPN tunnel, while other traffic goes through NetScaler Gateway. Reverse split tunneling can be used to log all non-local LAN traffic. For example, if users have a home network and are logged on through the NetScaler Gateway Plug-in, network traffic destined to a printer or another device within the home network is not intercepted.

<b>localLanAccess</b>
Set local LAN access. If split tunneling is OFF, and you set local LAN access to ON, the local client can route traffic to its local interface. When the local area network switch is specified, this combination of switches is useful. The client can allow local LAN access to devices that commonly have non-routable addresses, such as local printers or local file servers.

<b>rfc1918</b>
As defined in the local area network, allow only the following local area network addresses to bypass the VPN tunnel when the local LAN access feature is enabled:
* 10.*.*.*,
* 172.16.*.*,
* 192.168.*.*

<b>spoofIIP</b>
IP address that the intranet application uses to route the connection through the virtual adapter.

<b>killConnections</b>
Specify whether the NetScaler Gateway Plug-in should disconnect all preexisting connections, such as the connections existing before the user logged on to NetScaler Gateway, and prevent new incoming connections on the NetScaler Gateway Plug-in for Windows and MAC when the user is connected to NetScaler Gateway and split tunneling is disabled.

<b>transparentInterception</b>
Allow access to network resources by using a single IP address and subnet mask or a range of IP addresses. The OFF setting sets the mode to proxy, in which you configure destination and source IP addresses and port numbers. If you are using the NetScaler Gateway Plug-in for Windows, set this parameter to ON, in which the mode is set to transparent. If you are using the NetScaler Gateway Plug-in for Java, set this parameter to OFF.

<b>windowsClientType</b>
Windows client type, e.g. Agent or ActiveX

<b>defaultAuthorizationAction</b>
The Authorization Action, e.g. allow or deny

<b>authorizationGroup</b>
The authorization group applied to client sessions.

<b>Smartgroup</b>
The smartaccess group applied to client sessions used in ica (smartaccess2) policy expressions to check if user is a member of group that has any antivirus (this expression would be on the vpn session policy

<b>clientIdleTimeout</b>
The client idle timeout, in minutes.

<b>clientIdleTimeoutWarning</b>
The time after which the client gets a timeout warning, in minutes.

<b>proxy</b>
The state of proxy configuration for the session.

<b>allProtocolProxy</b>
The address set for all proxies.

<b>httpProxy</b>
The HTTP proxy IP address.

<b>ftpProxy</b>
The FTP proxy IP address.

<b>socksProxy</b>
IP address of the proxy server to be used for SOCKS access for all subsequent connections to the internal network.

<b>gopherProxy</b>
The Gopher proxy IP address.

<b>sslProxy</b>
The HTTPS proxy IP address.

<b>proxyException</b>
Proxy exception string that will be configured in the browser for bypassing the previously configured proxies. Allowed only if proxy type is Browser.

<b>proxyLocalBypass</b>
Bypass proxy server for local addresses option in Internet Explorer and Firefox proxy server settings.

<b>clientCleanupPrompt</b>
Prompt for client-side cache clean-up when a client-initiated session closes.

<b>forceCleanup</b>
Force cache clean-up when the user closes a session. You can specify all, none, or any combination of the client-side items.

<b>clientOptions</b>
List of configured buttons(and/or menu options in the docked client) in the Windows VPN client.

<b>clientConfiguration</b>
List of configured tabs in the Windows VPN client.

<b>SSO</b>
Whether or not Single Sign-On is used for this session.

<b>ssoCredential</b>
Specify whether to use the primary or secondary authentication credentials for single sign-on to the server.

<b>windowsAutoLogon</b>
Whether or not Windows Auto Logon is enabled for this session.

<b>useMIP</b>
Whether or not a Mapped IP address is used for the session

<b>useIIP</b>
Define IP address pool options. Available settings function as follows: 
* SPILLOVER - When an address pool is configured and the mapped IP is used as an intranet IP address, the mapped IP address is used when an intranet IP address cannot be assigned. 
* NOSPILLOVER - When intranet IP addresses are enabled and the mapped IP address is not used, the Transfer Login page appears for users who have used all available intranet IP addresses. 
* OFF - Address pool is not configured.

<b>clientDebug</b>
Trace level on the Windows VPN Client.

<b>loginScript</b>
Path to the logon script that is run when a session is established. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>logoutScript</b>
Path to the logout script. Separate multiple scripts by using comma. A "$" in the path signifies that the word following the "$" is an environment variable.

<b>homePage</b>
The client home page.

<b>icaProxy</b>
Enable ICA proxy to configure secure Internet access to servers running Citrix XenApp or XenDesktop by using Citrix Receiver instead of the NetScaler Gateway Plug-in.

<b>wihome</b>
Web address of the Web Interface server, such as http://&lt;ipAddress>/Citrix/XenApp, or Receiver for Web, which enumerates the virtualized resources, such as XenApp, XenDesktop, and cloud applications. This web address is used as the home page in ICA proxy mode. 
If Client Choices is ON, you must configure this setting. Because the user can choose between FullClient and ICAProxy, the user may see a different home page. An Internet web site may appear if the user gets the FullClient option, or a Web Interface site if the user gets the ICAProxy option. If the setting is not configured, the XenApp option does not appear as a client choice.

<b>wihomeAddressType</b>
Type of the wihome address(IPV4/V6)

<b>citrixReceiverHome</b>
Web address for the Citrix Receiver home page. Configure NetScaler Gateway so that when users log on to the appliance, the NetScaler Gateway Plug-in opens a web browser that allows single sign-on to the Citrix Receiver home page.

<b>wiPortalMode</b>
Layout on the Access Interface. The COMPACT value indicates the use of small icons.

<b>ClientChoices</b>
Provide users with multiple logon options. With client choices, users have the option of logging on by using the NetScaler Gateway Plug-in for Windows, NetScaler Gateway Plug-in for Java, the Web Interface, or clientless access from one location. Depending on how NetScaler Gateway is configured, users are presented with up to three icons for logon choices. The most common are the NetScaler Gateway Plug-in for Windows, Web Interface, and clientless access.

<b>epaClientType</b>
Choose between two types of End point Windows Client
a) Application Agent - which always runs in the task bar as a standalone application and also has a supporting service which runs permanently when installed
b) Activex Control - ActiveX control run by Microsoft Internet Explorer.

<b>iipDnsSuffix</b>
The IntranetIP DNS suffix.

<b>forcedTimeout</b>
Force a disconnection from the NetScaler Gateway Plug-in with NetScaler Gateway after a specified number of minutes. If the session closes, the user must log on again.

<b>forcedTimeoutWarning</b>
Number of minutes to warn a user before the user session is disconnected.

<b>ntDomain</b>
Single sign-on domain to use for single sign-on to applications in the internal network. This setting can be overwritten by the domain that users specify at the time of logon or by the domain that the authentication server returns.

<b>clientlessVpnMode</b>
Whether clientlessVPN is available to the session.

<b>clientlessModeUrlEncoding</b>
URL encoding used in clientless mode.

<b>clientlessPersistentCookie</b>
State of persistent cookies in clientless access mode. Persistent cookies are required for accessing certain features of SharePoint, such as opening and editing Microsoft Word, Excel, and PowerPoint documents hosted on the SharePoint server. A persistent cookie remains on the user device and is sent with each HTTP request. NetScaler Gateway encrypts the persistent cookie before sending it to the plug-in on the user device, and refreshes the cookie periodically as long as the session exists. The cookie becomes stale if the session ends. Available settings function as follows: 
* ALLOW - Enable persistent cookies. Users can open and edit Microsoft documents stored in SharePoint. 
* DENY - Disable persistent cookies. Users cannot open and edit Microsoft documents stored in SharePoint. 
* PROMPT - Prompt users to allow or deny persistent cookies during the session. Persistent cookies are not required for clientless access if users do not connect to SharePoint.

<b>emailHome</b>
The EMail home for the portal

<b>stateflag</b>

<b>allowedLoginGroups</b>
Specify groups that have permission to log on to NetScaler Gateway. Users who do not belong to this group or groups are denied access even if they have valid credentials.

<b>SecureBrowse</b>
Allow users to connect through NetScaler Gateway to network resources from iOS and Android mobile devices with Citrix Receiver. Users do not need to establish a full VPN tunnel to access resources in the secure network.

<b>storefronturl</b>
Web address for StoreFront to be used in this session for enumeration of resources from XenApp or XenDesktop.

<b>kcdAccount</b>
The kcd account details to be used in SSO

<b>rdpClientProfileName</b>
Name of the RDP profile associated with the vserver.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>WindowsPluginUpgrade</b>
Option to set plugin upgrade behaviour for Win

<b>MacPluginUpgrade</b>
Option to set plugin upgrade behaviour for Mac

<b>LinuxPluginUpgrade</b>
Option to set plugin upgrade behaviour for Linux

<b>iconWithReceiver</b>
Option to decide whether to show plugin icon along with receiver

<b>devno</b>

<b>count</b>



