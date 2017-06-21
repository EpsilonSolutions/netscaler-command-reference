#appflow policylabel

The following operations can be performed on "appflow policylabel":


[add](#add-appflow-policylabel) | [rm](#rm-appflow-policylabel) | [bind](#bind-appflow-policylabel) | [unbind](#unbind-appflow-policylabel) | [rename](#rename-appflow-policylabel) | [show](#show-appflow-policylabel)

##add appflow policylabel

Creates a user-defined AppFlow policy label. You can bind AppFlow policies to the AppFlow policy label.


##Synopsys

add appflow policylabel &lt;labelName> [-policylabeltype ( HTTP | OTHERTCP )]


##Arguments

<b>labelName</b>
Name of the AppFlow policy label. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at
(@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow policylabel" or 'my appflow policylabel').

<b>policylabeltype</b>
Type of traffic evaluated by the policies bound to the policy label.
Possible values: HTTP, OTHERTCP
Default value: HTTP



##Example

add appflow policylabel appflow_pol_label

##rm appflow policylabel

Removes an AppFlow policy label.


##Synopsys

rm appflow policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the policy label to be removed.



##Example

rm appflow policylabel appflow_pol_label

##bind appflow policylabel

Binds an AppFlow policy to an AppFlow policy label.


##Synopsys

bind appflow policylabel &lt;labelName> -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.

<b>policyName</b>
Name of the policy to bind to the policy label.

<b>priority</b>
Priority assigned to the policy. The lower the number, the higher the priority.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the priority of the next policy, within the policy label, to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
* NEXT - Evaluate the policy with the next higher numbered priority.
* END - Stop evaluation.
* USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* An expression that evaluates to a number.
If you specify an expression, it's evaluation result determines the next policy to evaluate, as follows: 
* If the expression evaluates to a higher numbered priority, that policy is evaluated next.
* If the expression evaluates to the priority of the current policy, the policy with the next higher priority number is evaluated next.
* If the expression evaluates to a priority number that is numerically higher than the highest priority number, policy evaluation ends.
An UNDEF event is triggered if:
* The expression is invalid.
* The expression evaluates to a priority number that is numerically lower than the current policy's priority.
* The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to be invoked.
Possible values: vserver, policylabel



##Example

bind appflow policylabel appflow_pol_label -policyName appflow_pol -priority 1

##unbind appflow policylabel

Unbinds an AppFlow policy from an AppFlow policy label.


##Synopsys

unbind appflow policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the policy label from which to unbind a policy.

<b>policyName</b>
Name of the policy to unbind.

<b>priority</b>
Priority of the NOPOLICY to be unbound. Applicable only if a NOPOLICY has been bound to the policy label. 
Minimum value: 1
Maximum value: 2147483647



##Example

unbind appflow policylabel appflow_pol_label appflow_pol

##rename appflow policylabel

Renames an AppFlow policy label.


##Synopsys

rename appflow policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Existing name of the policylabel.

<b>newName</b>
New name for the policy label. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. 
                    The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow policylabel" or 'my appflow policylabel')



##Example

rename appflow policylabel old_name new_name

##show appflow policylabel

Displays information about all AppFlow policy labels, or detailed information about the specified policy label.


##Synopsys

show appflow policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the policy label about which to display detailed information.



##Outputs

<b>stateflag</b>

<b>policylabeltype</b>
Type of traffic evaluated by the policies bound to the policy label.

<b>numpol</b>
Number of polices bound to the policy label.

<b>hits</b>
Number of times the policy label was invoked.

<b>policyName</b>
Name of the AppFlow policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority.

<b>labelType</b>
Type of policy label to be invoked.

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound AppFlow policy.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show appflow policylabel appflow_pol_label	ii)	show appflow policylabel

