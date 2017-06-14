#responder policylabel

The following operations can be performed on "responder policylabel":


[add](#add-responder-policylabel) | [rm](#rm-responder-policylabel) | [bind](#bind-responder-policylabel) | [unbind](#unbind-responder-policylabel) | [show](#show-responder-policylabel) | [stat](#stat-responder-policylabel) | [rename](#rename-responder-policylabel)

##add responder policylabel

Creates a user-defined responder policy label, to which you can bind policies. A policy label is a tool for evaluating a set of policies in a specified order. By using a policy label, you can configure the responder feature to choose the next policy, invoke a different policy label, or terminate policy evaluation completely by looking at whether the previous policy evaluated to TRUE or FALSE.


##Synopsys

add responder policylabel &lt;labelName> [-policylabeltype &lt;policylabeltype>] [-comment &lt;string>]


##Arguments

<b>labelName</b>
Name for the responder policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the responder policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder policy label" or my responder policy label').

<b>policylabeltype</b>
Type of responses sent by the policies bound to this policy label. Types are:
* HTTP - HTTP responses. 
* OTHERTCP - NON-HTTP TCP responses.
* SIP_UDP - SIP responses.
* MYSQL - SQL responses in MySQL format.
* MSSQL - SQL responses in Microsoft SQL format.
* NAT - NAT response.
Possible values: HTTP, OTHERTCP, SIP_UDP, MYSQL, MSSQL, NAT, DIAMETER
Default value: NS_PLTMAP_RSP_REQ

<b>comment</b>
Any comments to preserve information about this responder policy label.



##Example

add responder policylabel resp_lab

##rm responder policylabel

Removes a responder policy label.


##Synopsys

rm responder policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the responder policy label to remove.



##Example

rm responder policylabel resp_lab

##bind responder policylabel

Binds the specified responder policy to the specified policy label.


##Synopsys

bind responder policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the responder policy label to which to bind the policy.

<b>policyName</b>
Name of the policy to bind to the responder policy label.



##Example

	i)	bind responder policylabel resp_lab pol_resp 1 2	ii)	bind responder policylabel resp_lab pol_resp 1 2 -invoke vserver CURRENT

##unbind responder policylabel

Unbinds the specified responder policy from the specified policy label.


##Synopsys

unbind responder policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name for the responder policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the responder policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my responder policy label" or my responder policy label').

<b>policyName</b>
The name of the policy to be unbound.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind responder policylabel resp_lab pol_resp

##show responder policylabel

Displays the current settings for the specified responder policy label.If no policy label is specified, displays a list of all responder policy labels currently configured on the NetScaler appliance, with abbreviated settings.


##Synopsys

show responder policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the responder policy label.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>policylabeltype</b>
The type of the policy label.

<b>stateflag</b>

<b>numpol</b>
number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the responder policy.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
If the current policy evaluates to TRUE, terminate evaluation of policies bound to the current policy label and evaluate the specified policy label.

<b>labelType</b>
Type of policy label to invoke. Available settings function as follows:
* vserver - Invoke an unnamed policy label associated with a virtual server.
* policylabel - Invoke a user-defined policy label.

<b>labelName</b>
* If labelType is policylabel, name of the policy label to invoke. 
* If labelType is reqvserver or resvserver, name of the virtual server.

<b>flags</b>

<b>comment</b>
Any comments to preserve information about this responder policy label.

<b>devno</b>

<b>count</b>



##Example

	i)	show responder policylabel resp_lab	ii)	show responder policylabel

##stat responder policylabel

Displays statistics for the specified responder policy label.If no policy label name is provided, displays abbreviated statistics for all responder policy labels currently configured on the NetScaler appliance.


##Synopsys

stat responder policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the responder policy label.

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

<ul><li><a href="../../../cy.html#stat-responder-p/cy.html#stat-responder-p">stat responder policy</a></li></ul>



##rename responder policylabel

Renames the specified responder policy label.


##Synopsys

rename responder policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Current name of the responder policy label.

<b>newName</b>
New name for the responder policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.



##Example

rename responder policylabel oldname newname

