#wi site

The following operations can be performed on "wi site":


[add](#add-wi-site) | [rm](#rm-wi-site) | [set](#set-wi-site) | [unset](#unset-wi-site) | [bind](#bind-wi-site) | [unbind](#unbind-wi-site) | [show](#show-wi-site)

##add wi site

Creates a Web Interface site on the NetScaler appliance.          The NetScaler Web Interface feature provides access to Citrix XenApp and Citrix XenDesktop applications. Users access resources through a standard web browser or by using the Citrix XenApp plug-in.


##Synopsys

add wi site &lt;sitePath> [&lt;agURL>  [&lt;staURL>  [-secondSTAURL &lt;string>  [-useTwoTickets ( ON | OFF )]]  [-sessionReliability ( ON | OFF )]]  [-authenticationPoint ( WebInterface | AccessGateway )  [-agAuthenticationMethod ( Explicit | SmartCard )]]] [-wiAuthenticationMethods ( Explicit | Anonymous ) ...] [-defaultCustomTextLocale &lt;defaultCustomTextLocale>] [-webSessionTimeout &lt;positive_integer>] [-defaultAccessMethod &lt;defaultAccessMethod>] [-loginTitle &lt;string>] [-appWelcomeMessage &lt;string>] [-welcomeMessage &lt;string>] [-footerText &lt;string>] [-loginSysMessage &lt;string>] [-preLoginButton &lt;string>] [-preLoginMessage &lt;string>] [-preLoginTitle &lt;string>] [-domainSelection &lt;string>] [-siteType ( XenAppWeb | XenAppServices )  [-ShowSearch ( ON | OFF )]  [-ShowRefresh ( ON | OFF )]  [-wiUserInterfaceModes ( SIMPLE | ADVANCED )]  [-UserInterfaceLayouts &lt;UserInterfaceLayouts>]] [-userInterfaceBranding ( Desktops | Applications )] [-publishedResourceType &lt;publishedResourceType>] [-kioskMode ( ON | OFF )] [-restrictDomains ( ON | OFF )] [-loginDomains &lt;string>] [-hideDomainField ( ON | OFF )]


##Arguments

<b>sitePath</b>
Path to the Web Interface site being created on the NetScaler appliance.

<b>agURL</b>
URL of the Access Gateway.

<b>wiAuthenticationMethods</b>
The method of authentication to be used at Web Interface
Default value: WI_EXPLICIT

<b>defaultCustomTextLocale</b>
Default language for the Web Interface site.
Possible values: German, English, Spanish, French, Japanese, Korean, Russian, Chinese_simplified, Chinese_traditional
Default value: LANG_EN

<b>webSessionTimeout</b>
Time-out, in minutes, for idle Web Interface browser sessions. If a client's session is idle for a time that exceeds the time-out value, the NetScaler appliance terminates the connection.
Default value: 20
Minimum value: 1
Maximum value: 1440

<b>defaultAccessMethod</b>
Default access method for clients accessing the Web Interface site.
            Note: Before you configure an access method based on the client IP address, you must enable USIP mode on the Web Interface service to make the client?s IP address available with the Web Interface.
            Depending on whether the Web Interface site is configured to use an HTTP or HTTPS virtual server or to use access gateway, you can send clients or access gateway the IP address, or the alternate address, of a XenApp or XenDesktop server. Or, you can send the IP address translated from a mapping entry, which defines mapping of an internal address and port to an external address and port.
            Note: In the NetScaler command line, mapping entries can be created by using the bind wi site command.
Possible values: Direct, Alternate, Translated, GatewayDirect, GatewayAlternate, GatewayTranslated

<b>loginTitle</b>
A custom login page title for the Web Interface site.
Default value: "Welcome to Web Interface on NetScaler"

<b>appWelcomeMessage</b>
Specifies localized text to appear at the top of the main content area of the Applications screen. LanguageCode is en, de, es, fr, ja, or any other supported language identifier.

<b>welcomeMessage</b>
Localized welcome message that appears on the welcome area of the login screen.

<b>footerText</b>
Localized text that appears in the footer area of all pages.

<b>loginSysMessage</b>
Localized text that appears at the bottom of the main content area of the login screen.

<b>preLoginButton</b>
Localized text that appears as the name of the pre-login message confirmation button.

<b>preLoginMessage</b>
Localized text that appears on the pre-login message page.

<b>preLoginTitle</b>
Localized text that appears as the title of the pre-login message page.

<b>domainSelection</b>
Domain names listed on the login screen for explicit authentication.

<b>siteType</b>
Type of access to the Web Interface site. Available settings function as follows:
* XenApp/XenDesktop web site - Configures the Web Interface site for access by a web browser.
* XenApp/XenDesktop services site - Configures the Web Interface site for access by the XenApp plug-in.
Possible values: XenAppWeb, XenAppServices
Default value: WI_XENAPPWEB

<b>userInterfaceBranding</b>
Specifies whether the site is focused towards users accessing applications or desktops. Setting the parameter to Desktops changes the functionality of the site to improve the experience for XenDesktop users. Citrix recommends using this setting for any deployment that includes XenDesktop.
Possible values: Desktops, Applications
Default value: WI_UIBRAND_APP

<b>publishedResourceType</b>
Method for accessing the published XenApp and XenDesktop resources. 
            Available settings function as follows:
            * Online - Allows applications to be launched on the XenApp and XenDesktop servers. 
            * Offline - Allows streaming of applications to the client. 
            * DualMode - Allows both online and offline modes.
Possible values: Online, Offline, DualMode
Default value: WI_ONLINE

<b>kioskMode</b>
User settings do not persist from one session to another.
Possible values: ON, OFF
Default value: OFF

<b>ShowSearch</b>
Enables search option on XenApp websites
Possible values: ON, OFF
Default value: OFF

<b>ShowRefresh</b>
Provides the Refresh button on the applications screen.
Possible values: ON, OFF
Default value: OFF

<b>wiUserInterfaceModes</b>
Appearance of the login screen.
	    * Simple - Only the login fields for the selected authentication method are displayed.
	    * Advanced - Displays the navigation bar, which provides access to the pre-login messages and preferences screens.
Possible values: SIMPLE, ADVANCED
Default value: WI_SIMPLE

<b>UserInterfaceLayouts</b>
Specifies whether or not to use the compact user interface.
Possible values: AUTO, NORMAL, COMPACT
Default value: WI_AUTO

<b>restrictDomains</b>
The RestrictDomains setting is used to enable/disable domain restrictions. If domain restriction is enabled, the LoginDomains list is used for validating the login domain. It is applied to all the authentication methods except Anonymous for XenApp Web and XenApp Services sites
Possible values: ON, OFF
Default value: OFF

<b>loginDomains</b>
[List of NetBIOS domain names], Domain names to use for access restriction.
	    Only takes effect when used in conjunction with the RestrictDomains setting.

<b>hideDomainField</b>
The HideDomainField setting is used to control whether the domain field is displayed on the logon screen.
Possible values: ON, OFF
Default value: OFF



##Example

add wi site /Citrix/PNAgent -siteType XenAppServices

##rm wi site

Removes a Web Interface site from the NetScaler appliance.


##Synopsys

rm wi site &lt;sitePath>


##Arguments

<b>sitePath</b>
Path to the Web Interface site being created on the NetScaler appliance.



##Example

rm wi site /Citrix/PNAgent

##set wi site

Modifies the parameters of a Web Interface site configured on the NetScaler appliance.


##Synopsys

set wi site &lt;sitePath> [-agURL &lt;string>] [-staURL &lt;string>] [-sessionReliability ( ON | OFF )] [-useTwoTickets ( ON | OFF )] [-secondSTAURL &lt;string>] [-wiAuthenticationMethods ( Explicit | Anonymous ) ...] [-defaultAccessMethod &lt;defaultAccessMethod>] [-defaultCustomTextLocale &lt;defaultCustomTextLocale>] [-webSessionTimeout &lt;positive_integer>] [-loginTitle &lt;string>] [-appWelcomeMessage &lt;string>] [-welcomeMessage &lt;string>] [-footerText &lt;string>] [-loginSysMessage &lt;string>] [-preLoginButton &lt;string>] [-preLoginMessage &lt;string>] [-preLoginTitle &lt;string>] [-domainSelection &lt;string>] [-userInterfaceBranding ( Desktops | Applications )] [-authenticationPoint ( WebInterface | AccessGateway )] [-agAuthenticationMethod ( Explicit | SmartCard )] [-publishedResourceType &lt;publishedResourceType>] [-kioskMode ( ON | OFF )] [-ShowSearch ( ON | OFF )] [-ShowRefresh ( ON | OFF )] [-wiUserInterfaceModes ( SIMPLE | ADVANCED )] [-UserInterfaceLayouts &lt;UserInterfaceLayouts>] [-restrictDomains ( ON | OFF )] [-loginDomains &lt;string>] [-hideDomainField ( ON | OFF )]


##Arguments

<b>sitePath</b>
Path to the Web Interface site being created on the NetScaler appliance.

<b>agURL</b>
URL of the Access Gateway.

<b>staURL</b>
URL of the Secure Ticket Authority (STA) server.

<b>sessionReliability</b>
Enable session reliability through Access Gateway.
Possible values: ON, OFF
Default value: OFF

<b>useTwoTickets</b>
Request tickets issued by two separate Secure Ticket Authorities (STA) when a resource is accessed.
Possible values: ON, OFF
Default value: OFF

<b>secondSTAURL</b>
URL of the second Secure Ticket Authority (STA) server.

<b>wiAuthenticationMethods</b>
The method of authentication to be used at Web Interface
Default value: WI_EXPLICIT

<b>defaultAccessMethod</b>
Default access method for clients accessing the Web Interface site.
            Note: Before you configure an access method based on the client IP address, you must enable USIP mode on the Web Interface service to make the client?s IP address available with the Web Interface.
            Depending on whether the Web Interface site is configured to use an HTTP or HTTPS virtual server or to use access gateway, you can send clients or access gateway the IP address, or the alternate address, of a XenApp or XenDesktop server. Or, you can send the IP address translated from a mapping entry, which defines mapping of an internal address and port to an external address and port.
            Note: In the NetScaler command line, mapping entries can be created by using the bind wi site command.
Possible values: Direct, Alternate, Translated, GatewayDirect, GatewayAlternate, GatewayTranslated

<b>defaultCustomTextLocale</b>
Default language for the Web Interface site.
Possible values: German, English, Spanish, French, Japanese, Korean, Russian, Chinese_simplified, Chinese_traditional
Default value: LANG_EN

<b>webSessionTimeout</b>
Time-out, in minutes, for idle Web Interface browser sessions. If a client's session is idle for a time that exceeds the time-out value, the NetScaler appliance terminates the connection.
Default value: 20
Minimum value: 1
Maximum value: 1440

<b>loginTitle</b>
A custom login page title for the Web Interface site.
Default value: "Welcome to Web Interface on NetScaler"

<b>appWelcomeMessage</b>
Specifies localized text to appear at the top of the main content area of the Applications screen. LanguageCode is en, de, es, fr, ja, or any other supported language identifier.

<b>welcomeMessage</b>
Localized welcome message that appears on the welcome area of the login screen.

<b>footerText</b>
Localized text that appears in the footer area of all pages.

<b>loginSysMessage</b>
Localized text that appears at the bottom of the main content area of the login screen.

<b>preLoginButton</b>
Localized text that appears as the name of the pre-login message confirmation button.

<b>preLoginMessage</b>
Localized text that appears on the pre-login message page.

<b>preLoginTitle</b>
Localized text that appears as the title of the pre-login message page.

<b>domainSelection</b>
Domain names listed on the login screen for explicit authentication.

<b>userInterfaceBranding</b>
Specifies whether the site is focused towards users accessing applications or desktops. Setting the parameter to Desktops changes the functionality of the site to improve the experience for XenDesktop users. Citrix recommends using this setting for any deployment that includes XenDesktop.
Possible values: Desktops, Applications
Default value: WI_UIBRAND_APP

<b>authenticationPoint</b>
Authentication point for the Web Interface site.
Possible values: WebInterface, AccessGateway

<b>agAuthenticationMethod</b>
Method for authenticating a Web Interface site if you have specified Web Interface as the authentication point.
                            Available settings function as follows:
                            * Explicit - Users must provide a user name and password to log on to the Web Interface.
                            * Anonymous - Users can log on to the Web Interface without providing a user name and password. They have access to resources published for anonymous users.
Possible values: Explicit, SmartCard

<b>publishedResourceType</b>
Method for accessing the published XenApp and XenDesktop resources. 
            Available settings function as follows:
            * Online - Allows applications to be launched on the XenApp and XenDesktop servers. 
            * Offline - Allows streaming of applications to the client. 
            * DualMode - Allows both online and offline modes.
Possible values: Online, Offline, DualMode
Default value: WI_ONLINE

<b>kioskMode</b>
User settings do not persist from one session to another.
Possible values: ON, OFF
Default value: OFF

<b>ShowSearch</b>
Enables search option on XenApp websites
Possible values: ON, OFF
Default value: OFF

<b>ShowRefresh</b>
Provides the Refresh button on the applications screen.
Possible values: ON, OFF
Default value: OFF

<b>wiUserInterfaceModes</b>
Appearance of the login screen.
	    * Simple - Only the login fields for the selected authentication method are displayed.
	    * Advanced - Displays the navigation bar, which provides access to the pre-login messages and preferences screens.
Possible values: SIMPLE, ADVANCED
Default value: WI_SIMPLE

<b>UserInterfaceLayouts</b>
Specifies whether or not to use the compact user interface.
Possible values: AUTO, NORMAL, COMPACT
Default value: WI_AUTO

<b>restrictDomains</b>
The RestrictDomains setting is used to enable/disable domain restrictions. If domain restriction is enabled, the LoginDomains list is used for validating the login domain. It is applied to all the authentication methods except Anonymous for XenApp Web and XenApp Services sites
Possible values: ON, OFF
Default value: OFF

<b>loginDomains</b>
[List of NetBIOS domain names], Domain names to use for access restriction.
	    Only takes effect when used in conjunction with the RestrictDomains setting.

<b>hideDomainField</b>
The HideDomainField setting is used to control whether the domain field is displayed on the logon screen.
Possible values: ON, OFF
Default value: OFF



##Example

set wi site /Citrix/PNAgent -staURL http://myStaServer

##unset wi site

Use this command to remove wi site settings.Refer to the set wi site command for meanings of the arguments.


##Synopsys

unset wi site &lt;sitePath> [-appWelcomeMessage] [-welcomeMessage] [-footerText] [-loginSysMessage] [-preLoginButton] [-preLoginMessage] [-preLoginTitle] [-userInterfaceBranding] [-loginDomains]


##bind wi site

Binds XenApp or XenDesktop farms to a Web Interface site and optionally, defines access methods for different client IP addresses or networks.


##Synopsys

bind wi site &lt;sitePath> ((&lt;farmName>  &lt;xmlServerAddresses>  [-groups &lt;string>]  [-recoveryFarm ( ON | OFF )]  [-xmlPort &lt;positive_integer>]  [-transport &lt;transport>  [-sslRelayPort &lt;positive_integer>]]  [-loadBalance ( ON | OFF )]) | ((-accessMethod &lt;accessMethod>  (-clientIpAddress &lt;ip_addr>  -clientNetMask &lt;netmask>)) | (-translationInternalIp &lt;ip_addr>  -translationInternalPort &lt;port|*>  -translationExternalIp &lt;ip_addr>  -translationExternalPort &lt;port|*>  [-accessType &lt;accessType>])))


##Arguments

<b>sitePath</b>
Path to the Web Interface site.

<b>farmName</b>
Name for the logical representation of a XenApp or XenDesktop farm to be bound to the Web Interface site. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>accessMethod</b>
Secure access method to be applied to the IPv4 or network address of the client specified by the Client IP Address parameter.
            Depending on whether the Web Interface site is configured to use an HTTP or HTTPS virtual server or to use access gateway, you can send clients or access gateway the IP address, or the alternate address, of a XenApp or XenDesktop server. Or, you can send the IP address translated from a mapping entry, which defines mapping of an internal address and port to an external address and port.
Possible values: Direct, Alternate, Translated, GatewayDirect, GatewayAlternate, GatewayTranslated

<b>translationInternalIp</b>
IP address of the server for which you want to associate an external IP address. (Clients access the server through the associated external address and port.)
Default value: 0



##Example

bind wi site /Citrix/XenApp Farm2 10.10.10.11

##unbind wi site

Unbinds XenApp or XenDesktop farms from the Web Interface site and removes the existing access method definition for a client IP address or network.


##Synopsys

unbind wi site &lt;sitePath> (&lt;farmName> | ((-clientIpAddress &lt;ip_addr>  -clientNetMask &lt;netmask>) | (-translationInternalIp &lt;ip_addr>  -translationInternalPort &lt;port|*>  -translationExternalIp &lt;ip_addr>  -translationExternalPort &lt;port|*>)))


##Arguments

<b>sitePath</b>
Path to the Web Interface site.

<b>farmName</b>
Name of the XenApp farm to be unbound from the Web Interface site.

<b>clientIpAddress</b>
IPv4 address or network address of the client for which you want to remove the defined access method.
Default value: 0

<b>translationInternalIp</b>
Internal IP address of a mapping entry to be removed.
Default value: 0



##Example

unbind wi site  /Citrix/XenApp Farm2

##show wi site

Displays settings of all the Web Interface sites, or of a specified site.  To display settings of all the Web Interface sites, run the command without any parameters.


##Synopsys

show wi site [&lt;sitePath>]


##Arguments

<b>sitePath</b>
Path of a Web Interface site whose details you want the NetScaler appliance to display.

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>agURL</b>
URL of the Access Gateway.

<b>staURL</b>
The URL of Secure Ticketing Authortity server

<b>wiAuthenticationMethods</b>
The method of authentication to be used at Web Interface

<b>loginTitle</b>
A custom login page title for the Web Interface site.

<b>appWelcomeMessage</b>
Specifies localized text to appear at the top of the main content area of the Applications screen. LanguageCode is en, de, es, fr, ja, or any other supported language identifier.

<b>welcomeMessage</b>
Localized welcome message that appears on the welcome area of the login screen.

<b>footerText</b>
Localized text that appears in the footer area of all pages.

<b>loginSysMessage</b>
Localized text that appears at the bottom of the main content area of the login screen.

<b>preLoginButton</b>
Localized text that appears as the name of the pre-login message confirmation button.

<b>preLoginMessage</b>
Localized text that appears on the pre-login message page.

<b>preLoginTitle</b>
Localized text that appears as the title of the pre-login message page.

<b>domainSelection</b>
Domain names listed on the login screen for explicit authentication.

<b>defaultCustomTextLocale</b>
Default language for the Web Interface site.

<b>webSessionTimeout</b>
Time-out, in minutes, for idle Web Interface browser sessions. If a client's session is idle for a time that exceeds the time-out value, the NetScaler appliance terminates the connection.

<b>siteType</b>
Type of access to the Web Interface site. Available settings function as follows:
* XenApp/XenDesktop web site - Configures the Web Interface site for access by a web browser.
* XenApp/XenDesktop services site - Configures the Web Interface site for access by the XenApp plug-in.

<b>userInterfaceBranding</b>
Specifies whether the site is focused towards users accessing applications or desktops. Setting the parameter to Desktops changes the functionality of the site to improve the experience for XenDesktop users. Citrix recommends using this setting for any deployment that includes XenDesktop.

<b>ShowSearch</b>
Enables search option on XenApp websites

<b>ShowRefresh</b>
Provides the Refresh button on the applications screen.

<b>wiUserInterfaceModes</b>
Appearance of the login screen.
	    * Simple - Only the login fields for the selected authentication method are displayed.
	    * Advanced - Displays the navigation bar, which provides access to the pre-login messages and preferences screens.

<b>UserInterfaceLayouts</b>
Specifies whether or not to use the compact user interface.

<b>publishedResourceType</b>
Method for accessing the published XenApp and XenDesktop resources. 
            Available settings function as follows:
            * Online - Allows applications to be launched on the XenApp and XenDesktop servers. 
            * Offline - Allows streaming of applications to the client. 
            * DualMode - Allows both online and offline modes.

<b>defaultAccessMethod</b>
Default access method for clients accessing the Web Interface site.
            Note: Before you configure an access method based on the client IP address, you must enable USIP mode on the Web Interface service to make the client?s IP address available with the Web Interface.
            Depending on whether the Web Interface site is configured to use an HTTP or HTTPS virtual server or to use access gateway, you can send clients or access gateway the IP address, or the alternate address, of a XenApp or XenDesktop server. Or, you can send the IP address translated from a mapping entry, which defines mapping of an internal address and port to an external address and port.
            Note: In the NetScaler command line, mapping entries can be created by using the bind wi site command.

<b>farmName</b>
Name for the logical representation of a XenApp or XenDesktop farm to be bound to the Web Interface site. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>accessMethod</b>
Secure access method to be applied to the IPv4 or network address of the client specified by the Client IP Address parameter.
            Depending on whether the Web Interface site is configured to use an HTTP or HTTPS virtual server or to use access gateway, you can send clients or access gateway the IP address, or the alternate address, of a XenApp or XenDesktop server. Or, you can send the IP address translated from a mapping entry, which defines mapping of an internal address and port to an external address and port.

<b>clientIpAddress</b>
IPv4 or network address of the client for which you want to associate an access method.

<b>clientNetMask</b>
Subnet mask associated with the IPv4 or network address specified by the Client IP Address parameter.

<b>translationInternalIp</b>
IP address of the server for which you want to associate an external IP address. (Clients access the server through the associated external address and port.)

<b>translationInternalPort</b>
Port number of the server for which you want to associate an external port.  (Clients access the server through the associated external address and port.)

<b>translationExternalIp</b>
External IP address associated with server's IP address.

<b>translationExternalPort</b>
External port number associated with the server's port number.

<b>accessType</b>
Type of access to the XenApp or XenDesktop server. 
                            Available settings function as follows:
                            * User Device - Clients can use the translated address of the mapping entry to connect to the XenApp or XenDesktop server.
                            * Gateway - Access Gateway can use the translated address of the mapping entry to connect to the XenApp or XenDesktop server.
                            * User Device and Gateway - Both clients and Access Gateway can use the translated address of the mapping entry to connect to the XenApp or XenDesktop server.

<b>xmlServerAddresses</b>
Comma-separated IP addresses or host names of XenApp or XenDesktop servers providing XML services.

<b>xmlPort</b>
Port number at which to contact the XML service.

<b>transport</b>
Transport protocol to use for transferring data, related to the Web Interface site, between the NetScaler appliance and the XML service.

<b>sslRelayPort</b>
TCP port at which the XenApp or XenDesktop servers listenfor SSL Relay traffic from the NetScaler appliance. This parameter is required if you have set SSL Relay as the transport protocol. 
            Web Interface uses root certificates when authenticating a server running SSL Relay. Make sure that all the servers running SSL Relay are configured to listen on the same port.

<b>agAuthenticationMethod</b>
Method for authenticating a Web Interface site if you have specified Web Interface as the authentication point.
                            Available settings function as follows:
                            * Explicit - Users must provide a user name and password to log on to the Web Interface.
                            * Anonymous - Users can log on to the Web Interface without providing a user name and password. They have access to resources published for anonymous users.

<b>groups</b>
Active Directory groups that are permitted to enumerate resources from server farms. Including a setting for this parameter activates the user roaming feature. A maximum of 512 user groups can be specified for each farm defined with the Farm&lt;n> parameter.  The groups must be comma separated.

<b>recoveryFarm</b>
Binded farm is set as a recovery farm.

<b>sessionReliability</b>
Enable session reliability through Access Gateway.

<b>useTwoTickets</b>
Request tickets issued by two separate Secure Ticket Authorities (STA) when a resource is accessed.

<b>secondSTAURL</b>
URL of the second Secure Ticket Authority (STA) server.

<b>loadBalance</b>
Use all the XML servers (load balancing mode) or only one server (failover mode).

<b>authenticationPoint</b>
Authentication point for the Web Interface site.

<b>kioskMode</b>
User settings do not persist from one session to another.

<b>restrictDomains</b>
The RestrictDomains setting is used to enable/disable domain restrictions. If domain restriction is enabled, the LoginDomains list is used for validating the login domain. It is applied to all the authentication methods except Anonymous for XenApp Web and XenApp Services sites

<b>loginDomains</b>
[List of NetBIOS domain names], Domain names to use for access restriction.
	    Only takes effect when used in conjunction with the RestrictDomains setting.

<b>hideDomainField</b>
The HideDomainField setting is used to control whether the domain field is displayed on the logon screen.

<b>devno</b>

<b>count</b>



##Example

show wi site

