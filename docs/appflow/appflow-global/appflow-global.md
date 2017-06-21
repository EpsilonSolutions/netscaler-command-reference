#appflow global

The following operations can be performed on "appflow global":


[bind](#bind-appflow-global) | [unbind](#unbind-appflow-global) | [show](#show-appflow-global)

##bind appflow global

Binds the AppFlow policy to one of the two global lists of AppFlow policies. A policy becomes active only after it is bound.


##Synopsys

bind appflow global &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the AppFlow policy to be bound.

<b>priority</b>
Integer specifying the priority of the policy. The lower the number, the higher the priority. By default, policies in the list are evaluated in the order of their priority numbers.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the priority of the next policy, within the policy list, to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher numbered priority.
* END - Stop evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy list. If the final goto in the invoked policy list has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy list performs a NEXT.
* An expression that evaluates to a number.
If you specify an expression, it's evaluation result determines the next policy to evaluate, as follows: 
* If the expression evaluates to a higher numbered priority, that policy is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher priority number is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest priority number, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
The bind point to which to bind the policy.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT, ORACLE_REQ_OVERRIDE, ORACLE_REQ_DEFAULT

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to invoke. Specify vserver for a policy label associated with a virtual server, or policylabel for a user-defined policy label.
Possible values: vserver, policylabel

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.



##Example

	i)	bind appflow global pol9 9	ii)	bind appflow global pol9 9 120	iii)	bind appflow global pol9 9 "HTTP.REQ.HEADER(\\\\"qh3\\\\").TYPECAST_NUM_T(DECIMAL)"	

##unbind appflow global

Unbinds entities from an AppFlow global bind point.


##Synopsys

unbind appflow global (&lt;policyName>  [-type &lt;type>]  [-priority &lt;positive_integer>])


##Arguments

<b>policyName</b>
Name of the policy to be unbound.

<b>type</b>
Bind point from which to unbind the policy.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT, ORACLE_REQ_OVERRIDE, ORACLE_REQ_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.  Applicable only if a NOPOLICY has been bound to the bind point.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind appflow global pol9

##show appflow global

Displays the AppFlow global bind points and the number of policies bound to each global bind point, or more detailed information about the specified bind point.


##Synopsys

show appflow global [-type &lt;type>]


##Arguments

<b>type</b>
Global bind point for which to show detailed information about the policies bound to the bind point.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, ICA_REQ_OVERRIDE, ICA_REQ_DEFAULT, ORACLE_REQ_OVERRIDE, ORACLE_REQ_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the AppFlow policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to invoke. Specify vserver for a policy label associated with a virtual server, or policylabel for a user-defined policy label.

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flowType</b>
Flow type of the bound AppFlow policy.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show appflow global

