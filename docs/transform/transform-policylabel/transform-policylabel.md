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
Name of the URL Transformation policy label to which to bind the policy.

<b>policyName</b>
Name of the URL Transformation policy to bind to the policy label.



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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

