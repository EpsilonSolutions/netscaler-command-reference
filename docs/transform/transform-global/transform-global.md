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



##Example

bind transform global pol9 9

##unbind transform global

Unbinds the specified URL Transformation policy from URL Transformation global.


##Synopsys

unbind transform global &lt;policyName> [-type ( REQ_OVERRIDE | REQ_DEFAULT )] [-priority &lt;positive_integer>]


##Arguments

<b>policyName</b>
The name of the policy to be unbound.

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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



##Example

show transform global

