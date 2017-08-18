#cr policy

The following operations can be performed on "cr policy":


[add](#add-cr-policy) | [rm](#rm-cr-policy) | [set](#set-cr-policy) | [unset](#unset-cr-policy) | [show](#show-cr-policy) | [rename](#rename-cr-policy)

##add cr policy

Creates a cache redirection policy. To associate the new policy with a cache redirection virtual server, use the bind cr vserver command.


##Synopsys

add cr policy &lt;policyName> -rule &lt;expression> [-action &lt;string>] [-logAction &lt;string>]


##Arguments

<b>policyName</b>
Name for the cache redirection policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI: 
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic syntax.
Note:Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: "&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
*  If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in cache redirection action: CACHE/ORIGIN.

<b>logAction</b>
The log action associated with the cache redirection policy



##Related Commands

<ul><li><a href="../../../r-vs/r-vs">add cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">bind cr vserver</a></li><li><a href="../../../r-vs/r-vs">set cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">show cr vserver</a></li><li><a href="../../../d-cr-vs/d-cr-vs">unbind cr vserver</a></li><li><a href="../../../-cr-vs/-cr-vs">unset cr vserver</a></li></ul>



##rm cr policy

Removes a cache redirection policy. You can delete a user-defined cache redirection policy that is not bound to a cache redirection virtual server. If the policy is bound to a virtual server, you must first unbind the policy, and then remove it.


##Synopsys

rm cr policy &lt;policyName>


##Arguments

<b>policyName</b>
Name of the cache redirection policy to remove.



##Related Commands

<ul><li><a href="../../../r-vs/r-vs">add cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">bind cr vserver</a></li><li><a href="../../../r-vs/r-vs">set cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">show cr vserver</a></li><li><a href="../../../d-cr-vs/d-cr-vs">unbind cr vserver</a></li><li><a href="../../../-cr-vs/-cr-vs">unset cr vserver</a></li></ul>



##set cr policy

Changes the specified parameters of an existing cache redirection policy.


##Synopsys

set cr policy &lt;policyName> [-rule &lt;expression>] [-action &lt;string>] [-logAction &lt;string>]


##Arguments

<b>policyName</b>
Name of the cache redirection policy to change.

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic syntax. 
Note: 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. 
For example, you can create a 500-character string as follows: "&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
*  If the expression itself includes double quotation marks, escape the quotations by using the  character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
The cache redirection action name.

<b>logAction</b>
The log action associated with the cache redirection policy



##unset cr policy

Unset logaction for existing cache redirection policy..Refer to the set cr policy command for meanings of the arguments.


##Synopsys

unset cr policy &lt;policyName> -logAction


##Example

unset cr policy pol -logAction

##show cr policy

Displays all existing cache redirection policies, or just the specified policy.


##Synopsys

show cr policy [&lt;policyName>]


##Arguments

<b>policyName</b>
Name of the cache redirection policy to display. If this parameter is omitted, details of all the policies are displayed.



##Outputs

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic syntax.
Note:Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: "&lt;string of 255 characters>" + "&lt;string of 245 characters>"
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
*  If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>domain</b>
Domain name.

<b>action</b>
The CR action name.

<b>vstype</b>
Virtual server type.

<b>hits</b>
Total number of hits.

<b>piHits</b>
Total number of hits.

<b>bindHits</b>
Total number of hits.

<b>piPolicyhits</b>
bind hits for PI CR Policy.

<b>priority</b>
priority of bound policy

<b>flag</b>

<b>stateflag</b>

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>csPolicyType</b>
Indicates whether policy is PI or not.(used only during display)

<b>logAction</b>
The log action associated with the cache redirection policy

<b>labelName</b>
Name of the label invoked.

<b>labelType</b>
The invocation type.

<b>builtin</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>isDefault</b>
A value of true is returned if it is a default cr policy.

<b>devno</b>

<b>count</b>



##Related Commands

<ul><li><a href="../../../r-vs/r-vs">add cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">bind cr vserver</a></li><li><a href="../../../r-vs/r-vs">set cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">show cr vserver</a></li><li><a href="../../../d-cr-vs/d-cr-vs">unbind cr vserver</a></li><li><a href="../../../-cr-vs/-cr-vs">unset cr vserver</a></li></ul>



##rename cr policy

Rename a cache redirection policy.


##Synopsys

rename cr policy &lt;policyName>@ &lt;newName>@


##Arguments

<b>policyName</b>
The name of the content switching policy.

<b>newName</b>
The new name of the content switching policy.



##Example

rename cr policy oldname newname

