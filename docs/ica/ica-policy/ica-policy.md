#ica policy

The following operations can be performed on "ica policy":


[add](#add-ica-policy) | [rm](#rm-ica-policy) | [set](#set-ica-policy) | [unset](#unset-ica-policy) | [stat](#stat-ica-policy) | [rename](#rename-ica-policy) | [show](#show-ica-policy)

##add ica policy

This command adds an ICA policy. The policy specifies the rule, on which the traffic is evaluated, and the action to be taken if the rule returns "TRUE".


##Synopsys

add ica policy &lt;name> -rule &lt;expression> -action &lt;string> [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ica policy" or 'my ica policy').

<b>rule</b>
Expression or other value against which the traffic is evaluated. Must be a Boolean, default syntax expression.  Note: Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character.
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the ica action to be associated with this policy.

<b>comment</b>
Any type of information about this ICA policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.



##Example

add ica policy &lt;name&gt; -rule &lt;expression&gt; -action &lt;string&gt; [-comment &lt;string&gt;] [-logAction &lt;string&gt;] , where the action is the ica action name

##rm ica policy

This command removes an ICA policy


##Synopsys

rm ica policy &lt;name>


##Arguments

<b>name</b>
Name of the policy to be removed.



##Example

rm ica policy ica_policy_1

##set ica policy

This command modifies the parameters like rule, action , comment etc for an existing ICA policy.


##Synopsys

set ica policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the policy to modify.

<b>rule</b>
Expression or other value against which the traffic is evaluated. Must be a Boolean, default syntax expression.  Note: Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character.
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the ica action to be associated with this policy.

<b>comment</b>
Any type of information about this ICA policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.



##Example

set ica policy ica_policy -rule &lt;rule&gt;

##unset ica policy

Use this command to remove ica policy settings.Refer to the set ica policy command for meanings of the arguments.


##Synopsys

unset ica policy &lt;name> [-comment] [-logAction]


##stat ica policy

Displays statistics for the specified ICA policy.If no policy name is specified, displays abbreviated statistics for all ICA policies currently configured on the NetScaler appliance.


##Synopsys

stat ica policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the ica policy.

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

stat ica policy

##rename ica policy

This command renames an ICA policy.


##Synopsys

rename ica policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the policy.

<b>newName</b>
New name for the policy. Must begin with an ASCII alphabetic or underscore (_)character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), s
pace, colon (:), at (@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ica policy" or 'my ica policy').



##Example

rename ica policy old_name new_name

##show ica policy

This command displays information about all configured ICA policies, or detailed information about the specified policy.


##Synopsys

show ica policy [&lt;name>]show ica policy stats - alias for 'stat ica policy'


##Arguments

<b>name</b>
Name of the policy about which to display detailed information.



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression to be used by ICA policy.

<b>action</b>
ICA profile (action) associated with the policy.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of policy UNDEF hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>comment</b>
Any type of information about this ICA policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>boundTo</b>
Location where policy is bound.

<b>priority</b>
Specifies the priority of the policy.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>builtin</b>
Indicates that the ICA policy is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>



##Example

show ica policy

