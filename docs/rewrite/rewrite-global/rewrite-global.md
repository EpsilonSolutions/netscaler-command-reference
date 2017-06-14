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



##Example

	i)	bind rewrite global pol9 9	ii)	bind rewrite global pol9 9 120	iii)	bind rewrite global pol9 9 "HTTP.REQ.HEADER(\\\\"qh3\\\\").TYPECAST_NUM_T(DECIMAL)"	

##unbind rewrite global

Unbinds the specified rewrite policy from rewrite global. See the bind rewrite global command for a description of the parameters.


##Synopsys

unbind rewrite global &lt;policyName> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Name of the rewrite policy to deactivate.

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
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, OTHERTCP_REQ_OVERRIDE, OTHERTCP_REQ_DEFAULT, OTHERTCP_RES_OVERRIDE, OTHERTCP_RES_DEFAULT, SIPUDP_REQ_OVERRIDE, SIPUDP_REQ_DEFAULT, SIPUDP_RES_OVERRIDE, SIPUDP_RES_DEFAULT, DIAMETER_REQ_OVERRIDE, DIAMETER_REQ_DEFAULT, DIAMETER_RES_OVERRIDE, DIAMETER_RES_DEFAULT

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



##Example

show rewrite global

