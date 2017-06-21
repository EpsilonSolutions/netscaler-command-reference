#aaa preauthenticationparameter

The following operations can be performed on "aaa preauthenticationparameter":


[set](#set-aaa-preauthenticationparameter) | [unset](#unset-aaa-preauthenticationparameter) | [show](#show-aaa-preauthenticationparameter)

##set aaa preauthenticationparameter

Configures the default end point analysis (EPA) parameters that are applied before authentication.


##Synopsys

set aaa preauthenticationparameter [-preauthenticationaction ( ALLOW | DENY )] [-rule &lt;expression>] [-killProcess &lt;string>] [-deletefiles &lt;string>]


##Arguments

<b>preauthenticationaction</b>
Deny or allow login on the basis of end point analysis results.
Possible values: ALLOW, DENY

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, to be evaluated by the EPA tool.

<b>killProcess</b>
String specifying the name of a process to be terminated by the EPA tool.

<b>deletefiles</b>
String specifying the path(s) to and name(s) of the files to be deleted by the EPA tool, as a string of between 1 and 1023 characters.



##unset aaa preauthenticationparameter

Resets the default end point analysis(EPA) configuration settings on the NetScaler appliance.Attributes for which a default value is available revert to their default values. See the set aaa preauthenticationparameter command for descriptions of the parameters..Refer to the set aaa preauthenticationparameter command for meanings of the arguments.


##Synopsys

unset aaa preauthenticationparameter [-rule] [-preauthenticationaction] [-killProcess] [-deletefiles]


##show aaa preauthenticationparameter

Displays the current preauthentication configuration.


##Synopsys

show aaa preauthenticationparameter


##Outputs

<b>preauthenticationaction</b>
Deny or allow login after End point analysis results.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, to be evaluated by the EPA tool.

<b>killProcess</b>
Processes to be killed by EPA tool.

<b>deletefiles</b>
Files to be deleted by EPA tool.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.



