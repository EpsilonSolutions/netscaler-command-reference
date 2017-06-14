#authentication ldapAction

The following operations can be performed on "authentication ldapAction":


[add](#add-authentication-ldapaction) | [rm](#rm-authentication-ldapaction) | [set](#set-authentication-ldapaction) | [unset](#unset-authentication-ldapaction) | [show](#show-authentication-ldapaction)

##add authentication ldapAction

Creates an action (profile) for an LDAP server. This profile contains all configuration data needed to communicate with that LDAP server.


##Synopsys

add authentication ldapAction &lt;name> {-serverIP &lt;ip_addr|ipv6_addr|*> | {-serverName &lt;string>}} [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] [-ldapBase &lt;string>] [-ldapBindDn &lt;string>] {-ldapBindDnPassword } [-ldapLoginName &lt;string>] [-searchFilter &lt;string>] [-groupAttrName &lt;string>] [-subAttributeName &lt;string>] [-secType &lt;secType>] [-svrType ( AD | NDS )] [-ssoNameAttribute &lt;string>] [-authentication ( ENABLED | DISABLED )] [-requireUser ( YES | NO )] [-passwdChange ( ENABLED | DISABLED )] [-nestedGroupExtraction ( ON | OFF )  [-maxNestingLevel &lt;positive_integer>]  [-groupSearchSubAttribute &lt;string>]  [-groupSearchFilter &lt;string>]] [-followReferrals ( ON | OFF )  [-maxLDAPReferrals &lt;positive_integer>]] [-validateServerCert ( YES | NO )] [-ldapHostname &lt;string>] [-groupNameIdentifier &lt;string>] [-groupSearchAttribute &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name for the new LDAP action. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the LDAP action is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication action? or ?my authentication action?).

<b>serverIP</b>
IP address assigned to the LDAP server.

<b>serverName</b>
LDAP server name as a FQDN.  Mutually exclusive with LDAP IP address.

<b>serverPort</b>
Port on which the LDAP server accepts connections.
Default value: 389
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.
Default value: 3
Minimum value: 1

<b>ldapBase</b>
Base (node) from which to start LDAP searches. 
If the LDAP server is running locally, the default value of base is dc=netscaler, dc=com.

<b>ldapBindDn</b>
Full distinguished name (DN) that is used to bind to the LDAP server. 
Default: cn=Manager,dc=netscaler,dc=com

<b>ldapBindDnPassword</b>
Password used to bind to the LDAP server.

<b>ldapLoginName</b>
LDAP login name attribute. 
The NetScaler appliance uses the LDAP login name to query external LDAP servers or Active Directories.

<b>searchFilter</b>
String to be combined with the default LDAP user search string to form the search value. For example, if the search filter ?"vpnallowed=true"? is combined with the LDAP login name ?"samaccount"? and the user-supplied username is ?"bob"?, the result is the LDAP search string ""(&(vpnallowed=true)(samaccount=bob)"" (Be sure to enclose the search string in two sets of double quotation marks; both sets are needed.).

<b>groupAttrName</b>
LDAP group attribute name.
Used for group extraction on the LDAP server.

<b>subAttributeName</b>
LDAP group sub-attribute name. 
Used for group extraction from the LDAP server.

<b>secType</b>
Type of security used for communications between the NetScaler appliance and the LDAP server. For the PLAINTEXT setting, no encryption is required.
Possible values: PLAINTEXT, TLS, SSL
Default value: AAA_LDAP_PLAINTEXT

<b>svrType</b>
The type of LDAP server.
Possible values: AD, NDS
Default value: AAA_LDAP_SERVER_TYPE_DEFAULT

<b>ssoNameAttribute</b>
LDAP single signon (SSO) attribute. 
The NetScaler appliance uses the SSO name attribute to query external LDAP servers or Active Directories for an alternate username.

<b>authentication</b>
Perform LDAP authentication.
If authentication is disabled, any LDAP authentication attempt returns authentication success if the user is found. 
CAUTION! Authentication should be disabled only for authorization group extraction or where other (non-LDAP) authentication methods are in use and either bound to a primary list or flagged as secondary.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>requireUser</b>
Require a successful user search for authentication.
Possible values: YES, NO
Default value: YES

<b>passwdChange</b>
Allow password change requests.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nestedGroupExtraction</b>
Allow nested group extraction, in which the NetScaler appliance queries external LDAP servers to determine whether a group is part of another group.
Possible values: ON, OFF
Default value: OFF

<b>maxNestingLevel</b>
If nested group extraction is ON, specifies the number of levels up to which group extraction is performed.
Default value: 2
Minimum value: 2

<b>followReferrals</b>
Setting this option to ON enables following LDAP referrals received from the LDAP server.
Possible values: ON, OFF
Default value: OFF

<b>maxLDAPReferrals</b>
Specifies the maximum number of nested referrals to follow.
Default value: 1
Minimum value: 1

<b>validateServerCert</b>
When to validate LDAP server certs
Possible values: YES, NO
Default value: NO

<b>ldapHostname</b>
Hostname for the LDAP server.  If -validateServerCert is ON then this must be the host name on the certificate from the LDAP server.
A hostname mismatch will cause a connection failure.

<b>groupNameIdentifier</b>
Name that uniquely identifies a group in LDAP or Active Directory.

<b>groupSearchAttribute</b>
LDAP group search attribute. 
Used to determine to which groups a group belongs.

<b>groupSearchSubAttribute</b>
LDAP group search subattribute. 
Used to determine to which groups a group belongs.

<b>groupSearchFilter</b>
String to be combined with the default LDAP group search string to form the search value.  For example, the group search filter ""vpnallowed=true"" when combined with the group identifier ""samaccount"" and the group name ""g1"" yields the LDAP search string ""(&(vpnallowed=true)(samaccount=g1)"". (Be sure to enclose the search string in two sets of double quotation marks; both sets are needed.)

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64



##rm authentication ldapAction

Removes an LDAP profile (action).NOTE: An action cannot be removed if it is bound to a policy.


##Synopsys

rm authentication ldapAction &lt;name>


##Arguments

<b>name</b>
Name of the LDAP profile (action) to be removed.



##set authentication ldapAction

Modifies an LDAP server profile (action.) The profile contains all configuration data needed to communicate with that LDAP server.


##Synopsys

set authentication ldapAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverName &lt;string>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] [-ldapBase &lt;string>] [-ldapBindDn &lt;string>] {-ldapBindDnPassword } [-ldapLoginName &lt;string>] [-searchFilter &lt;string>] [-groupAttrName &lt;string>] [-subAttributeName &lt;string>] [-secType &lt;secType>] [-svrType ( AD | NDS )] [-ssoNameAttribute &lt;string>] [-authentication ( ENABLED | DISABLED )] [-requireUser ( YES | NO )] [-passwdChange ( ENABLED | DISABLED )] [-validateServerCert ( YES | NO )] [-ldapHostname &lt;string>] [-nestedGroupExtraction ( ON | OFF )] [-maxNestingLevel &lt;positive_integer>] [-groupNameIdentifier &lt;string>] [-groupSearchAttribute &lt;string>  [-groupSearchSubAttribute &lt;string>]] [-groupSearchFilter &lt;string>] [-followReferrals ( ON | OFF )] [-maxLDAPReferrals &lt;positive_integer>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>name</b>
Name of the LDAP profile to modify.

<b>serverIP</b>
IP address assigned to the LDAP server.

<b>serverName</b>
LDAP server name as a FQDN.  Mutually exclusive with LDAP IP address.

<b>serverPort</b>
Port on which the LDAP server accepts connections.
Default value: 389
Minimum value: 1

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.
Default value: 3
Minimum value: 1

<b>ldapBase</b>
Base (node) from which to start LDAP searches. 
If the LDAP server is running locally, the default value of base is dc=netscaler, dc=com.

<b>ldapBindDn</b>
Full distinguished name (DN) that is used to bind to the LDAP server. 
Default: cn=Manager,dc=netscaler,dc=com

<b>ldapBindDnPassword</b>
Password used to bind to the LDAP server.

<b>ldapLoginName</b>
LDAP login name attribute. 
The NetScaler appliance uses the LDAP login name to query external LDAP servers or Active Directories.

<b>searchFilter</b>
String to be combined with the default LDAP user search string to form the search value. For example, if the search filter ?"vpnallowed=true"? is combined with the LDAP login name ?"samaccount"? and the user-supplied username is ?"bob"?, the result is the LDAP search string ""(&(vpnallowed=true)(samaccount=bob)"" (Be sure to enclose the search string in two sets of double quotation marks; both sets are needed.).

<b>groupAttrName</b>
LDAP group attribute name.
Used for group extraction on the LDAP server.

<b>subAttributeName</b>
LDAP group sub-attribute name. 
Used for group extraction from the LDAP server.

<b>secType</b>
Type of security used for communications between the NetScaler appliance and the LDAP server. For the PLAINTEXT setting, no encryption is required.
Possible values: PLAINTEXT, TLS, SSL
Default value: AAA_LDAP_PLAINTEXT

<b>svrType</b>
The type of LDAP server.
Possible values: AD, NDS
Default value: AAA_LDAP_SERVER_TYPE_DEFAULT

<b>ssoNameAttribute</b>
LDAP single signon (SSO) attribute. 
The NetScaler appliance uses the SSO name attribute to query external LDAP servers or Active Directories for an alternate username.

<b>authentication</b>
Perform LDAP authentication.
If authentication is disabled, any LDAP authentication attempt returns authentication success if the user is found. 
CAUTION! Authentication should be disabled only for authorization group extraction or where other (non-LDAP) authentication methods are in use and either bound to a primary list or flagged as secondary.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>requireUser</b>
Require a successful user search for authentication.
Possible values: YES, NO
Default value: YES

<b>passwdChange</b>
Allow password change requests.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>validateServerCert</b>
When to validate LDAP server certs
Possible values: YES, NO
Default value: NO

<b>ldapHostname</b>
Hostname for the LDAP server.  If -validateServerCert is ON then this must be the host name on the certificate from the LDAP server.
A hostname mismatch will cause a connection failure.

<b>nestedGroupExtraction</b>
Allow nested group extraction, in which the NetScaler appliance queries external LDAP servers to determine whether a group is part of another group.
Possible values: ON, OFF
Default value: OFF

<b>followReferrals</b>
Setting this option to ON enables following LDAP referrals received from the LDAP server.
Possible values: ON, OFF
Default value: OFF

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64



##unset authentication ldapAction

Use this command to remove authentication ldapAction settings.Refer to the set authentication ldapAction command for meanings of the arguments.


##Synopsys

unset authentication ldapAction &lt;name> [-serverIP] [-serverName] [-serverPort] [-authTimeout] [-ldapBase] [-ldapBindDn] [-ldapBindDnPassword] [-ldapLoginName] [-searchFilter] [-groupAttrName] [-subAttributeName] [-secType] [-svrType] [-ssoNameAttribute] [-authentication] [-requireUser] [-passwdChange] [-validateServerCert] [-ldapHostname] [-nestedGroupExtraction] [-maxNestingLevel] [-groupNameIdentifier] [-groupSearchAttribute] [-groupSearchSubAttribute] [-groupSearchFilter] [-followReferrals] [-maxLDAPReferrals] [-defaultAuthenticationGroup]


##show authentication ldapAction

Displays the current configuration settings for the specified LDAP profile (action).


##Synopsys

show authentication ldapAction [&lt;name>]


##Arguments

<b>name</b>
Name of the LDAP profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>serverIP</b>
IP address assigned to the LDAP server.

<b>serverName</b>
LDAP server name as a FQDN.  Mutually exclusive with LDAP IP address.

<b>serverPort</b>
Port on which the LDAP server accepts connections.

<b>authTimeout</b>
Number of seconds the NetScaler appliance waits for a response from the RADIUS server.

<b>ldapBindDn</b>
Full distinguished name (DN) that is used to bind to the LDAP server. 
Default: cn=Manager,dc=netscaler,dc=com

<b>ldapBindDnPassword</b>
Password used to bind to the LDAP server.

<b>ldapLoginName</b>
LDAP login name attribute. 
The NetScaler appliance uses the LDAP login name to query external LDAP servers or Active Directories.

<b>ldapBase</b>
Base (node) from which to start LDAP searches. 
If the LDAP server is running locally, the default value of base is dc=netscaler, dc=com.

<b>searchFilter</b>
String to be combined with the default LDAP user search string to form the search value. For example, if the search filter ?"vpnallowed=true"? is combined with the LDAP login name ?"samaccount"? and the user-supplied username is ?"bob"?, the result is the LDAP search string ""(&(vpnallowed=true)(samaccount=bob)"" (Be sure to enclose the search string in two sets of double quotation marks; both sets are needed.).

<b>groupAttrName</b>
LDAP group attribute name.
Used for group extraction on the LDAP server.

<b>subAttributeName</b>
LDAP group sub-attribute name. 
Used for group extraction from the LDAP server.

<b>secType</b>
Type of security used for communications between the NetScaler appliance and the LDAP server. For the PLAINTEXT setting, no encryption is required.

<b>svrType</b>
The type of LDAP server.

<b>ssoNameAttribute</b>
LDAP single signon (SSO) attribute. 
The NetScaler appliance uses the SSO name attribute to query external LDAP servers or Active Directories for an alternate username.

<b>authentication</b>
Perform LDAP authentication.
If authentication is disabled, any LDAP authentication attempt returns authentication success if the user is found. 
CAUTION! Authentication should be disabled only for authorization group extraction or where other (non-LDAP) authentication methods are in use and either bound to a primary list or flagged as secondary.

<b>requireUser</b>
Require a successful user search for authentication.

<b>Success</b>

<b>Failure</b>

<b>stateflag</b>

<b>nestedGroupExtraction</b>
Allow nested group extraction, in which the NetScaler appliance queries external LDAP servers to determine whether a group is part of another group.

<b>maxNestingLevel</b>
If nested group extraction is ON, specifies the number of levels up to which group extraction is performed.

<b>followReferrals</b>
Setting this option to ON enables following LDAP referrals received from the LDAP server.

<b>maxLDAPReferrals</b>
Specifies the maximum number of nested referrals to follow.

<b>validateServerCert</b>
When to validate LDAP server certs

<b>ldapHostname</b>
Hostname for the LDAP server.  If -validateServerCert is ON then this must be the host name on the certificate from the LDAP server.
A hostname mismatch will cause a connection failure.

<b>groupNameIdentifier</b>
Name that uniquely identifies a group in LDAP or Active Directory.

<b>groupSearchAttribute</b>
LDAP group search attribute. 
Used to determine to which groups a group belongs.

<b>groupSearchSubAttribute</b>
LDAP group search subattribute. 
Used to determine to which groups a group belongs.

<b>groupSearchFilter</b>
String to be combined with the default LDAP group search string to form the search value.  For example, the group search filter ""vpnallowed=true"" when combined with the group identifier ""samaccount"" and the group name ""g1"" yields the LDAP search string ""(&(vpnallowed=true)(samaccount=g1)"". (Be sure to enclose the search string in two sets of double quotation marks; both sets are needed.)

<b>passwdChange</b>
Allow password change requests.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>devno</b>

<b>count</b>



