#cmp global

The following operations can be performed on "cmp global":


[bind](#bind-cmp-global) | [unbind](#unbind-cmp-global) | [show](#show-cmp-global)

##bind cmp global

Binds (activates) the compression policy globally.Note that the compression feature requires a compression license. When you enable the compression feature, all of the built-in compression policies are bound globally.


##Synopsys

bind cmp global &lt;policyName> [-priority &lt;positive_integer>] [-state ( ENABLED | DISABLED )] [-gotoPriorityExpression &lt;expression>] [-type &lt;type>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>policyName</b>
Name of the policy to bind globally.

<b>priority</b>
Positive integer specifying the priority of the policy. The lower the number, the higher the priority. By default, polices within a label are evaluated in the order of their priority numbers.
In the configuration utility, you can click the Priority field and edit the priority level or drag the entry to a new position in the list. If you drag the entry to a new position, the priority level is updated automatically.
Minimum value: 1
Maximum value: 2147483647

<b>state</b>
Operational state of the globally bound policy.
Possible values: ENABLED, DISABLED
Default value: ENABLED

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

<b>type</b>
Global bind point, specifying where to bind the policy. This is relevant for advanced (default-syntax) policies only.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE
Default value: NONE

<b>invoke</b>
Invoke policies bound to a virtual server or a policy label. After the invoked policies are evaluated, the flow returns to the policy with the next priority. Applicable only for default-syntax policies.

<b>labelType</b>
Type of policy label invocation. This argument is relevant only for advanced (default-syntax) policies.
Possible values: reqvserver, resvserver, policylabel

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE. Applicable only to advanced (default-syntax) policies.



##Example

add cmp policy pdf_cmp -rule "RES.HTTP.HEADER Content-Type CONTAINS application/pdf" -resAction COMPRESSAfter creating the above compression policy, you must activate it by binding it globally:bind cmp global pdf_cmpAfter binding pdf_cmp compression policy globally, the policy gets activated and the NetScaler system will perform compression for the pdf files.To view the globally active compression policies, enter the following command:&gt; show cmp global        5 Globally Active Compression Policies:1)      Policy Name: ns_cmp_content_type        Priority: 02)      Policy Name: ns_nocmp_mozilla_47        Priority: 03)      Policy Name: ns_cmp_mscss       Priority: 04)      Policy Name: ns_cmp_msapp       Priority: 05)      Policy Name: pdf_cmp    Priority: 0 Done

##unbind cmp global

Deactivates a globally bound HTTP compression policy.


##Synopsys

unbind cmp global &lt;policyName> [-type &lt;type>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the compression policy to unbind.

<b>type</b>
Bind point, specifying from where to unbind the policy. Applicable only to advanced (default-syntax) policies.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT, NONE

<b>priority</b>
Integer specifying the priority of the policy. The lower the number, the higher the priority. By default, polices within a label are evaluated in the order of their priority numbers. 
Note that in the configuration utility, you can click the Priority field and edit the priority level or drag the entry to a new position in the list. If you drag the entry to a new position, the priority level is updated automatically.
Minimum value: 1
Maximum value: 2147483647



##Example

To view the globally active compression policies, enter the following command:&gt; show cmp global        5 Globally Active Compression Policies:1)      Policy Name: ns_cmp_content_type        Priority: 02)      Policy Name: ns_nocmp_mozilla_47        Priority: 03)      Policy Name: ns_cmp_mscss       Priority: 04)      Policy Name: ns_cmp_msapp       Priority: 05)      Policy Name: pdf_cmp    Priority: 0 DoneTo deactivate this globally active compression policy on the NetScaler system, enter the following command:unbind cmp global pdf_cmp

##show cmp global

Displays the globally bound HTTP compression policies.


##Synopsys

show cmp global [-type &lt;type>]


##Arguments

<b>type</b>
Bind point to which the policy is bound.
Possible values: REQ_OVERRIDE, REQ_DEFAULT, RES_OVERRIDE, RES_DEFAULT



##Outputs

<b>stateflag</b>

<b>policyName</b>
The name of the globally bound HTTP compression policy.

<b>priority</b>
Positive integer specifying the priority of the policy. The lower the number, the higher the priority. By default, polices within a label are evaluated in the order of their priority numbers.
In the configuration utility, you can click the Priority field and edit the priority level or drag the entry to a new position in the list. If you drag the entry to a new position, the priority level is updated automatically.

<b>state</b>
The current state of the policy binding. This attribute is relevant only for CLASSIC policies.

<b>numpol</b>
The number of policies bound to the bindpoint.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE

<b>invoke</b>
Invoke flag. This attribute is relevant only for ADVANCED policies

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>policyType</b>
Policy type (Classic/Advanced) to be bound.Used for display.

<b>globalBindType</b>

<b>devno</b>

<b>count</b>



##Example

&gt; show cmp global        4 Globally Active Compression Policies:1)      Policy Name: ns_cmp_content_type        Priority: 02)      Policy Name: ns_nocmp_mozilla_47        Priority: 03)      Policy Name: ns_cmp_mscss       Priority: 04)      Policy Name: ns_cmp_msapp       Priority: 0 Done

