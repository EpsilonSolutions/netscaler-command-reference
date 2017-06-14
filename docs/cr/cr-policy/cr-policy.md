#cr policy

The following operations can be performed on "cr policy":


[add](#add-cr-policy) | [rm](#rm-cr-policy) | [set](#set-cr-policy) | [show](#show-cr-policy)

##add cr policy

Creates a cache redirection policy. To associate the new policy with a cache redirection virtual server, use the bind cr vserver command.


##Synopsys

add cr policy &lt;policyName> -rule &lt;expression>


##Arguments

<b>policyName</b>
Name for the cache redirection policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI: 
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my policy? or ?my policy?).

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic syntax.
Note:Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: "&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
*  If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>builtin</b>



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

set cr policy &lt;policyName> -rule &lt;expression>


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



##show cr policy

Displays all existing cache redirection policies, or just the specified policy.


##Synopsys

show cr policy [&lt;policyName>]


##Arguments

<b>policyName</b>
Name of the cache redirection policy to display. If this parameter is omitted, details of all the policies are displayed.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

<b>vstype</b>
Virtual server type.

<b>csPolicyType</b>
Indicates whether policy is PI or not.(used only during display)

<b>builtin</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Related Commands

<ul><li><a href="../../../r-vs/r-vs">add cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">bind cr vserver</a></li><li><a href="../../../r-vs/r-vs">set cr vserver</a></li><li><a href="../../../cr-vs/cr-vs">show cr vserver</a></li><li><a href="../../../d-cr-vs/d-cr-vs">unbind cr vserver</a></li><li><a href="../../../-cr-vs/-cr-vs">unset cr vserver</a></li></ul>



