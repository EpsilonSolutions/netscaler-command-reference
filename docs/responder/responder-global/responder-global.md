#responder global

The following operations can be performed on "responder global":


[bind](#bind-responder-global) | [unbind](#unbind-responder-global) | [show](#show-responder-global)

##bind responder global

Activates the specified responder policy for all requests sent to the NetScaler appliance.


##Synopsys

bind responder global &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the responder policy to activate. If you want to create the policy as well as activate it, specify a name for the responder policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder policy" or 'my responder policy').

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Must be unique within the label. Policies are evaluated in the order of their priority numbers, and the first policy that matches the request is applied.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
*  NEXT - Evaluate the policy with the next higher priority number.
*  END - End policy evaluation.
*  USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
*  If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
*  If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
*  If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
*  The expression is invalid.
*  The expression evaluates to a priority number that is smaller than the current policy's priority number.
*  The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
Bind point to which to bind the policy. Available settings function as follows:
* REQ_OVERRIDE - Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT - Binds the policy to the default request queue.
* OTHERTCP_REQ_OVERRIDE - Binds the policy to the non-HTTP TCP priority request queue.
* OTHERTCP_REQ_DEFAULT - Binds the policy to the non-HTTP TCP default request queue.
* SIPUDP_REQ_OVERRIDE - Binds the policy to the SIP UDP priority response queue.
* SIPUDP_REQ_DEFAULT - Binds the policy to the SIP UDP default response queue.
* RADIUS_REQ_OVERRIDE - Binds the policy to the RADIUS priority response queue.
* RADIUS_REQ_DEFAULT - Binds the policy to the RADIUS default response queue.
* MSSQL_REQ_OVERRIDE - Binds the policy to the Microsoft SQL priority response queue.
* MSSQL_REQ_DEFAULT - Binds the policy to the Microsoft SQL default response queue.
* MYSQL_REQ_OVERRIDE - Binds the policy to the MySQL priority response queue.
* MYSQL_REQ_DEFAULT - Binds the policy to the MySQL default response queue.
* NAT_REQ_OVERRIDE - Binds the policy to the NAT priority request queue.
* NAT_REQ_DEFAULT - Binds the policy to the NAT  default request queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, NAT_REQ_OVERRIDE, NAT_REQ_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation, Available settings function as follows:
* vserver - Forward the request to the specified virtual server.
* policylabel - Invoke the specified policy label.
Possible values: vserver, policylabel

<b>labelName</b>
Name of the policy label to invoke. If the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is policylabel.



##Example

	i)	bind responder global pol9 9

##unbind responder global

Unbind the specified responder policy from responder global.


##Synopsys

unbind responder global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Name of the policy to unbind.

<b>type</b>
The bindpoint from which the policy is to be unbound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, NAT_REQ_OVERRIDE, NAT_REQ_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind responder global pol9

##show responder global

Displays the list of policies bound to the specified responder global bind point.If no bind point is specified, displays a list of all policies bound to responder global.


##Synopsys

show responder global [-type &lt;type>]


##Arguments

<b>type</b>
Specifies the bind point whose policies you want to display. Available settings function as follows:
* REQ_OVERRIDE - Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT - Binds the policy to the default request queue.
* OTHERTCP_REQ_OVERRIDE - Binds the policy to the non-HTTP TCP priority request queue.
* OTHERTCP_REQ_DEFAULT - Binds the policy to the non-HTTP TCP default request queue..
* SIPUDP_REQ_OVERRIDE - Binds the policy to the SIP UDP priority response queue..
* SIPUDP_REQ_DEFAULT - Binds the policy to the SIP UDP default response queue.
* RADIUS_REQ_OVERRIDE - Binds the policy to the RADIUS priority response queue..
* RADIUS_REQ_DEFAULT - Binds the policy to the RADIUS default response queue.
* MSSQL_REQ_OVERRIDE - Binds the policy to the Microsoft SQL priority response queue..
* MSSQL_REQ_DEFAULT - Binds the policy to the Microsoft SQL default response queue.
* MYSQL_REQ_OVERRIDE - Binds the policy to the MySQL priority response queue.
* MYSQL_REQ_DEFAULT - Binds the policy to the MySQL default response queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, OVERRIDE, DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, MSSQL_REQ_OVERRIDE, MSSQL_REQ_DEFAULT, MYSQL_REQ_OVERRIDE, MYSQL_REQ_DEFAULT, NAT_REQ_OVERRIDE, NAT_REQ_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the responder policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation, Available settings function as follows:
* vserver - Forward the request to the specified virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
Name of the policy label to invoke. If the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is policylabel.

<b>flowType</b>
flowtype of the bound responder policy.

<b>numpol</b>
number of polices bound to label.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show responder global

