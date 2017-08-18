#authentication epaAction

The following operations can be performed on "authentication epaAction":


[add](#add-authentication-epaaction) | [rm](#rm-authentication-epaaction) | [set](#set-authentication-epaaction) | [unset](#unset-authentication-epaaction) | [show](#show-authentication-epaaction)

##add authentication epaAction

Adds an action (profile) for endpoint analysis (EPA) clients before authentication.


##Synopsys

add authentication epaAction &lt;name> -csecexpr &lt;expression> [-killProcess &lt;string>] [-deletefiles &lt;string>] [-defaultEPAGroup &lt;string>] [-quarantineGroup &lt;string>]


##Arguments

<b>name</b>
Name for the epa action. Must begin with a
	    letter, number, or the underscore character (_), and must consist
	    only of letters, numbers, and the hyphen (-), period (.) pound
	    (#), space ( ), at (@), equals (=), colon (:), and underscore
		    characters. Cannot be changed after epa action is created.The following requirement applies only to the NetScaler CLI:If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my aaa action" or 'my aaa action').

<b>csecexpr</b>
it holds the ClientSecurityExpression to be sent to the client

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool. Multiple processes to be delimited by comma

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool. Multiple files to be delimited by comma

<b>defaultEPAGroup</b>
This is the default group that is chosen when the EPA check succeeds.
Maximum value: 64

<b>quarantineGroup</b>
This is the quarantine group that is chosen when the EPA check fails
if configured.
Maximum value: 64



##rm authentication epaAction

Removes an epa action.NOTE: An epa action cannot be removed if it is bound to a policy.


##Synopsys

rm authentication epaAction &lt;name>


##Arguments

<b>name</b>
Name of the epa action to remove.



##set authentication epaAction

Modifies an existing epa action (profile).


##Synopsys

set authentication epaAction &lt;name> [-csecexpr &lt;expression>] [-killProcess &lt;string>] [-deletefiles &lt;string>] [-defaultEPAGroup &lt;string>] [-quarantineGroup &lt;string>]


##Arguments

<b>name</b>
Name of the epa action to modify.

<b>csecexpr</b>
it holds the ClientSecurityExpression to be sent to the client

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool. Multiple processes to be delimited by comma

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool. Multiple files to be delimited by comma

<b>defaultEPAGroup</b>
This is the default group that is chosen when the EPA check succeeds.
Maximum value: 64

<b>quarantineGroup</b>
This is the quarantine group that is chosen when the EPA check fails
if configured.
Maximum value: 64



##unset authentication epaAction

Use this command to remove authentication epaAction settings.Refer to the set authentication epaAction command for meanings of the arguments.


##Synopsys

unset authentication epaAction &lt;name> [-killProcess] [-deletefiles] [-defaultEPAGroup] [-quarantineGroup]


##show authentication epaAction

Displays details of the specified epa action.


##Synopsys

show authentication epaAction [&lt;name>]


##Arguments

<b>name</b>
Name of the epa action.



##Outputs

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool. Multiple processes to be delimited by comma

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool. Multiple files to be delimited by comma

<b>stateflag</b>

<b>defaultEPAGroup</b>
This is the default group that is chosen when the EPA check succeeds.

<b>quarantineGroup</b>
This is the quarantine group that is chosen when the EPA check fails
if configured.

<b>csecexpr</b>
it holds the ClientSecurityExpression to be sent to the client

<b>devno</b>

<b>count</b>



