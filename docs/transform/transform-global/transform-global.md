#transform global

The following operations can be performed on "transform global":


[bind](#bind-transform-global) | [unbind](#unbind-transform-global) | [show](#show-transform-global)

##bind transform global

Activates the specified URL Transformation policy for all traffic received by this NetScaler appliance.If you set policyName to a name that does not match an existing URL Transformation policy name, this command creates the policy, with the configuration that you specify.


##Synopsys

bind transform global &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-type ( REQ_OVERRIDE | REQ_DEFAULT )] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the policy.
If you want to create the policy as well as activate it, specify a name for the policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policy? or ?my transform policy).

<b>priority</b>
Positive integer specifying the priority of the policy within the list of globally-bound URL transformation policies. A lower number specifies a higher priority. Must be unique within the list. Policies are evaluated in the order of their priorities, and the first policy that matches is applied.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Optional expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A PCRE-compatible regular expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher priority number is evaluated next.
* If the expression evaluates to a number that is larger than the largest priority number, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is smaller than the current policy's priority number.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>type</b>
Bind point to which to bind the policy. Available settings function as follows:
* REQ_OVERRIDE. Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT. Binds the policy to the default request queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forwards the request or response to the specified virtual server or evaluates the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Send the request to the specified request virtual server.
* resvserver - Send the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.
Possible values: reqvserver, resvserver, policylabel

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and the label type is Policy Label.



##Example

bind transform global pol9 9

##unbind transform global

Unbinds the specified URL Transformation policy from URL Transformation global.


##Synopsys

unbind transform global &lt;policyName> [-type ( REQ_OVERRIDE | REQ_DEFAULT )] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
The name of the policy to be unbound.

<b>type</b>
The bindpoint from which the policy is to be unbound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind transform global pol9

##show transform global

Displays the policies bound to the specified URL Transformation global bind point.If no bind point is specified, displays a list of all policies bound to URL Transformation global.


##Synopsys

show transform global [-type ( REQ_OVERRIDE | REQ_DEFAULT )]


##Arguments

<b>type</b>
Specifies the bind point to which to bind the policy. Available settings function as follows:
* REQ_OVERRIDE. Request override. Binds the policy to the priority request queue.
* REQ_DEFAULT. Binds the policy to the default request queue.
Possible values: REQ_OVERRIDE, REQ_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
Name of the transform policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forwards the request or response to the specified virtual server or evaluates the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Send the request to the specified request virtual server.
* resvserver - Send the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and the label type is Policy Label.

<b>flowType</b>
flowtype of the bound transform policy.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>flags</b>

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

show transform global

