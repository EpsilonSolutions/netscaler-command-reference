#appfw settings

The following operations can be performed on "appfw settings":


[set](#set-appfw-settings) | [unset](#unset-appfw-settings) | [show](#show-appfw-settings)

##set appfw settings

Modifies the global application firewall settings. The global settings apply to all application firewall profiles.


##Synopsys

set appfw settings [-defaultProfile &lt;string>] [-undefAction &lt;string>] [-sessionTimeout &lt;positive_integer>] [-learnRateLimit &lt;positive_integer>] [-sessionLifetime &lt;positive_integer>] [-sessionCookieName &lt;string>] [-clientIPLoggingHeader &lt;string>] [-importSizeLimit &lt;positive_integer>] [-signatureAutoUpdate ( ON | OFF )] [-signatureUrl &lt;expression>] [-cookiePostEncryptPrefix &lt;string>] [-logMalformedReq ( ON | OFF )] [-GeoLocationLogging ( ON | OFF )] [-CEFLogging ( ON | OFF )] [-entityDecoding ( ON | OFF )] [-useConfigurableSecretKey ( ON | OFF )]


##Arguments

<b>defaultProfile</b>
Profile to use when a connection does not match any policy. Default setting is APPFW_BYPASS, which sends unmatched connections back to the NetScaler appliance without attempting to filter them further.
Default value: APPFW_BYPASS

<b>undefAction</b>
Profile to use when an application firewall policy evaluates to undefined (UNDEF). 
An UNDEF event indicates an internal error condition. The APPFW_BLOCK built-in profile is the default setting. You can specify a different built-in or user-created profile as the UNDEF profile.
Default value: APPFW_BLOCK

<b>sessionTimeout</b>
Timeout, in seconds, after which a user session is terminated. Before continuing to use the protected web site, the user must establish a new session by opening a designated start URL.
Default value: 900 
Minimum value: 1
Maximum value: 65535

<b>learnRateLimit</b>
Maximum number of connections per second that the application firewall learning engine examines to generate new relaxations for learning-enabled security checks. The application firewall drops any connections above this limit from the list of connections used by the learning engine.
Default value: 400 
Minimum value: 1
Maximum value: 1000

<b>sessionLifetime</b>
Maximum amount of time (in seconds) that the application firewall allows a user session to remain active, regardless of user activity. After this time, the user session is terminated. Before continuing to use the protected web site, the user must establish a new session by opening a designated start URL.
Default value: 0 
Minimum value: 0
Maximum value: 2147483647

<b>sessionCookieName</b>
Name of the session cookie that the application firewall uses to track user sessions. 
Must begin with a letter or number, and can consist of from 1 to 31 letters, numbers, and the hyphen (-) and underscore (_) symbols.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cookie name" or 'my cookie name').
Default value: NS_S_AS_DEFAULT_COOKIE_NAME

<b>clientIPLoggingHeader</b>
Name of an HTTP header that contains the IP address that the client used to connect to the protected web site or service.

<b>importSizeLimit</b>
Cumulative total maximum number of bytes in web forms imported to a protected web site. If a user attempts to upload files with a total byte count higher than the specified limit, the application firewall blocks the request.
Default value: 134217728 
Minimum value: 1
Maximum value: 134217728

<b>signatureAutoUpdate</b>
Flag used to enable/disable auto update signatures
Possible values: ON, OFF
Default value: OFF

<b>signatureUrl</b>
URL to download the mapping file from server
Default value: https://s3.amazonaws.com/NSAppFwSignatures/SignaturesMapping.xml

<b>cookiePostEncryptPrefix</b>
String that is prepended to all encrypted cookie values.
Default value: NS_S_AS_DEFAULT_CKI_POST_ENCRYPT_PREFIX

<b>logMalformedReq</b>
Log requests that are so malformed that application firewall parsing doesn't occur.
Possible values: ON, OFF
Default value: ON

<b>GeoLocationLogging</b>
Enable Geo-Location Logging in CEF format logs.
Possible values: ON, OFF
Default value: OFF

<b>CEFLogging</b>
Enable CEF format logs.
Possible values: ON, OFF
Default value: OFF

<b>entityDecoding</b>
Transform multibyte (double- or half-width) characters to single width characters.
Possible values: ON, OFF
Default value: OFF

<b>useConfigurableSecretKey</b>
Use configurable secret key in AppFw operations
Possible values: ON, OFF
Default value: OFF



##unset appfw settings

Use this command to remove appfw settings settings.Refer to the set appfw settings command for meanings of the arguments.


##Synopsys

unset appfw settings [-defaultProfile] [-undefAction] [-sessionTimeout] [-learnRateLimit] [-sessionLifetime] [-sessionCookieName] [-clientIPLoggingHeader] [-importSizeLimit] [-signatureAutoUpdate] [-signatureUrl] [-cookiePostEncryptPrefix] [-logMalformedReq] [-GeoLocationLogging] [-CEFLogging] [-entityDecoding] [-useConfigurableSecretKey]


##show appfw settings

Displays the current application firewall global settings.


##Synopsys

show appfw settings


##Outputs

<b>defaultProfile</b>
Profile to use when a connection does not match any policy. Default setting is APPFW_BYPASS, which sends unmatched connections back to the NetScaler appliance without attempting to filter them further.

<b>undefAction</b>
Profile to use when an application firewall policy evaluates to undefined (UNDEF). 
An UNDEF event indicates an internal error condition. The APPFW_BLOCK built-in profile is the default setting. You can specify a different built-in or user-created profile as the UNDEF profile.

<b>sessionTimeout</b>
Session timeout (in seconds).

<b>learnRateLimit</b>
Learn messages rate limit value (in messages per second).

<b>sessionLifetime</b>
Session lifetime (in seconds). Zero means no limit.

<b>sessionCookieName</b>
Name of the session cookie that the application firewall uses to track user sessions. 
Must begin with a letter or number, and can consist of from 1 to 31 letters, numbers, and the hyphen (-) and underscore (_) symbols.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cookie name" or 'my cookie name').

<b>clientIPLoggingHeader</b>
Name of header that holds downstream IP address for logging purposes.

<b>importSizeLimit</b>
Cumulative total maximum number of bytes in web forms imported to a protected web site. If a user attempts to upload files with a total byte count higher than the specified limit, the application firewall blocks the request.

<b>signatureAutoUpdate</b>
Flag used to enable/disable auto update signatures

<b>signatureUrl</b>
URL to download the mapping file from server

<b>cookiePostEncryptPrefix</b>
String that is prepended to all encrypted cookie values.

<b>logMalformedReq</b>
Log requests that are so malformed that application firewall parsing doesn't occur.

<b>GeoLocationLogging</b>
Enable Geo-Location Logging in CEF format logs.

<b>CEFLogging</b>
Enable CEF format logs.

<b>entityDecoding</b>
Transform multibyte (double- or half-width) characters to single width characters.

<b>useConfigurableSecretKey</b>
Use configurable secret key in AppFw operations



