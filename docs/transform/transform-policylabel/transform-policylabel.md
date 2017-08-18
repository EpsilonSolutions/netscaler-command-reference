#transform policylabel

The following operations can be performed on "transform policylabel":


[add](#add-transform-policylabel) | [rm](#rm-transform-policylabel) | [bind](#bind-transform-policylabel) | [unbind](#unbind-transform-policylabel) | [show](#show-transform-policylabel) | [stat](#stat-transform-policylabel) | [rename](#rename-transform-policylabel)

##add transform policylabel

Creates a URL Transformation policy label.A policy label is a tool for evaluating a set of policies in a specified order. By using a policy label, you can configure the URL Transformation feature to choose the next policy, invoke a different policy label, or terminate policy evaluation completely by looking at whether the previous policy evaluated to TRUE or FALSE.


##Synopsys

add transform policylabel &lt;labelName> &lt;policylabeltype>


##Arguments

<b>labelName</b>
Name for the policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the URL Transformation policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policylabel? or ?my transform policylabel).

<b>policylabeltype</b>
Types of transformations allowed by the policies bound to the label. For URL transformation, always http_req (HTTP Request).
Possible values: http_req



##Example

add transform policylabel trans_policylabel http_req

##rm transform policylabel

Removes a URL Transformation policy label.


##Synopsys

rm transform policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the policy label to remove.



##Example

rm transform policylabel trans_policylabel

##bind transform policylabel

Binds the specified URL Transformation policy to the specified policy label.


##Synopsys

bind transform policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the policy label to be invoke if the current policy evaluates to TRUE, the invoke parameter is set, and the label type is Policy Label.

<b>policyName</b>
Name of the URL Transformation policy to bind to the policy label.

<b>priority</b>
Positive integer specifying the priority of the policy within the policy label. A lower number specifies a higher priority. Must be unique within the list of policies bound to the label. Policies are evaluated in the order of their priority numbers, and the first policy that matches is applied.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Optional expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
*  NEXT - Evaluate the policy with the next higher priority number.
*  END - End policy evaluation.
*  USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A PCRE-compatible regular expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher priority number is evaluated next.
* If the expression evaluates to a number that is larger than the largest priority number, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is smaller than the current policy's priority number.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* policylabel - Invoke the specified policy label.
Possible values: reqvserver, policylabel



##Example

	i)	bind transform policylabel trans_policylabel pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind transform policylabel trans_policylabel pol_2 2

##unbind transform policylabel

Unbinds the specified URL Transformation policy from the specified policy label.


##Synopsys

unbind transform policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the label from which to unbind the policy.

<b>policyName</b>
Name of the label to which to bind the policy.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind transform policylabel trans_policylabel pol_1

##show transform policylabel

Displays the current settings for the specified URL Transformation policy label.If no policy label is specified, displays a list of all URL Transformation policy labels currently configured on the NetScaler appliance.


##Synopsys

show transform policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name for the policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the URL Transformation policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policylabel? or ?my transform policylabel).



##Outputs

<b>stateflag</b>

<b>policylabeltype</b>
Types of transformations allowed by the policies bound to the label. For URL transformation, always http_req (HTTP Request).

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the URL Transformation policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
Name of the policy label.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show transform policylabel trans_policylabel	ii)	show transform policylabel

##stat transform policylabel

Displays statistics for the specified URL Transformation policy label.If no policy label name is provided, displays abbreviated statistics for all URL Transformation policy labels currently configured on the NetScaler appliance.


##Synopsys

stat transform policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
The name of the URL Transformation policy label.

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

<b>Policy Label Hits (Hits)</b>
Number of times policy label was invoked.



##Related Commands

<ul><li><a href="../../../cy.html#stat-transform-p/cy.html#stat-transform-p">stat transform policy</a></li></ul>



##rename transform policylabel

Renames a URL Transformation policy label.


##Synopsys

rename transform policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Current name of the policy label.

<b>newName</b>
New name for the policy label.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform policylabel? or ?my transform policylabel).



##Example

rename transform policylabel oldname newname

