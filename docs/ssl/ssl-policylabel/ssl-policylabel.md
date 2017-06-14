#ssl policylabel

The following operations can be performed on "ssl policylabel":


[add](#add-ssl-policylabel) | [rm](#rm-ssl-policylabel) | [bind](#bind-ssl-policylabel) | [unbind](#unbind-ssl-policylabel) | [show](#show-ssl-policylabel)

##add ssl policylabel

Creates an SSL policy label. An SSL policy label can be a control label or a data label.


##Synopsys

add ssl policylabel &lt;labelName> -type ( CONTROL | DATA )


##Arguments

<b>labelName</b>
Name for the SSL policy label.  Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the policy label is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my label" or 'my label').

<b>type</b>
Type of policies that the policy label can contain.
Possible values: CONTROL, DATA



##Example

add ssl policylabel ssl_pol_label -type REQ

##rm ssl policylabel

Removes an SSL policy label.


##Synopsys

rm ssl policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the SSL policy label to remove.



##Example

rm ssl policylabel ssl_pol_label

##bind ssl policylabel

Binds an SSL policy to an SSL policy label and specifies the order in which the policies in the label are to be evaluated.


##Synopsys

bind ssl policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the SSL policy label to which to bind policies.

<b>policyName</b>
Name of the SSL policy to bind to the policy label.



##Example

bind ssl policylabel ssl_pol_label -policyName ssl_pol -priority 1

##unbind ssl policylabel

Unbinds an SSL policy from an SSL policy label.


##Synopsys

unbind ssl policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the SSL policy label from which to unbind policies.

<b>policyName</b>
Name of the SSL policy to unbind.



##Example

unbind ssl policylabel ssl_pol_label ssl_pol

##show ssl policylabel

Displays information about all the SSL policy labels, or displays detailed information about the specified policy label.


##Synopsys

show ssl policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the SSL policy label for which to show detailed information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>type</b>
Type of policies that the policy label can contain.

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the SSL policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke flag.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound SSL policy.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show ssl policylabel ssl_pol_label	ii)	show ssl policylabel

