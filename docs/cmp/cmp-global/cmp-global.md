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



##Example

add cmp policy pdf_cmp -rule "RES.HTTP.HEADER Content-Type CONTAINS application/pdf" -resAction COMPRESSAfter creating the above compression policy, you must activate it by binding it globally:bind cmp global pdf_cmpAfter binding pdf_cmp compression policy globally, the policy gets activated and the NetScaler system will perform compression for the pdf files.To view the globally active compression policies, enter the following command:&gt; show cmp global        5 Globally Active Compression Policies:1)      Policy Name: ns_cmp_content_type        Priority: 02)      Policy Name: ns_nocmp_mozilla_47        Priority: 03)      Policy Name: ns_cmp_mscss       Priority: 04)      Policy Name: ns_cmp_msapp       Priority: 05)      Policy Name: pdf_cmp    Priority: 0 Done

##unbind cmp global

Deactivates a globally bound HTTP compression policy.


##Synopsys

unbind cmp global &lt;policyName> [-type &lt;type>  [-priority &lt;positive_integer>]]


##Arguments

<b>policyName</b>
Name of the compression policy to unbind.



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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>devno</b>

<b>count</b>



##Example

&gt; show cmp global        4 Globally Active Compression Policies:1)      Policy Name: ns_cmp_content_type        Priority: 02)      Policy Name: ns_nocmp_mozilla_47        Priority: 03)      Policy Name: ns_cmp_mscss       Priority: 04)      Policy Name: ns_cmp_msapp       Priority: 0 Done

