#rewrite global

The following operations can be performed on "rewrite global":


[bind](#bind-rewrite-global) | [unbind](#unbind-rewrite-global) | [show](#show-rewrite-global)

##bind rewrite global

Activates the specified rewrite policy globally.


##Synopsys

bind rewrite global &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the rewrite policy to activate.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Must be unique within the label. Policies are evaluated in the order of their priorities, and the first policy that matches the request or response is applied.
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
*  The expression evaluates to a priority number that is smaller than the current policy?s priority number.
*  The expression evaluates to a priority number that is between the current policy?s priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
Bind point to which to bind the policy. Available settings function as follows:
* REQ_OVERRIDE - Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT - Binds the policy to the default request queue.
* RES_OVERRIDE - Response override. Binds the policy to the priority response queue.
RES_DEFAULT - Binds the policy to the default response queue.
OTHERTCP_REQ_OVERRIDE - Binds the policy to the non-HTTP TCP priority request queue.
OTHERTCP_REQ_DEFAULT - Binds the policy to the non-HTTP TCP default request queue.
OTHERTCP_RES_OVERRIDE - Binds the policy to the non-HTTP TCP priority response queue.
OTHERTCP_RES_DEFAULT - Binds the policy to the non-HTTP TCP default response queue.
SIPUDP_REQ_OVERRIDE - Binds the policy to the SIP priority request queue.
SIPUDP_REQ_DEFAULT - Binds the policy to the SIP default request queue.
SIPUDP_RES_OVERRIDE - Binds the policy to the SIP priority response queue.
SIPUDP_RES_DEFAULT - Binds the policy to the SIP default response queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, OTHERTCP_RES_OVERRIDE, OTHERTCP_RES_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPUDP_RES_OVERRIDE, SIPUDP_RES_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, SIPTCP_RES_OVERRIDE, SIPTCP_RES_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, DIAMETER_RES_OVERRIDE, DIAMETER_RES_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, RADIUS_RES_OVERRIDE, RADIUS_RES_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT, DNS_RES_OVERRIDE, DNS_RES_DEFAULT

<b>invoke</b>
Terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* resvserver - Forward the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.
Possible values: reqvserver, resvserver, policylabel

<b>labelName</b>
* If labelType is policylabel, name of the policy label to invoke. 
* If labelType is reqvserver or resvserver, name of the virtual server to which to forward the request of response.



##Example

	i)	bind rewrite global pol9 9	ii)	bind rewrite global pol9 9 120	iii)	bind rewrite global pol9 9 "HTTP.REQ.HEADER(\\\\"qh3\\\\").TYPECAST_NUM_T(DECIMAL)"	

##unbind rewrite global

Unbinds the specified rewrite policy from rewrite global. See the bind rewrite global command for a description of the parameters.


##Synopsys

unbind rewrite global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Name of the rewrite policy to deactivate.

<b>type</b>
The bindpoint from which to unbind.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, OTHERTCP_RES_OVERRIDE, OTHERTCP_RES_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPUDP_RES_OVERRIDE, SIPUDP_RES_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, SIPTCP_RES_OVERRIDE, SIPTCP_RES_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, DIAMETER_RES_OVERRIDE, DIAMETER_RES_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, RADIUS_RES_OVERRIDE, RADIUS_RES_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT, DNS_RES_OVERRIDE, DNS_RES_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind rewrite global pol9

##show rewrite global

Displays the list of policies bound to the specified rewrite global policy bank. If no policy bank is specified, displays a list of all policies bound to rewrite global.


##Synopsys

show rewrite global [-type &lt;type>]


##Arguments

<b>type</b>
The bindpoint to which to policy is bound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, OTHERTCP_RES_OVERRIDE, OTHERTCP_RES_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPUDP_RES_OVERRIDE, SIPUDP_RES_DEFAULT, SIPTCP_REQ_OVERRIDE, SIPTCP_REQ_DEFAULT, SIPTCP_RES_OVERRIDE, SIPTCP_RES_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, DIAMETER_RES_OVERRIDE, DIAMETER_RES_DEFAULT, RADIUS_REQ_OVERRIDE, RADIUS_REQ_DEFAULT, RADIUS_RES_OVERRIDE, RADIUS_RES_DEFAULT, DNS_REQ_OVERRIDE, DNS_REQ_DEFAULT, DNS_RES_OVERRIDE, DNS_RES_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the rewrite policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* resvserver - Forward the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
* If labelType is policylabel, name of the policy label to invoke. 
* If labelType is reqvserver or resvserver, name of the virtual server to which to forward the request of response.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flowType</b>
flowtype of the bound rewrite policy.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show rewrite global

