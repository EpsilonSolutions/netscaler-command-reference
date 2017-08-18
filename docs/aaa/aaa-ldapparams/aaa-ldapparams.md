#aaa ldapParams

The following operations can be performed on "aaa ldapParams":


[set](#set-aaa-ldapparams) | [unset](#unset-aaa-ldapparams) | [show](#show-aaa-ldapparams)

##set aaa ldapParams

Modifies the global configuration settings for the LDAP server. The settings that you specify are used for all SSL-VPN virtual servers unless you use authentication policies to create a configuration for a specific SSL-VPN virtual server.


##Synopsys

set aaa ldapParams [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-authTimeout &lt;positive_integer>] [-ldapBase &lt;string>] [-ldapBindDn &lt;string>] {-ldapBindDnPassword } [-ldapLoginName &lt;string>] [-searchFilter &lt;string>] [-groupAttrName &lt;string>] [-subAttributeName &lt;string>] [-secType &lt;secType>] [-svrType ( AD | NDS )] [-ssoNameAttribute &lt;string>] [-passwdChange ( ENABLED | DISABLED )] [-nestedGroupExtraction ( ON | OFF )] [-maxNestingLevel &lt;positive_integer>] [-groupNameIdentifier &lt;string>] [-groupSearchAttribute &lt;string>  [-groupSearchSubAttribute &lt;string>]] [-groupSearchFilter &lt;string>] [-defaultAuthenticationGroup &lt;string>]


##Arguments

<b>serverIP</b>
IP address of your LDAP server.

<b>serverPort</b>
Port number on which the LDAP server listens for connections.
Default value: 389
Minimum value: 1

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the LDAP server.
Default value: 3
Minimum value: 1

<b>ldapBase</b>
Base (the server and location) from which LDAP search commands should start. 
If the LDAP server is running locally, the default value of base is dc=netscaler, dc=com.

<b>ldapBindDn</b>
Complete distinguished name (DN) string used for binding to the LDAP server.

<b>ldapBindDnPassword</b>
Password for binding to the LDAP server.

<b>ldapLoginName</b>
Name attribute that the NetScaler appliance uses to query the external LDAP server or an Active Directory.

<b>searchFilter</b>
String to be combined with the default LDAP user search string to form the value to use when executing an LDAP search. 
For example, the following values:
vpnallowed=true,
ldaploginame=""samaccount""
when combined with the user-supplied username ""bob"", yield the following LDAP search string:
""(&(vpnallowed=true)(samaccount=bob)""

<b>groupAttrName</b>
Attribute name used for group extraction from the LDAP server.

<b>subAttributeName</b>
Subattribute name used for group extraction from the LDAP server.

<b>secType</b>
Type of security used for communications between the NetScaler appliance and the LDAP server. For the PLAINTEXT setting, no encryption is required.
Possible values: PLAINTEXT, TLS, SSL
Default value: PLAINTEXT

<b>svrType</b>
The type of LDAP server.
Possible values: AD, NDS
Default value: AAA_LDAP_SERVER_TYPE_DEFAULT

<b>ssoNameAttribute</b>
Attribute used by the NetScaler appliance to query an external LDAP server or Active Directory for an alternative username. 
This alternative username is then used for single sign-on (SSO).

<b>passwdChange</b>
Accept password change requests.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>nestedGroupExtraction</b>
Queries the external LDAP server to determine whether the specified group belongs to another group.
Possible values: ON, OFF
Default value: OFF

<b>maxNestingLevel</b>
Number of levels up to which the system can query nested LDAP groups.
Default value: 2
Minimum value: 2

<b>groupNameIdentifier</b>
LDAP-group attribute that uniquely identifies the group. No two groups on one LDAP server can have the same group name identifier.

<b>groupSearchAttribute</b>
LDAP-group attribute that designates the parent group of the specified group. Use this attribute to search for a group's parent group.

<b>groupSearchSubAttribute</b>
LDAP-group subattribute that designates the parent group of the specified group. Use this attribute to search for a group's parent group.

<b>groupSearchFilter</b>
Search-expression that can be specified for sending group-search requests to the LDAP server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.
Maximum value: 64



##Example

	To configure authentication in the LDAP server running at 192.40.1.2:set aaa ldapparams -serverip 192.40.1.2 -ldapbase "dc=netscaler,dc=com" -ldapBindDN "cn=Manager,dc=netscaler,dc=com" -ldapBindDnPassword secret -ldaploginname uid

##Related Commands

<ul><li><a href="../../../l#set-aaa-radiusp/l#set-aaa-radiusp">set aaa radiusparams</a></li><li><a href="../../../et-aaa-para/et-aaa-para">set aaa parameter</a></li></ul>



##unset aaa ldapParams

Use this command to remove aaa ldapParams settings.Refer to the set aaa ldapParams command for meanings of the arguments.


##Synopsys

unset aaa ldapParams [-serverIP] [-serverPort] [-authTimeout] [-ldapBase] [-ldapBindDn] [-ldapBindDnPassword] [-ldapLoginName] [-searchFilter] [-groupAttrName] [-subAttributeName] [-secType] [-svrType] [-ssoNameAttribute] [-passwdChange] [-nestedGroupExtraction] [-maxNestingLevel] [-groupNameIdentifier] [-groupSearchAttribute] [-groupSearchSubAttribute] [-groupSearchFilter] [-defaultAuthenticationGroup]


##show aaa ldapParams

Displays the current LDAP configuration on the NetScaler appliance.


##Synopsys

show aaa ldapParams


##Outputs

<b>serverIP</b>
The IP address of the LDAP server.

<b>serverPort</b>
Port number on which the LDAP server listens for connections.

<b>authTimeout</b>
Maximum number of seconds that the NetScaler appliance waits for a response from the LDAP server.

<b>ldapBindDnPassword</b>
Password for binding to the LDAP server.

<b>ldapBindDn</b>
The full distinguished name used to bind to the LDAP server.

<b>ldapLoginName</b>
The name attribute used by the system to query the external LDAP server, or an Active Directory.

<b>ldapBase</b>
The base or node where the ldapsearch should start. If the LDAP server is running locally, the default value of base is dc=netscaler, dc=com.

<b>secType</b>
The communication type between the system and the LDAP server.

<b>svrType</b>
LDAP server.

<b>ssoNameAttribute</b>
The attribute used by the system to query the external LDAP server, or an Active Directory, for an alternate username to be used in Single Sign-On.

<b>searchFilter</b>
The String to be combined with the default LDAP user search string to form the value. For example, vpnallowed=true with ldaploginame "samaccount" and the user-supplied username "bob" would yield the LDAP search string "(&(vpnallowed=true)(samaccount=bob)".

<b>groupAttrName</b>
The Attribute name for group extraction from the LDAP server.

<b>subAttributeName</b>
Subattribute name used for group extraction from the LDAP server.

<b>groupAuthName</b>
To associate AAA users with an AAA group, use the command
    "bind AAA group ... -username ...".
You can bind different policies to each AAA group. Use the command
    "bind AAA group ... -policy ..."

<b>passwdChange</b>
Accept password change requests.

<b>nestedGroupExtraction</b>
Queries the external LDAP server to determine whether the specified group belongs to another group.

<b>maxNestingLevel</b>
Number of levels up to which the system can query nested LDAP groups.

<b>groupNameIdentifier</b>
LDAP-group attribute that uniquely identifies the group. No two groups on one LDAP server can have the same group name identifier.

<b>groupSearchAttribute</b>
LDAP-group attribute that designates the parent group of the specified group. Use this attribute to search for a group's parent group.

<b>groupSearchSubAttribute</b>
LDAP-group subattribute that designates the parent group of the specified group. Use this attribute to search for a group's parent group.

<b>groupSearchFilter</b>
Search-expression that can be specified for sending group-search requests to the LDAP server.

<b>defaultAuthenticationGroup</b>
This is the default group that is chosen when the authentication succeeds in addition to extracted groups.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.



##Example

&gt; show aaa ldapparamsConfigured LDAP parameters  Server IP: 127.0.0.1    Port: 389 Timeout: 1      BindDn: cn=Manager,dc=florazel,dc=com login: uid      Base: dc=florazel,dc=com Secure Type: PLAINTEXTDone&gt;

