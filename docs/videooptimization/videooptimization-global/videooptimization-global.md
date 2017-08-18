#videooptimization global

The following operations can be performed on "videooptimization global":


[bind](#bind-videooptimization-global) | [unbind](#unbind-videooptimization-global) | [show](#show-videooptimization-global)

##bind videooptimization global

Activates the specified video optimization policy for all requests and responses sent to the NetScaler appliance.


##Synopsys

bind videooptimization global -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-type &lt;type>] [-invoke  (-labelType ( vserver | policylabel )  -labelName &lt;string>) ]


##Arguments

<b>policyName</b>
Name of the video optimization policy to activate.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Policies are evaluated in the order of their priority numbers, and the first policy that matches the request is applied.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.

<b>type</b>
Bind point to which to bind the policy. Available settings function as follows:
* REQ_OVERRIDE - Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT - Binds the policy to the default request queue.
* RES_OVERRIDE - Response override.
* RES_DEFAULT - Binds the policy to the default response queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or
evaluate the specified policy label.

<b>labelType</b>
Type of invocation, Available settings function as follows:
* vserver - Forward the request to the specified virtual server.
* policylabel - Invoke the specified policy label.
Possible values: vserver, policylabel

<b>labelName</b>
Name of the policy label to invoke. If the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is policylabel.



##Example

	i)	bind videooptimization global -policyName pol1 -priority 100

##unbind videooptimization global

Unbind the specified video optimization policy from videooptimization global.


##Synopsys

unbind videooptimization global -policyName &lt;string> [-type &lt;type>] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
Name of the policy to unbind.

<b>type</b>
The bindpoint from which the policy is to be unbound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT

<b>priority</b>
Priority of the videooptimization policy to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind videooptimization global pol1

##show videooptimization global

Displays the list of policies bound to the specified video optimization global bindpoint.If bindpoint is not specified, displays a list of all policies bound to video optimization global.


##Synopsys

show videooptimization global [-type &lt;type>]


##Arguments

<b>type</b>
Specifies the bind point whose policies you want to display.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the video optimization policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>numpol</b>
number of polices bound.

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show videooptimization global

