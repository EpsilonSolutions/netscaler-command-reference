#vpn clientlessAccessPolicy

The following operations can be performed on "vpn clientlessAccessPolicy":


[add](#add-vpn-clientlessaccesspolicy) | [rm](#rm-vpn-clientlessaccesspolicy) | [set](#set-vpn-clientlessaccesspolicy) | [show](#show-vpn-clientlessaccesspolicy)

##add vpn clientlessAccessPolicy

Adds a clientless access policy, which enables users to log on using a web browser and connect to the bookmarked web address without requiring the user to install a software plug-in.


##Synopsys

add vpn clientlessAccessPolicy &lt;name> &lt;rule> &lt;profileName>


##Arguments

<b>name</b>
Name of the new clientless access policy.

<b>rule</b>
Expression, or name of a named expression, specifying the traffic that matches the policy. Can be written in either default or classic syntax. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>profileName</b>
Name of the profile to invoke for the clientless access.



##rm vpn clientlessAccessPolicy

Removes a clientless access policy.


##Synopsys

rm vpn clientlessAccessPolicy &lt;name>


##Arguments

<b>name</b>
Name of the clientless access policy to remove.



##set vpn clientlessAccessPolicy

Adds a new rule to be used by an existing clientless access policy that includes a simple expression that specifies the conditions for which the policy is enforced.


##Synopsys

set vpn clientlessAccessPolicy &lt;name> [-rule &lt;expression>] [-profileName &lt;string>]


##Arguments

<b>name</b>
Name of the existing clientless access policy to modify.

<b>rule</b>
Expression, or name of a named expression, specifying the traffic that matches the policy. Can be written in either default or classic syntax. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>profileName</b>
Name of the profile to invoke for the clientless access.



##show vpn clientlessAccessPolicy

Displays a clientless access policy.


##Synopsys

show vpn clientlessAccessPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the clientless access policy to display.



##Outputs

<b>rule</b>
The rule used by the clientless access policy. Rules are combinations of expressions. Expressions are simple conditions, such as a test for equality, applied to operands, such as a URL string or an IP address. Expression syntax is described in the Installation and Configuration Guide

<b>profileName</b>
The profile to invoked for the clientless access.

<b>undefAction</b>
The UNDEF action.

<b>hits</b>
The number of times the policy evaluated to true.

<b>undefHits</b>
The number of times the policy evaluation resulted in undefined processing.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound.

<b>priority</b>
Specifies the priority of the policy.

<b>description</b>
Description of the clientless access policy.

<b>isDefault</b>
A value of true is returned if it is a default vpnclientlessrwpolicy.

<b>stateflag</b>

<b>builtin</b>
Flag to determine if vpn clientless rewrite policy is built-in or not

<b>devno</b>

<b>count</b>



