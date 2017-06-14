#authentication policylabel

The following operations can be performed on "authentication policylabel":


[add](#add-authentication-policylabel) | [rm](#rm-authentication-policylabel) | [bind](#bind-authentication-policylabel) | [unbind](#unbind-authentication-policylabel) | [rename](#rename-authentication-policylabel) | [show](#show-authentication-policylabel) | [stat](#stat-authentication-policylabel)

##add authentication policylabel

Creates a user-defined authentication policy label.


##Synopsys

add authentication policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name for the new authentication policy label. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication policy label? or ?authentication policy label?).



##Example

add authentication policylabel trans_http_url

##rm authentication policylabel

Removes an authorization policy label.


##Synopsys

rm authentication policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the authorization policy label to remove.



##Example

rm authorization policylabel trans_http_url

##bind authentication policylabel

Binds an authentication policy to &lt;authentication policy label>.


##Synopsys

bind authentication policylabel &lt;labelName> -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-nextFactor &lt;string>]


##Arguments

<b>labelName</b>
Name of the authentication policy label to which to bind the policy.

<b>policyName</b>
Name of the authentication policy to bind to the policy label.



##Example

	i)	bind authentication policylabel authn_label_1 -policyName authn_pol_1 -priority 1	ii)	bind authentication policylabel authn_label_2 -policyName authn_pol_2 -priority 2 -nextFactor authn_label_1 -gotoPriorityExpression next

##unbind authentication policylabel

Unbinds the specified policy from the specified authorization policy label.


##Synopsys

unbind authentication policylabel &lt;labelName> -policyName &lt;string> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name for the new authentication policy label. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication policy label? or ?authentication policy label?).

<b>policyName</b>
Name of the authentication policy to bind to the policy label.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind authorization policylabel trans_http_url pol_1

##rename authentication policylabel

Rename a authn policy label.


##Synopsys

rename authentication policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
The name of the auth policy label

<b>newName</b>
The new name of the auth policy label



##Example

rename authn policy label oldname newname

##show authentication policylabel

Displays the current settings for the specified authentication policy label.If no policy name is provided, displays a list of all authentication policy labels currently configured on the NetScaler appliance.


##Synopsys

show authentication policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the authorization policy label.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the authentication policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound authentication policy.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>nextFactor</b>
On success invoke label.

<b>devno</b>

<b>count</b>



##Example

	i)	show authentication policylabel trans_http_url	ii)	show authentication policylabel

##stat authentication policylabel

Displays statistics for the specified authentication policy label.If no authentication policy label is specified, displays a list of all authentication policy labels.


##Synopsys

stat authentication policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the authentication policy label.

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

<ul><li><a href="../../../ation-policy.html#stat-authentication-p/ation-policy.html#stat-authentication-p">stat authentication Policy</a></li><li><a href="../../../ation-vserver.html#stat-authentication-vs/ation-vserver.html#stat-authentication-vs">stat authentication vserver</a></li><li><a href="../../../ation-samlidppolicy.html#stat-authentication-samlidpp/ation-samlidppolicy.html#stat-authentication-samlidpp">stat authentication samlIdPPolicy</a></li></ul>



