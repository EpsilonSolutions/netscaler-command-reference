#lb group

The following operations can be performed on "lb group":


[add](#add-lb-group) | [set](#set-lb-group) | [unset](#unset-lb-group) | [bind](#bind-lb-group) | [unbind](#unbind-lb-group) | [rm](#rm-lb-group) | [show](#show-lb-group) | [rename](#rename-lb-group)

##add lb group

Adds lb group entity


##Synopsys

add lb group &lt;name>@ [-persistenceType &lt;persistenceType>] [-persistenceBackup ( SOURCEIP | NONE )] [-backupPersistenceTimeout &lt;mins>] [-persistMask &lt;netmask>] [-cookieName &lt;string>] [-v6persistmasklen &lt;positive_integer>] [-cookieDomain &lt;string>] [-timeout &lt;mins>] [-rule &lt;expression>] [-useVserverPersistency ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the load balancing virtual server group.

<b>persistenceType</b>
Type of persistence for the group. Available settings function as follows:
* SOURCEIP - Create persistence sessions based on the client IP.
* COOKIEINSERT - Create persistence sessions based on a cookie in client requests. The cookie is inserted by a Set-Cookie directive from the server, in its first response to a client.
* RULE - Create persistence sessions based on a user defined rule.
* NONE - Disable persistence for the group.
Possible values: SOURCEIP, COOKIEINSERT, RULE, NONE

<b>persistenceBackup</b>
Type of backup persistence for the group.
Possible values: SOURCEIP, NONE

<b>backupPersistenceTimeout</b>
Time period, in minutes, for which backup persistence is in effect.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>persistMask</b>
Persistence mask to apply to source IPv4 addresses when creating source IP based persistence sessions.
Default value: 0xFFFFFFFF

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>v6persistmasklen</b>
Persistence mask to apply to source IPv6 addresses when creating source IP based persistence sessions.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>cookieDomain</b>
Domain attribute for the HTTP cookie.

<b>timeout</b>
Time period for which a persistence session is in effect.
Default value: 2
Maximum value: 1440

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.
Default value: "None"

<b>useVserverPersistency</b>



##set lb group

Configures persistence for the specified load balancing group. The persistence settings are applied to all the members of the group.


##Synopsys

set lb group &lt;name>@ [-persistenceType &lt;persistenceType>] [-persistenceBackup ( SOURCEIP | NONE )] [-backupPersistenceTimeout &lt;mins>] [-persistMask &lt;netmask>] [-cookieName &lt;string>] [-v6persistmasklen &lt;positive_integer>] [-cookieDomain &lt;string>] [-timeout &lt;mins>] [-rule &lt;expression>] [-useVserverPersistency ( ENABLED | DISABLED )] [-masterVserver &lt;string>]


##Arguments

<b>name</b>
Name of the load balancing virtual server group.

<b>persistenceType</b>
Type of persistence for the group. Available settings function as follows:
* SOURCEIP - Create persistence sessions based on the client IP.
* COOKIEINSERT - Create persistence sessions based on a cookie in client requests. The cookie is inserted by a Set-Cookie directive from the server, in its first response to a client.
* RULE - Create persistence sessions based on a user defined rule.
* NONE - Disable persistence for the group.
Possible values: SOURCEIP, COOKIEINSERT, RULE, NONE

<b>persistenceBackup</b>
Type of backup persistence for the group.
Possible values: SOURCEIP, NONE

<b>backupPersistenceTimeout</b>
Time period, in minutes, for which backup persistence is in effect.
Default value: 2
Minimum value: 2
Maximum value: 1440

<b>persistMask</b>
Persistence mask to apply to source IPv4 addresses when creating source IP based persistence sessions.
Default value: 0xFFFFFFFF

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>v6persistmasklen</b>
Persistence mask to apply to source IPv6 addresses when creating source IP based persistence sessions.
Default value: 128
Minimum value: 1
Maximum value: 128

<b>cookieDomain</b>
Domain attribute for the HTTP cookie.

<b>timeout</b>
Time period for which a persistence session is in effect.
Default value: 2
Maximum value: 1440

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.
Default value: "None"

<b>useVserverPersistency</b>

<b>masterVserver</b>



##Example

set lb group webgrp -persistenceType COOKIEINSERT	To set the persistence type for multiple groups use the following command:       set lb group webgrp[1-3] -persistenceType COOKIEINSERT

##unset lb group

Use this command to remove lb group settings.Refer to the set lb group command for meanings of the arguments.


##Synopsys

unset lb group &lt;name>@ [-persistenceType] [-persistenceBackup] [-backupPersistenceTimeout] [-persistMask] [-cookieName] [-v6persistmasklen] [-cookieDomain] [-timeout] [-rule] [-useVserverPersistency] [-masterVserver]


##bind lb group

Binds one or more virtual servers to a load balancing virtual server group. If the specified group does not exist, the NetScaler appliance first creates the group, and then binds the virtual servers to it. A virtual server group enables you to specify common persistence settings for all of its members through a single set lb group command. Only address-based virtual servers can be added to a group. Content-based virtual servers (content switching and cache redirection virtual servers) cannot be added. A virtual server can be assigned to only one group at any given time. To move a virtual server from one group to another, the virtual server must first be unbound from the group to which it belongs.


##Synopsys

bind lb group &lt;name>@ &lt;vServerName>@ ...


##Arguments

<b>name</b>
Name for the load balancing virtual server group. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the virtual server is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my lbgroup" or 'my lbgroup').

<b>vServerName</b>
Name of the virtual server to bind to the group. Multiple names can be specified.



##Example

bind lb group webgrp http_vip	To bind multiple vservers to a group use the following command:	bind lb group webgrp v[1-4]	To bind vserver v1 to group webgrp1, v2 to webgrp2 and v3 to webgrp3, use the following command:	bind lb group webgrp[1-3] v[1-3]

##unbind lb group

Unbinds one or more virtual servers from a group. When the last virtual server is unbound, the group is removed.


##Synopsys

unbind lb group &lt;name> &lt;vServerName>@ ...


##Arguments

<b>name</b>
Name of the load balancing virtual server group.

<b>vServerName</b>
Name of the virtual server to unbind. Multiple names can be specified.



##Example

unbind lb group webgroup http_vip	To unbind multiple vservers use the following command:	unbind lb group webgroup v[1-3]

##rm lb group

Removes the lb group


##Synopsys

rm lb group &lt;name>@ ...


##Arguments

<b>name</b>
Name of the lb group to delete.



##Example

rm lb group lb_grp1

##show lb group

Displays the virtual servers bound to the specified group.


##Synopsys

show lb group [&lt;name>]


##Arguments

<b>name</b>
Name of the load balancing virtual server group.



##Outputs

<b>vServerName</b>
Virtual server name.

<b>persistenceType</b>
The type of the persistence set for the group.

<b>persistenceBackup</b>
The type of the backup persistence set for the group.

<b>backupPersistenceTimeout</b>
Time period, in minutes, for which backup persistence is in effect.

<b>persistMask</b>
The netmask applied for ipv4 traffic when the persistency type is SOURCEIP.

<b>v6persistmasklen</b>
The netmask applied for ipv6 traffic when the persistency type is SOURCEIP.

<b>cookieName</b>
Use this parameter to specify the cookie name for COOKIE peristence type. It specifies the name of cookie with a maximum of 32 characters. If not specified, cookie name is internally generated.

<b>cookieDomain</b>
Domain attribute for the HTTP cookie.

<b>timeout</b>
Time period for which a persistence session is in effect.

<b>rule</b>
Rule type.

<b>td</b>
Integer value that uniquely identifies the traffic domain in which you want to configure the entity. If you do not specify an ID, the entity becomes part of the default traffic domain, which has an ID of 0.

<b>stateflag</b>

<b>useVserverPersistency</b>

<b>masterVserver</b>

<b>devno</b>

<b>count</b>



##Example

show lb group webgrp

##rename lb group

Renames a load balancing virtual server group.


##Synopsys

rename lb group &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the load balancing virtual server group.

<b>newName</b>
New name for the load balancing virtual server group.



##Example

rename lb group gv1 gv-new1

