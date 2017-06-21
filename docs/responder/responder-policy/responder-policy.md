#responder policy

The following operations can be performed on "responder policy":


[add](#add-responder-policy) | [rm](#rm-responder-policy) | [set](#set-responder-policy) | [unset](#unset-responder-policy) | [show](#show-responder-policy) | [rename](#rename-responder-policy) | [stat](#stat-responder-policy)

##add responder policy

Creates a responder policy, which specifies requests that the NetScaler appliance intercepts and responds to directly instead of forwarding them to a protected server.


##Synopsys

add responder policy &lt;name> &lt;rule> &lt;action> [&lt;undefAction>] [-comment &lt;string>] [-logAction &lt;string>] [-appflowAction &lt;string>]


##Arguments

<b>name</b>
Name for the responder policy.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the responder policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder policy" or 'my responder policy').

<b>rule</b>
Default syntax expression that the policy uses to determine whether to respond to the specified request.

<b>action</b>
Name of the responder action to perform if the request matches this responder policy. There are also some built-in actions which can be used. These are:
* NOOP - Send the request to the protected server instead of responding to it.
* RESET - Reset the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any type of information about this responder policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.

<b>appflowAction</b>
AppFlow action to invoke for requests that match this policy.



##Example

i) add responder policy pol9 "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" act_respondwith

##rm responder policy

Removes the specified responder policy.


##Synopsys

rm responder policy &lt;name>


##Arguments

<b>name</b>
Name of the responder policy to remove.



##Example

rm responder policy pol9

##set responder policy

Modifies the rule or action portion of the specified responder policy.


##Synopsys

set responder policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>] [-appflowAction &lt;string>]


##Arguments

<b>name</b>
Name of the responder policy.

<b>rule</b>
Default syntax expression that the policy uses to determine whether to respond to the specified request.

<b>action</b>
Name of the responder action to perform if the request matches this responder policy. There are also some built-in actions which can be used. These are:
* NOOP - Send the request to the protected server instead of responding to it.
* RESET - Reset the client connection by closing it. The client program, such as a browser, will handle this and may inform the user. The client may then resend the request if desired.
* DROP - Drop the request without sending a response to the user.

<b>undefAction</b>
Action to perform if the result of policy evaluation is undefined (UNDEF). An UNDEF event indicates an internal error condition. Only the above built-in actions can be used.

<b>comment</b>
Any type of information about this responder policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.

<b>appflowAction</b>
AppFlow action to invoke for requests that match this policy.



##Example

set responder policy pol9 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset responder policy

Removes the settings of an existing responder policy. Attributes for which a default value is available revert to their default values. See the set responder policy command for descriptions of the parameters..Refer to the set responder policy command for meanings of the arguments.


##Synopsys

unset responder policy &lt;name> [-undefAction] [-comment] [-logAction] [-appflowAction]


##Example

unset responder policy respol9 -undefAction

##show responder policy

Displays the current settings for the specified responder policy.If no policy name is specified, displays a list of all responder policies currently configured on the NetScaler appliance, with abbreviated settings.


##Synopsys

show responder policy [&lt;name>]show responder policy stats - alias for 'stat responder policy'


##Arguments

<b>name</b>
Name of the responder policy for which to display settings.



##Outputs

<b>stateflag</b>

<b>rule</b>
Rule of the policy.

<b>action</b>
Responder action associated with the policy.

<b>undefAction</b>
UNDEF action associated with the policy.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of policy UNDEF hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>comment</b>
Any type of information about this responder policy.

<b>logAction</b>
Name of the messagelog action to use for requests that match this policy.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>appflowAction</b>
AppFlow action to invoke for requests that match this policy.

<b>builtin</b>
Flag to determine if responder policy is built-in or not

<b>devno</b>

<b>count</b>



##Example

show responder policy

##rename responder policy

Renames the specified responder policy.


##Synopsys

rename responder policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the responder policy.

<b>newName</b>
New name for the responder policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder policy" or 'my responder policy').



##Example

rename responder policy oldname newname

##stat responder policy

Displays statistics for all responder policies currently configured on the NetScaler appliance, or detailed statistics for the specified policy.


##Synopsys

stat responder policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the responder policy for which to show detailed statistics.

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



##Related Commands

<ul><li><a href="../../../cylabel.html#stat-responder-policy/cylabel.html#stat-responder-policy">stat responder policylabel</a></li></ul>



