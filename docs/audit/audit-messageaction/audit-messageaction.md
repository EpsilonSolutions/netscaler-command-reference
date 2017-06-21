#audit messageaction

The following operations can be performed on "audit messageaction":


[add](#add-audit-messageaction) | [rm](#rm-audit-messageaction) | [set](#set-audit-messageaction) | [unset](#unset-audit-messageaction) | [show](#show-audit-messageaction)

##add audit messageaction

Adds an audit message action.The action specifies whether to log the message, and to which log.


##Synopsys

add audit messageaction &lt;name> &lt;logLevel> &lt;stringBuilderExpr> [-logtoNewnslog ( YES | NO )] [-bypassSafetyCheck ( YES | NO )]


##Arguments

<b>name</b>
Name of the audit message action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the message action is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my message action? or ?my message action?).

<b>logLevel</b>
Audit log level, which specifies the severity level of the log message being generated.. 
The following loglevels are valid: 
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.
Possible values: EMERGENCY, ALERT, CRITICAL, ERROR, WARNING, NOTICE, INFORMATIONAL, DEBUG

<b>stringBuilderExpr</b>
Default-syntax expression that defines the format and content of the log message.

<b>logtoNewnslog</b>
Send the message to the new nslog.
Possible values: YES, NO

<b>bypassSafetyCheck</b>
Bypass the safety check and allow unsafe expressions.
Possible values: YES, NO
Default value: NO



##rm audit messageaction

Removes the specified audit message action and associated configuration.


##Synopsys

rm audit messageaction &lt;name>


##Arguments

<b>name</b>
Name of the audit message action to remove.



##set audit messageaction

Modifies the specified parameters of an existing audit message action.


##Synopsys

set audit messageaction &lt;name> [-logLevel &lt;logLevel>] [-stringBuilderExpr &lt;string>] [-logtoNewnslog ( YES | NO )] [-bypassSafetyCheck ( YES | NO )]


##Arguments

<b>name</b>
Name of the audit message action to modify.

<b>logLevel</b>
Audit log level, which specifies the severity level of the log message being generated. 
The following loglevels are valid: 
* EMERGENCY - Events that indicate an immediate crisis on the server.
* ALERT - Events that might require action.
* CRITICAL - Events that indicate an imminent server crisis.
* ERROR - Events that indicate some type of error.
* WARNING - Events that require action in the near future.
* NOTICE - Events that the administrator should know about.
* INFORMATIONAL - All but low-level events.
* DEBUG - All events, in extreme detail.
Possible values: EMERGENCY, ALERT, CRITICAL, ERROR, WARNING, NOTICE, INFORMATIONAL, DEBUG

<b>stringBuilderExpr</b>
Default-syntax expression that defines the format and content of the log message.

<b>logtoNewnslog</b>
Send the message to the new nslog.
Possible values: YES, NO

<b>bypassSafetyCheck</b>
Bypass the safety check and allow unsafe expressions.
Possible values: YES, NO
Default value: NO



##unset audit messageaction

Use this command to remove audit messageaction settings.Refer to the set audit messageaction command for meanings of the arguments.


##Synopsys

unset audit messageaction &lt;name> [-logtoNewnslog] [-bypassSafetyCheck]


##show audit messageaction

Displays the current configuration of the specified audit message action.If no audit message action is specified, displays a list of all audit message actions currently configured on the NetScaler appliance.


##Synopsys

show audit messageaction [&lt;name>]


##Arguments

<b>name</b>
Name of the audit message action.



##Outputs

<b>logLevel</b>

<b>stringBuilderExpr</b>
Default-syntax expression that defines the format and content of the log message.

<b>logtoNewnslog</b>
Send the message to the new nslog.

<b>bypassSafetyCheck</b>
Bypass the safety check and allow unsafe expressions.

<b>stateflag</b>

<b>hits</b>
The number of times the action has been taken.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>referenceCount</b>
The number of references to the action.

<b>devno</b>

<b>count</b>



