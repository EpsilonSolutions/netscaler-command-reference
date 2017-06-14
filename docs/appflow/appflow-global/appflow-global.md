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



##Example

	i)	bind appflow global pol9 9	ii)	bind appflow global pol9 9 120	iii)	bind appflow global pol9 9 "HTTP.REQ.HEADER(\\\\"qh3\\\\").TYPECAST_NUM_T(DECIMAL)"	

##unbind appflow global

Unbinds entities from an AppFlow global bind point.


##Synopsys

unbind appflow global (&lt;policyName>  [-type &lt;type>]  [-priority &lt;positive_integer>])


##Arguments

<b>policyName</b>
Name of the policy to be unbound.



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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



##Example

show appflow global

