#dns policy64

The following operations can be performed on "dns policy64":


[add](#add-dns-policy64) | [rm](#rm-dns-policy64) | [set](#set-dns-policy64) | [show](#show-dns-policy64)

##add dns policy64

Creates a DNS64 Policy.


##Synopsys

add dns policy64 &lt;name> -rule &lt;expression> -action &lt;string>


##Arguments

<b>name</b>
Name for the DNS64 policy.

<b>rule</b>
Expression against which DNS traffic is evaluated. Written in the default syntax.
Note:
* On the command line interface, if the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
Example: CLIENT.IP.SRC.IN_SUBENT(23.34.0.0/16)

<b>action</b>
Name of the DNS64 action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* A default dns64 action with prefix &lt;default prefix&gt; and mapped and exclude are any 
You can create custom actions by using the add dns action command in the CLI or the DNS64 &gt; Actions &gt; Create DNS64 Action dialog box in the NetScaler configuration utility.



##Example

add dns64 policy pol1 "client.ip.src.in_subnet(23.43.0.0/16)" -action act1

##rm dns policy64

Removes a DNS64 Policy.


##Synopsys

rm dns policy64 &lt;name>


##Arguments

<b>name</b>
Name of the DNS64 policy to be removed.



##set dns policy64

Modifies the parameters of the specified DNS64 policy.


##Synopsys

set dns policy64 &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the DNS policy.

<b>rule</b>
Expression against which DNS traffic is evaluated. Written in the default syntax.
Note:
* On the command line interface, if the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
Example: CLIENT.IP.SRC.IN_SUBENT(23.34.0.0/16)

<b>action</b>
Name of the DNS64 action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* A default dns64 action with prefix &lt;default prefix&gt; and mapped and exclude are any 
You can create custom actions by using the add dns action command in the CLI or the DNS64 &gt; Actions &gt; Create DNS64 Action dialog box in the NetScaler configuration utility.



##Example

set dns policy pol2 -rule "CLIENT.IP.SRC.IN_SUBNET(1.1.1.1/24)"

##show dns policy64

Displays the parameters of the specified DNS64 policy or, if no policy name is specified, all configured DNS64 policies.


##Synopsys

show dns policy64 [&lt;name>]


##Arguments

<b>name</b>
Name of the DNS64 policy.



##Outputs

<b>rule</b>
The expression to be used by the dns policy.

<b>hits</b>
The number of times the policy has been hit.

<b>action</b>
Name of the DNS64 action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* A default dns64 action with prefix &lt;default prefix> and mapped and exclude are any 
You can create custom actions by using the add dns action command in the CLI or the DNS64 > Actions > Create DNS64 Action dialog box in the NetScaler configuration utility.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>boundTo</b>
Location where policy is bound

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>undefHits</b>
Number of Undef hits.

<b>description</b>
Description of the policy

<b>stateflag</b>

<b>devno</b>

<b>count</b>



