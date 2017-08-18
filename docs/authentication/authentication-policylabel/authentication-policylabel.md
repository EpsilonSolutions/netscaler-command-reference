#authentication policylabel

The following operations can be performed on "authentication policylabel":


[add](#add-authentication-policylabel) | [rm](#rm-authentication-policylabel) | [bind](#bind-authentication-policylabel) | [unbind](#unbind-authentication-policylabel) | [rename](#rename-authentication-policylabel) | [show](#show-authentication-policylabel) | [stat](#stat-authentication-policylabel)

##add authentication policylabel

Creates a user-defined authentication policy label.


##Synopsys

add authentication policylabel &lt;labelName> [-type ( AAATM_REQ | RBA_REQ )] [-comment &lt;string>] [-loginSchema &lt;string>]


##Arguments

<b>labelName</b>
Name for the new authentication policy label.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy label" or 'authentication policy label').

<b>type</b>
Type of feature (aaatm or rba) against which to match the policies bound to this policy label.
Possible values: AAATM_REQ, RBA_REQ
Default value: AAATM_REQ

<b>comment</b>
Any comments to preserve information about this authentication policy label.

<b>loginSchema</b>
Login schema associated with authentication policy label. Login schema defines the UI rendering by providing customization option of the fields. If user intervention is not needed for a given factor such as group extraction, a loginSchema whose authentication schema is "noschema" should be used.



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

<b>priority</b>
Positive integer specifying the priority of the policy. The lower the number, the higher the priority. Policies within a label are evaluated in the order of their priority numbers.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to be evaluated if the current policy evaluates to TRUE.  Specify one of the following values:
*  NEXT - Evaluate the policy with the next higher priority number.
*  END - End policy evaluation.
*  USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
*  If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
*  If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
*  If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
*  The expression is invalid.
*  The expression evaluates to a priority number that is smaller than the current policy's priority number.
*  The expression evaluates to a priority number that is between the current policy's priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>nextFactor</b>
On success invoke label.



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
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy label" or 'authentication policy label').

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

<b>comment</b>
Any comments to preserve information about this authentication policy label.

<b>loginSchema</b>
Login schema associated with authentication policy label. Login schema defines the UI rendering by providing customization option of the fields. If user intervention is not needed for a given factor such as group extraction, a loginSchema whose authentication schema is "noschema" should be used.

<b>type</b>
Type of feature (aaatm or rba) against which to match the policies bound to this policy label.

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

<ul><li><a href="../../../ation-policy.html#stat-authentication-p/ation-policy.html#stat-authentication-p">stat authentication Policy</a></li><li><a href="../../../ation-vserver.html#stat-authentication-vs/ation-vserver.html#stat-authentication-vs">stat authentication vserver</a></li><li><a href="../../../ation-samlidppolicy.html#stat-authentication-samlidpp/ation-samlidppolicy.html#stat-authentication-samlidpp">stat authentication samlIdPPolicy</a></li><li><a href="../../../ation-loginschemapolicy.html#stat-authentication-loginschemap/ation-loginschemapolicy.html#stat-authentication-loginschemap">stat authentication loginSchemaPolicy</a></li></ul>



