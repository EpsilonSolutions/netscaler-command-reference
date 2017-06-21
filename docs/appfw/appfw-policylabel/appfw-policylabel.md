#appfw policylabel

The following operations can be performed on "appfw policylabel":


[add](#add-appfw-policylabel) | [rm](#rm-appfw-policylabel) | [bind](#bind-appfw-policylabel) | [unbind](#unbind-appfw-policylabel) | [show](#show-appfw-policylabel) | [stat](#stat-appfw-policylabel) | [rename](#rename-appfw-policylabel)

##add appfw policylabel

Creates a user-defined application firewall policy label.


##Synopsys

add appfw policylabel &lt;labelName> &lt;policylabeltype>


##Arguments

<b>labelName</b>
Name for the policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the policy label is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy label" or 'my policy label').

<b>policylabeltype</b>
Type of transformations allowed by the policies bound to the label. Always http_req for application firewall policy labels.
Possible values: http_req



##Example

add appfw policylabel appfw_label http_req

##rm appfw policylabel

Removes the specified application firewall policy label.


##Synopsys

rm appfw policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the application firewall policy label to remove.



##Example

rm appfw policylabel appfw_label

##bind appfw policylabel

Binds the specified application firewall policy to the specified policy label.


##Synopsys

bind appfw policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is set to Policy Label.

<b>policyName</b>
Name of the application firewall policy to bind to the policy label.

<b>priority</b>
Priority with which the policy is to be bound.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher priority number.
* END - End policy evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
* If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
* If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is smaller than the current policy's priority number.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of policy label to invoke if the current policy evaluates to TRUE and the invoke parameter is set. Available settings function as follows:
* reqvserver. Invoke the unnamed policy label associated with the specified request virtual server.
* policylabel. Invoke the specified user-defined policy label.
Possible values: reqvserver, policylabel



##Example

	i)	bind appfw policylabel trans_http_url pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind appfw policylabel trans_http_url pol_2 2

##unbind appfw policylabel

Unbinds the specified application firewall policy from the specified policy label.  See the bind appfw policylabel command for descriptions of the parameters.


##Synopsys

unbind appfw policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name for the policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the policy label is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy label" or 'my policy label').

<b>policyName</b>
Name of the application firewall policy to bind to the policy label.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind appfw policylabel appfw_label

##show appfw policylabel

Displays the current settings for the specified application firewall policy label.If no policy label is specified, displays a list of all application firewall policy labels currently configured on the NetScaler appliance.


##Synopsys

show appfw policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the application firewall policy label.



##Outputs

<b>stateflag</b>

<b>policylabeltype</b>
Type of transformations allowed by the policies bound to the label. Always http_req for application firewall policy labels.

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the application firewall policy to bind to the policy label.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Must be unique within a group of policies that are bound to the same bind point or label. Policies are evaluated in the order of their priority numbers.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of policy label to invoke if the current policy evaluates to TRUE and the invoke parameter is set. Available settings function as follows:
* reqvserver. Invoke the unnamed policy label associated with the specified request virtual server.
* policylabel. Invoke the specified user-defined policy label.

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is set to Policy Label.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show appfw policylabel appfw_label	ii)	show appfw policylabel

##stat appfw policylabel

Displays statistics for the specified application firewall policy label.If no application firewall policy label is specified, displays abbreviated statistics for all application firewall policy labels.


##Synopsys

stat appfw policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the application firewall policy label.

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

<ul><li><a href="../../..//">stat appfw</a></li><li><a href="../../../#stat-appfw-pr/#stat-appfw-pr">stat appfw profile</a></li><li><a href="../../../stat-appfw-p/stat-appfw-p">stat appfw policy</a></li></ul>



##rename appfw policylabel

Renames an application firewall policy label.


##Synopsys

rename appfw policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Existing name of the application firewall policy label.

<b>newName</b>
The new name of the application firewall policylabel.



##Example

rename appfw policylabel oldname newname

