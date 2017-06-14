#dns policy

The following operations can be performed on "dns policy":


[add](#add-dns-policy) | [rm](#rm-dns-policy) | [set](#set-dns-policy) | [show](#show-dns-policy)

##add dns policy

Creates a DNS policy.


##Synopsys

add dns policy &lt;name> &lt;rule> &lt;actionName>


##Arguments

<b>name</b>
Name for the DNS policy.

<b>rule</b>
Expression against which DNS traffic is evaluated. Written in the default syntax.
Note:
* On the command line interface, if the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
* If the expression itself includes double quotation marks, you must escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
Example: CLIENT.UDP.DNS.DOMAIN.EQ("domainname")

<b>viewName</b>
The view name that must be used for the given policy.

<b>preferredLocation</b>
The location used for the given policy. This is deprecated attribute. Please use -prefLocList

<b>preferredLocList</b>
The location list in priority order used for the given policy.

<b>drop</b>
The dns packet must be dropped.
Possible values: YES, NO

<b>cacheBypass</b>
By pass dns cache for this.
Possible values: YES, NO

<b>actionName</b>
Name of the DNS action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* dns_default_act_Drop. Drop the DNS request.
* dns_default_act_Cachebypass. Bypass the DNS cache and forward the request to the name server.
You can create custom actions by using the add dns action command in the CLI or the DNS &gt; Actions &gt; Create DNS Action dialog box in the NetScaler configuration utility.



##Example

add dns policy pol1 "dns.req.question.type.ne(aaaa)" -actionName act1add dns policy pol2 "CLIENT.IP.SRC.IN_SUBNET(1.1.1.1/24)" -actionName action1add dns policy pol1 dns.res.question.domain.contains("citrix") -actionName act2

##rm dns policy

Removes a DNS policy.


##Synopsys

rm dns policy &lt;name>


##Arguments

<b>name</b>
Name of the DNS policy to remove.



##set dns policy

Modifies the parameters of the specified DNS policy.


##Synopsys

set dns policy &lt;name> [&lt;rule>] [-actionName &lt;string>]


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
Example: CLIENT.UDP.DNS.DOMAIN.EQ("domainname")

<b>viewName</b>
The view name that must be used for the given policy

<b>preferredLocation</b>
The location used for the given policy. This is deprecated attribute. Please use -prefLocList

<b>preferredLocList</b>
The location list in priority order used for the given policy.

<b>drop</b>
The dns packet must be dropped.
Possible values: YES, NO

<b>cacheBypass</b>
By pass dns cache for this.
Possible values: YES, NO

<b>actionName</b>
Name of the DNS action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* dns_default_act_Drop. Drop the DNS request.
* dns_default_act_Cachebypass. Bypass the DNS cache and forward the request to the name server.
You can create custom actions by using the add dns action command in the CLI or the DNS &gt; Actions &gt; Create DNS Action dialog box in the NetScaler configuration utility.



##Example

set dns policy pol1 -rule "dns.req.question.type.ne(aaaa)"set dns policy pol2 -rule "CLIENT.IP.SRC.IN_SUBNET(1.1.1.1/24)"set dns policy pol1 -rule dns.res.header.rcode.eq(nxdomain)

##show dns policy

Displays the parameters of the specified DNS policy or, if no policy name is specified, all configured DNS policies.


##Synopsys

show dns policy [&lt;name>]


##Arguments

<b>name</b>
Name of the DNS policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
The expression to be used by the dns policy.

<b>viewName</b>
The view name that must be used for the given policyNOTE: This attribute is deprecated.This is deprecated attribute. Please use -actionName

<b>preferredLocation</b>
The location used for the given policy. This is deprecated attribute. Please use -prefLocListNOTE: This attribute is deprecated.This is deprecated attribute. Please use -actionName

<b>preferredLocList</b>
The location list in priority order used for the given policy.NOTE: This attribute is deprecated.This is deprecated attribute. Please use -actionName

<b>hits</b>
The number of times the policy has been hit.

<b>undefHits</b>
Number of Undef hits.

<b>drop</b>
The dns packet must be dropped.NOTE: This attribute is deprecated.This is deprecated attribute. Please use -actionName

<b>actionName</b>
Name of the DNS action to perform when the rule evaluates to TRUE. The built in actions function as follows:
* dns_default_act_Drop. Drop the DNS request.
* dns_default_act_Cachebypass. Bypass the DNS cache and forward the request to the name server.
You can create custom actions by using the add dns action command in the CLI or the DNS > Actions > Create DNS Action dialog box in the NetScaler configuration utility.

<b>cacheBypass</b>
By pass dns cache for this.NOTE: This attribute is deprecated.This is deprecated attribute. Please use -actionName

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>builtin</b>
Flag to determine whether DNS policy is default or not

<b>stateflag</b>

<b>devno</b>

<b>count</b>



