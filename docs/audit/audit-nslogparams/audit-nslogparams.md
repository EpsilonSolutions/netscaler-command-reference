#audit nslogParams

The following operations can be performed on "audit nslogParams":


[set](#set-audit-nslogparams) | [unset](#unset-audit-nslogparams) | [show](#show-audit-nslogparams)

##set audit nslogParams

Modifies the specified nslog parameters.Changes the IP address, the port, or the logging parameters for logs sent to nslog.


##Synopsys

set audit nslogParams [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-dateFormat &lt;dateFormat>] [-logLevel &lt;logLevel> ...] [-logFacility &lt;logFacility>] [-tcp ( NONE | ALL )] [-acl ( ENABLED | DISABLED )] [-timeZone ( GMT_TIME | LOCAL_TIME )] [-userDefinedAuditlog ( YES | NO )] [-appflowExport ( ENABLED | DISABLED )] [-lsn ( ENABLED | DISABLED )] [-alg ( ENABLED | DISABLED )] [-subscriberLog ( ENABLED | DISABLED )] [-sslInterception ( ENABLED | DISABLED )]


##Arguments

<b>serverIP</b>
IP address of the nslog server.

<b>serverPort</b>
Port on which the nslog server accepts connections.
Minimum value: 1

<b>dateFormat</b>
Format of dates in the logs.
Supported formats are: 
* MMDDYYYY - U.S. style month/date/year format.
* DDMMYYYY - European style date/month/year format.
* YYYYMMDD - ISO style year/month/date format.
Possible values: MMDDYYYY, DDMMYYYY, YYYYMMDD

<b>logLevel</b>
Types of information to be logged. 
Available settings function as follows: 
* ALL - All events.
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.
* NONE - No events.

<b>logFacility</b>
Facility value, as defined in RFC 3164, assigned to the log message. 
Log facility values are numbers 0 to 7 (LOCAL0 through LOCAL7). Each number indicates where a specific message originated from, such as the NetScaler appliance itself, the VPN, or external.
Possible values: LOCAL0, LOCAL1, LOCAL2, LOCAL3, LOCAL4, LOCAL5, LOCAL6, LOCAL7

<b>tcp</b>
Configure auditing to log TCP messages.
Possible values: NONE, ALL

<b>acl</b>
Configure auditing to log access control list (ACL) messages.
Possible values: ENABLED, DISABLED

<b>timeZone</b>
Time zone used for date and timestamps in the logs. 
Supported settings are: 
* GMT_TIME - Coordinated Universal Time.
* LOCAL_TIME - Use the server's timezone setting.
Possible values: GMT_TIME, LOCAL_TIME

<b>userDefinedAuditlog</b>
Log user-configurable log messages to nslog.
Setting this parameter to NO causes auditing to ignore all user-configured message actions. Setting this parameter to YES causes auditing to log user-configured message actions that meet the other logging criteria.
Possible values: YES, NO

<b>appflowExport</b>
Export log messages to AppFlow collectors.
Appflow collectors are entities to which log messages can be sent so that some action can be performed on them.
Possible values: ENABLED, DISABLED

<b>lsn</b>
Log the LSN messages
Possible values: ENABLED, DISABLED

<b>alg</b>
Log the ALG messages
Possible values: ENABLED, DISABLED

<b>subscriberLog</b>
Log subscriber session event information
Possible values: ENABLED, DISABLED

<b>sslInterception</b>
Log SSL Interception event information
Possible values: ENABLED, DISABLED



##unset audit nslogParams

Removes the existing nslog parameter settings. Attributes for which a default value is available revert to their default values. See the set audit nslogParams command for a description of the parameters..Refer to the set audit nslogParams command for meanings of the arguments.


##Synopsys

unset audit nslogParams [-serverIP] [-serverPort] [-logLevel] [-dateFormat] [-logFacility] [-tcp] [-acl] [-timeZone] [-userDefinedAuditlog] [-appflowExport] [-lsn] [-alg] [-subscriberLog] [-sslInterception]


##show audit nslogParams

Displays the current nslog parameter settings.


##Synopsys

show audit nslogParams


##Outputs

<b>name</b>
Name of the nslog param.

<b>serverIP</b>
IP address of the nslog server.

<b>serverPort</b>
Port on which the nslog server accepts connections.

<b>dateFormat</b>
Format of dates in the logs.
Supported formats are: 
* MMDDYYYY - U.S. style month/date/year format.
* DDMMYYYY - European style date/month/year format.
* YYYYMMDD - ISO style year/month/date format.

<b>logLevel</b>
The audit log level.

<b>logFacility</b>
Facility value, as defined in RFC 3164, assigned to the log message. 
Log facility values are numbers 0 to 7 (LOCAL0 through LOCAL7). Each number indicates where a specific message originated from, such as the NetScaler appliance itself, the VPN, or external.

<b>tcp</b>
Configure auditing to log TCP messages.

<b>acl</b>
Configure auditing to log access control list (ACL) messages.

<b>timeZone</b>
Time zone used for date and timestamps in the logs. 
Supported settings are: 
* GMT_TIME - Coordinated Universal Time.
* LOCAL_TIME - Use the server's timezone setting.

<b>userDefinedAuditlog</b>
Log user-configurable log messages to nslog.
Setting this parameter to NO causes auditing to ignore all user-configured message actions. Setting this parameter to YES causes auditing to log user-configured message actions that meet the other logging criteria.

<b>appflowExport</b>
Export log messages to AppFlow collectors.
Appflow collectors are entities to which log messages can be sent so that some action can be performed on them.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>lsn</b>
Log the LSN messages

<b>alg</b>
Log the ALG messages

<b>subscriberLog</b>
Log subscriber session event information

<b>sslInterception</b>
Log SSL Interception event information



