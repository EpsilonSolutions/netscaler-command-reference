#audit nslogAction

The following operations can be performed on "audit nslogAction":


[add](#add-audit-nslogaction) | [rm](#rm-audit-nslogaction) | [set](#set-audit-nslogaction) | [unset](#unset-audit-nslogaction) | [show](#show-audit-nslogaction)

##add audit nslogAction

Adds an nslog action. The action contains a reference to an nslog server and specifies which information to log and how to log that information.


##Synopsys

add audit nslogAction &lt;name> &lt;serverIP> [-serverPort &lt;port>] -logLevel &lt;logLevel> ... [-dateFormat &lt;dateFormat>] [-logFacility &lt;logFacility>] [-tcp ( NONE | ALL )] [-acl ( ENABLED | DISABLED )] [-timeZone ( GMT_TIME | LOCAL_TIME )] [-userDefinedAuditlog ( YES | NO )] [-appflowExport ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the nslog action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the nslog action is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my nslog action? or ?my nslog action).

<b>serverIP</b>
IP address of the nslog server.

<b>serverPort</b>
Port on which the nslog server accepts connections.
Minimum value: 1

<b>logLevel</b>
Audit log level, which specifies the types of events to log. 
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

<b>dateFormat</b>
Format of dates in the logs.
Supported formats are: 
* MMDDYYYY - U.S. style month/date/year format.
* DDMMYYYY - European style date/month/year format.
* YYYYMMDD - ISO style year/month/date format.
Possible values: MMDDYYYY, DDMMYYYY, YYYYMMDD

<b>logFacility</b>
Facility value, as defined in RFC 3164, assigned to the log message. 
Log facility values are numbers 0 to 7 (LOCAL0 through LOCAL7). Each number indicates where a specific message originated from, such as the NetScaler appliance itself, the VPN, or external.
Possible values: LOCAL0, LOCAL1, LOCAL2, LOCAL3, LOCAL4, LOCAL5, LOCAL6, LOCAL7

<b>tcp</b>
Log TCP messages.
Possible values: NONE, ALL

<b>acl</b>
Log access control list (ACL) messages.
Possible values: ENABLED, DISABLED

<b>timeZone</b>
Time zone used for date and timestamps in the logs. 
Available settings function as follows: 
* GMT_TIME. Coordinated Universal Time.
* LOCAL_TIME. The server?s timezone setting.
Possible values: GMT_TIME, LOCAL_TIME

<b>userDefinedAuditlog</b>
Log user-configurable log messages to nslog.
Setting this parameter to NO causes auditing to ignore all user-configured message actions. Setting this parameter to YES causes auditing to log user-configured message actions that meet the other logging criteria.
Possible values: YES, NO

<b>appflowExport</b>
Export log messages to AppFlow collectors.
Appflow collectors are entities to which log messages can be sent so that some action can be performed on them.
Possible values: ENABLED, DISABLED



##rm audit nslogAction

Removes the specified nslog action and associated configuration. Note: An nslog action cannot be removed if it is bound to an nslog policy.


##Synopsys

rm audit nslogAction &lt;name>


##Arguments

<b>name</b>
Name of the nslog action to remove.



##set audit nslogAction

Modifies the specified settings of an existing nslog action.


##Synopsys

set audit nslogAction &lt;name> [-serverIP &lt;ip_addr|ipv6_addr|*>] [-serverPort &lt;port>] [-logLevel &lt;logLevel> ...] [-dateFormat &lt;dateFormat>] [-logFacility &lt;logFacility>] [-tcp ( NONE | ALL )] [-acl ( ENABLED | DISABLED )] [-timeZone ( GMT_TIME | LOCAL_TIME )] [-userDefinedAuditlog ( YES | NO )] [-appflowExport ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name of the nslog action to be modified.

<b>serverIP</b>
IP address of the nslog server.

<b>serverPort</b>
Port on which the nslog server accepts connections.
Minimum value: 1

<b>logLevel</b>
Audit log level, which specifies the types of events to log. 
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

<b>dateFormat</b>
Format of dates in the logs.
Supported formats are: 
* MMDDYYYY - U.S. style month/date/year format.
* DDMMYYYY - European style date/month/year format.
* YYYYMMDD - ISO style year/month/date format.
Possible values: MMDDYYYY, DDMMYYYY, YYYYMMDD

<b>logFacility</b>
Facility value, as defined in RFC 3164, assigned to the log message. 
Log facility values are numbers 0 to 7 (LOCAL0 through LOCAL7). Each number indicates where a specific message originated from, such as the NetScaler appliance itself, the VPN, or external.
Possible values: LOCAL0, LOCAL1, LOCAL2, LOCAL3, LOCAL4, LOCAL5, LOCAL6, LOCAL7

<b>tcp</b>
Log TCP messages.
Possible values: NONE, ALL

<b>acl</b>
Log access control list (ACL) messages.
Possible values: ENABLED, DISABLED

<b>timeZone</b>
Time zone used for date and timestamps in the logs. 
Available settings function as follows: 
* GMT_TIME. Coordinated Universal Time.
* LOCAL_TIME. The server?s timezone setting.
Possible values: GMT_TIME, LOCAL_TIME

<b>userDefinedAuditlog</b>
Log user-configurable log messages to nslog.
Setting this parameter to NO causes auditing to ignore all user-configured message actions. Setting this parameter to YES causes auditing to log user-configured message actions that meet the other logging criteria.
Possible values: YES, NO

<b>appflowExport</b>
Export log messages to AppFlow collectors.
Appflow collectors are entities to which log messages can be sent so that some action can be performed on them.
Possible values: ENABLED, DISABLED



##unset audit nslogAction

Removes the settings of an existing nslog action. Attributes for which a default value is available revert to their default values. See the set audit nslogAction command for descriptions of the parameters..Refer to the set audit nslogAction command for meanings of the arguments.


##Synopsys

unset audit nslogAction &lt;name> [-serverPort] [-logLevel] [-dateFormat] [-logFacility] [-tcp] [-acl] [-timeZone] [-userDefinedAuditlog] [-appflowExport]


##show audit nslogAction

Displays the current configuration of the specified nslog action.If no nslog action is specified, displays a list of all nslog actions currently configured on the NetScaler appliance.


##Synopsys

show audit nslogAction [&lt;name>]


##Arguments

<b>name</b>
Name of the nslog action.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>serverIP</b>
IP address of the nslog server.

<b>serverPort</b>
Port on which the nslog server accepts connections.

<b>logLevel</b>
Audit log level, which specifies the types of events to log. 
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

<b>dateFormat</b>
Format of dates in the logs.
Supported formats are: 
* MMDDYYYY - U.S. style month/date/year format.
* DDMMYYYY - European style date/month/year format.
* YYYYMMDD - ISO style year/month/date format.

<b>logFacility</b>
Facility value, as defined in RFC 3164, assigned to the log message. 
Log facility values are numbers 0 to 7 (LOCAL0 through LOCAL7). Each number indicates where a specific message originated from, such as the NetScaler appliance itself, the VPN, or external.

<b>tcp</b>
Log TCP messages.

<b>acl</b>
Log access control list (ACL) messages.

<b>timeZone</b>
Time zone used for date and timestamps in the logs. 
Available settings function as follows: 
* GMT_TIME. Coordinated Universal Time.
* LOCAL_TIME. The server?s timezone setting.

<b>stateflag</b>

<b>userDefinedAuditlog</b>
Log user-configurable log messages to nslog.
Setting this parameter to NO causes auditing to ignore all user-configured message actions. Setting this parameter to YES causes auditing to log user-configured message actions that meet the other logging criteria.

<b>appflowExport</b>
Export log messages to AppFlow collectors.
Appflow collectors are entities to which log messages can be sent so that some action can be performed on them.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



