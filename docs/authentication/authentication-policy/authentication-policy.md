#authentication Policy

The following operations can be performed on "authentication Policy":


[add](#add-authentication-policy) | [rm](#rm-authentication-policy) | [set](#set-authentication-policy) | [unset](#unset-authentication-policy) | [show](#show-authentication-policy) | [rename](#rename-authentication-policy) | [stat](#stat-authentication-policy)

##add authentication Policy

Adds an advanced authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user.


##Synopsys

add authentication Policy &lt;name> -rule &lt;expression> -action &lt;string> [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the advance AUTHENTICATION policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after AUTHENTICATION policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the AUTHENTICATION server.

<b>action</b>
Name of the authentication action to be performed if the policy matches.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##rm authentication Policy

Removes the advance authentication policy.


##Synopsys

rm authentication Policy &lt;name>


##Arguments

<b>name</b>
Name of the advance authentication policy to remove.



##set authentication Policy

Modifies the specified parameters of a authentication policy.


##Synopsys

set authentication Policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the advance authentication policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the AUTHENTICATION server.

<b>action</b>
Name of the authentication action to be performed if the policy matches.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##unset authentication Policy

Use this command to remove authentication Policy settings.Refer to the set authentication Policy command for meanings of the arguments.


##Synopsys

unset authentication Policy &lt;name> [-undefAction] [-comment] [-logAction]


##show authentication Policy

Displays the current settings for the specified advance authentication policy.If no policy name is provided, displays a list of all advance authentication policies currently configured on the NetScaler appliance.


##Synopsys

show authentication Policy [&lt;name>]


##Arguments

<b>name</b>
Name of the advance authentication policy.



##Outputs

<b>rule</b>
The name of the new rule associated with the policy.

<b>action</b>
The name of the authentication action associated with the policy.

<b>stateflag</b>

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any comments to preserve information about this policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.

<b>hits</b>
Number of hits.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>nextFactor</b>
On success invoke label.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>vserverType</b>

<b>policySubType</b>

<b>devno</b>

<b>count</b>



##rename authentication Policy

Renames the specified authentication policy.


##Synopsys

rename authentication Policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the authentication policy.

<b>newName</b>
New name for the authentication policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').



##Example

rename authentication policy oldname newname

##stat authentication Policy

Displays authentication statistics for all advanced authentication policies, or for only the specified policy.


##Synopsys

stat authentication Policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the advanced authentication policy for which to display statistics. If no name is specified, statistics for all advanced authentication polices are shown.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Policy hits (Hits)</b>
Number of hits on the policy

<b>Policy undef hits (Undefhits)</b>
Number of undef hits on the policy



##Example

stat authentication policy

##Related Commands

<ul><li><a href="../../../ation-vserver.html#stat-authentication-vs/ation-vserver.html#stat-authentication-vs">stat authentication vserver</a></li><li><a href="../../../ation-samlidppolicy.html#stat-authentication-samlidpp/ation-samlidppolicy.html#stat-authentication-samlidpp">stat authentication samlIdPPolicy</a></li><li><a href="../../../ation-policylabel.html#stat-authentication-policy/ation-policylabel.html#stat-authentication-policy">stat authentication policylabel</a></li><li><a href="../../../ation-loginschemapolicy.html#stat-authentication-loginschemap/ation-loginschemapolicy.html#stat-authentication-loginschemap">stat authentication loginSchemaPolicy</a></li></ul>



