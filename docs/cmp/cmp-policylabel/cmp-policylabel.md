#cmp policylabel

The following operations can be performed on "cmp policylabel":


[add](#add-cmp-policylabel) | [rm](#rm-cmp-policylabel) | [bind](#bind-cmp-policylabel) | [unbind](#unbind-cmp-policylabel) | [show](#show-cmp-policylabel) | [stat](#stat-cmp-policylabel) | [rename](#rename-cmp-policylabel)

##add cmp policylabel

Creates a user-defined HTTP compression policy label for default-syntax policies. Policies that you bind to the label are evaluated only if you call the label from another policy.


##Synopsys

add cmp policylabel &lt;labelName> -type ( REQ | RES )


##Arguments

<b>labelName</b>
Name of the HTTP compression policy label. Must begin with a letter, number, or the underscore character (_). Additional characters allowed, after the first character, are the hyphen (-), period (.) pound sign (#), space ( ), at sign (@), equals (=), and colon (:). The name must be unique within the list of policy labels for compression policies. Can be renamed after the policy label is created. 
            The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp policylabel" or 'my cmp policylabel').

<b>type</b>
Type of packets (request packets or response) against which to match the policies bound to this policy label.
Possible values: REQ, RES



##Example

add cmp policylabel cmp_pol_label -type REQ

##rm cmp policylabel

Removes an HTTP compression policy label.


##Synopsys

rm cmp policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the HTTP compression policy label to be removed.



##Example

rm cmp policylabel cmp_pol_label

##bind cmp policylabel

Binds a default-syntax HTTP compression policy to an HTTP compression policy label.


##Synopsys

bind cmp policylabel &lt;labelName> -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.

<b>policyName</b>
Name of the compression policy to bind to the label.

<b>priority</b>
Integer specifying the priority of the policy. The lower the number, the higher the priority. By default, polices within a label are evaluated in the order of their priority numbers.
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
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next higher priority number in the original label.

<b>labelType</b>
Type of policy label invocation.
Possible values: reqvserver, resvserver, policylabel



##Example

bind cmp policylabel cmp_pol_label -policyName cmp_pol -priority 1

##unbind cmp policylabel

Unbinds a default-syntax HTTP compression policy from an HTTP compression policy label.


##Synopsys

unbind cmp policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the HTTP compression policy label from which to unbind the policy.

<b>policyName</b>
Name of the HTTP compression policy to unbind from the policy label.

<b>priority</b>
Priority of the NOPOLICY to unbind. Required only to unbind a NOPOLICY, if it has been bound to this policy label.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind cmp policylabel cmp_pol_label cmp_pol

##show cmp policylabel

Displays details of configured HTTP compression policy labels.


##Synopsys

show cmp policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the HTTP compression policy label for which to display details.



##Outputs

<b>stateflag</b>

<b>type</b>
Type of packets (request packets or response) against which to match the policies bound to this policy label.

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
The compression policy name.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next higher priority number in the original label.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound compression policy.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show cmp policylabel cmp_pol_label	ii)	show cmp policylabel

##stat cmp policylabel

Displays statistics for all compression policy labels.


##Synopsys

stat cmp policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the compression policy label for which to display statistics. If not specified, statistics are displayed for all compression policy labels.

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

<ul><li><a href="../../..//">stat cmp</a></li><li><a href="../../../-cmp-p/-cmp-p">stat cmp policy</a></li></ul>



##rename cmp policylabel

Renames a compression policylabel.


##Synopsys

rename cmp policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Existing name of the policy label.

<b>newName</b>
New name for the compression policy label. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
                        The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp policylabel" or 'my cmp policylabel').



##Example

rename cmp policylabel oldname newname

