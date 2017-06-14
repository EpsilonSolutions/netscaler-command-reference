#aaa preauthenticationaction

The following operations can be performed on "aaa preauthenticationaction":


[add](#add-aaa-preauthenticationaction) | [rm](#rm-aaa-preauthenticationaction) | [set](#set-aaa-preauthenticationaction) | [unset](#unset-aaa-preauthenticationaction) | [show](#show-aaa-preauthenticationaction)

##add aaa preauthenticationaction

Adds an action (profile) for endpoint analysis (EPA) clients before authentication.


##Synopsys

add aaa preauthenticationaction &lt;name> [&lt;preauthenticationaction>] [-killProcess &lt;string>] [-deletefiles &lt;string>]


##Arguments

<b>name</b>
Name for the preauthentication action. Must begin with a letter, number, or the underscore character (_), and must consist only of letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after preauthentication action is created. The following requirement applies only to the NetScaler CLI: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my aaa action? or ?my aaa action).

<b>preauthenticationaction</b>
Allow or deny logon after endpoint analysis (EPA) results. Possible values: ALLOW, DENY

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool.

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool.



##rm aaa preauthenticationaction

Removes a preauthentication action. NOTE: A preauthentication action cannot be removed if it is bound to a policy.


##Synopsys

rm aaa preauthenticationaction &lt;name>


##Arguments

<b>name</b>
Name of the preauthentication action to remove.



##set aaa preauthenticationaction

Modifies an existing preauthentication action (profile).


##Synopsys

set aaa preauthenticationaction &lt;name> [&lt;preauthenticationaction>] [-killProcess &lt;string>] [-deletefiles &lt;string>]


##Arguments

<b>name</b>
Name of the preauthentication action to modify.

<b>preauthenticationaction</b>
Allow or deny logon after endpoint analysis (EPA) results. Possible values: ALLOW, DENY

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool.

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool.



##unset aaa preauthenticationaction

Use this command to remove aaa preauthenticationaction settings.Refer to the set aaa preauthenticationaction command for meanings of the arguments.


##Synopsys

unset aaa preauthenticationaction &lt;name> [-killProcess] [-deletefiles]


##show aaa preauthenticationaction

Displays details of the specified preauthentication action.


##Synopsys

show aaa preauthenticationaction [&lt;name>]


##Arguments

<b>name</b>
Name of the preauthentication action.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>preauthenticationaction</b>
Allow or deny logon after endpoint analysis (EPA) results.

<b>killProcess</b>
String specifying the name of a process to be terminated by the endpoint analysis (EPA) tool.

<b>deletefiles</b>
String specifying the path(s) and name(s) of the files to be deleted by the endpoint analysis (EPA) tool.

<b>stateflag</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



