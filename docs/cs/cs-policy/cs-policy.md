#cs policy

The following operations can be performed on "cs policy":


[add](#add-cs-policy) | [rm](#rm-cs-policy) | [set](#set-cs-policy) | [unset](#unset-cs-policy) | [show](#show-cs-policy) | [rename](#rename-cs-policy)

##add cs policy

Creates a new content switching policy. You use this policy to manage content switching on a virtual server.


##Synopsys

add cs policy &lt;policyName> [-url &lt;string> | -rule &lt;expression> | -action &lt;string>] [-domain &lt;string>] [-logAction &lt;string>]


##Arguments

<b>policyName</b>
Name for the content switching policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after a policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, my policy or my policy).

<b>url</b>
URL string that is matched with the URL of a request. Can contain a wildcard character. Specify the string value in the following format: [[prefix] [*]] [.suffix].

<b>rule</b>
Expression, or name of a named expression, against which traffic is evaluated. Written in the classic or default syntax. 
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
*  If the expression itself includes double quotation marks, escape the quotations by using the  character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>domain</b>
The domain name. The string value can range to 63 characters.

<b>action</b>
Content switching action that names the target load balancing virtual server to which the traffic is switched.

<b>logAction</b>
The log action associated with the content switching policy



##Example

To match the requests that have URL "/", you would enter the following command:add cs policy &lt;policyName&gt; -url /To match with all URLs that start with "/sports/", you would enter the following command:add cs policy &lt;policyName&gt; -url /sports/*To match requests with URLs that start with "/sports", you would enter the following command:add cs policy &lt;policyName&gt; -url /sports*To match requests with the URL "/sports/tennis/index.html", you would enter the following command:add cs policy &lt;policyName&gt; -url /sports/tennis/index.htmlTo match requests that have URLs with the extension "jsp", you would enter the following command:add cs policy &lt;policyName&gt; -url /*.jspTo match requests with URLs that start with "/sports/" and the file extension "jsp", you would enter the following command:add cs policy &lt;policyName&gt; -url /sports/*.jspTo match requests with URLs that contain "sports", you would enter the following commands:add pol expression sports_url "URL contains sports"add cs policy &lt;policyName&gt; -rule sports_urlTo match requests with URL queries that contain "gold" or cookie headers that contain "gold", you would enter the following commands:add pol expression gold_query "URLQUERY contains gold"add pol expression gold_cookie "Header COOKIE contains gold"add cs policy &lt;policyName&gt; -rule "(gold_query ||gold_cookie)"To match requests with the domain name www.domainxyz.com, you enter the following command:add cs policy &lt;policyName&gt; -domain "www.domainxyz.com"To match requests with the domain name www.domainxyz.com and URLs with the extension "jsp", you would enter the following command:add cs policy &lt;policyName&gt; -url /*.jsp -domain "www.domainxyz.com"To match requests with the domain name www.domainxyz.com and URLs that contain "sports", you would enter the following commands:add pol expression sports_url "URL contains sports"add cs policy &lt;policyName&gt; -rule sports_url -domain "www.domainxyz.com"To match a policy with a rule and provide action:add cs policy &lt;policyname&gt; -rule "http.req.method.eq(GET)" -action act1

##rm cs policy

Removes a content switching policy. You can delete a user-defined content switching policy that is not bound to a content switching virtual server. If the policy is bound to a virtual server, you must first unbind the policy, and then remove it.


##Synopsys

rm cs policy &lt;policyName>


##Arguments

<b>policyName</b>
Name of the content switching policy to be removed.



##set cs policy

Changes an existing content switching policy.


##Synopsys

set cs policy &lt;policyName> [-url &lt;string> | -rule &lt;expression>] [-domain &lt;string>] [-action &lt;string>] [-logAction &lt;string>]


##Arguments

<b>policyName</b>
Name of the content switching policy.

<b>url</b>
The URL, with wildcards.

<b>rule</b>
The condition for applying this policy.

<b>domain</b>
The domain name.

<b>action</b>
The content switching action name.

<b>logAction</b>
The log action associated with the content switching policy



##unset cs policy

Unset logaction for existing content swtching policy..Refer to the set cs policy command for meanings of the arguments.


##Synopsys

unset cs policy &lt;policyName> [-logAction] [-url] [-rule] [-domain] [-action]


##Example

unset cs policy pol9 -logAction

##show cs policy

Displays all existing content switching policies, or just the specified policy.


##Synopsys

show cs policy [&lt;policyName>]


##Arguments

<b>policyName</b>
Name of the content switching policy to display. If this parameter is omitted, details of all the policies are displayed.



##Outputs

<b>url</b>
The URL with wildcards.

<b>rule</b>
The condition for applying this policy.

<b>domain</b>
The domain name.

<b>action</b>
The CS action name.

<b>vstype</b>
Virtual server type.

<b>hits</b>
Total number of hits.

<b>piHits</b>
Total number of hits.

<b>bindHits</b>
Total number of hits.

<b>piPolicyhits</b>
bind hits for PI CS Policy.

<b>labelName</b>
Name of the label invoked.

<b>labelType</b>
The invocation type.

<b>target</b>
Target flag

<b>priority</b>
priority of bound policy

<b>flag</b>

<b>stateflag</b>

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>csPolicyType</b>
Indicates whether policy is PI or not.(used only during display)

<b>logAction</b>
The log action associated with the content switching policy

<b>devno</b>

<b>count</b>



##Related Commands

<ul><li><a href="../../../cs-vs/cs-vs">show cs vserver</a></li></ul>



##rename cs policy

Rename a content switching policy.


##Synopsys

rename cs policy &lt;policyName>@ &lt;newName>@


##Arguments

<b>policyName</b>
The name of the content switching policy.

<b>newName</b>
The new name of the content switching policy.



##Example

rename cs policy oldname newname

