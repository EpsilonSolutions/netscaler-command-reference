#appflow policy

The following operations can be performed on "appflow policy":


[add](#add-appflow-policy) | [rm](#rm-appflow-policy) | [set](#set-appflow-policy) | [unset](#unset-appflow-policy) | [rename](#rename-appflow-policy) | [show](#show-appflow-policy)

##add appflow policy

Adds an Appflow policy. The policy specifies the rule based on which the traffic is evaluated, and the action to be taken if the rule returns "TRUE".


##Synopsys

add appflow policy &lt;name> &lt;rule> &lt;action> [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at
(@), equals (=), and hyphen (-) characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow policy" or 'my appflow policy').

<b>rule</b>
Expression or other value against which the traffic is evaluated. Must be a Boolean, default syntax expression.  Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the action to be associated with this policy.

<b>comment</b>
Any comments about this policy.



##Example

add appflow policy appflow_pol "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh3\\\\")" appflow_act

##rm appflow policy

Removes an AppFlow policy. (Cannot remove a policy that is bound to a policy label.)


##Synopsys

rm appflow policy &lt;name>


##Arguments

<b>name</b>
Name of the policy to be removed.



##Example

rm appflow policy appflow_policy_1

##set appflow policy

Modifies the rule and/or action for an existing AppFlow policy. The rule for flow type can be changed only if the associated action is of NEUTRAL flow type.


##Synopsys

set appflow policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the policy to modify.

<b>rule</b>
Expression or other value against which the traffic is evaluated. Must be a Boolean, default syntax expression.  Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the action to be associated with this policy.

<b>comment</b>
Any comments about this policy.



##Example

set appflow policy appflow_policy -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset appflow policy

Use this command to remove appflow policy settings.Refer to the set appflow policy command for meanings of the arguments.


##Synopsys

unset appflow policy &lt;name> -comment


##rename appflow policy

Renames an AppFlow policy.


##Synopsys

rename appflow policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the policy.

<b>newName</b>
New name for the policy. Must begin with an ASCII alphabetic or underscore (_)character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow policy" or 'my appflow policy').



##Example

rename appflow policy old_name new_name

##show appflow policy

Displays information about all configured AppFlow policies, or detailed information about the specified policy.


##Synopsys

show appflow policy [&lt;name>]


##Arguments

<b>name</b>
Name of the policy about which to display detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
Expression to be used by AppFlow policy.

<b>action</b>
AppFlow action associated with the policy.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of policy UNDEF hits.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>comment</b>
Any comments about this policy.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>devno</b>

<b>count</b>



##Example

show appflow policy

