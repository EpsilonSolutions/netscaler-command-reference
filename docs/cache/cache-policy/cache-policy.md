#cache policy

The following operations can be performed on "cache policy":


[add](#add-cache-policy) | [rm](#rm-cache-policy) | [set](#set-cache-policy) | [unset](#unset-cache-policy) | [show](#show-cache-policy) | [stat](#stat-cache-policy) | [rename](#rename-cache-policy)

##add cache policy

Creates an integrated caching policy. The newly created policy is in inactive state. To activate the policy, use the bind cache global command.


##Synopsys

add cache policy &lt;policyName> -rule &lt;expression> -action &lt;action> [-storeInGroup &lt;string>] [-invalGroups &lt;string> ...] [-invalObjects &lt;string> ...] [-undefAction ( NOCACHE | RESET )]


##Arguments

<b>policyName</b>
Name for the policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the policy is created.

<b>rule</b>
Expression against which the traffic is evaluated.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to apply to content that matches the policy. 
* CACHE or MAY_CACHE action - positive cachability policy
* NOCACHE or MAY_NOCACHE action - negative cachability policy
* INVAL action - Dynamic Invalidation Policy
Possible values: CACHE, NOCACHE, MAY_CACHE, MAY_NOCACHE, INVAL

<b>storeInGroup</b>
Name of the content group in which to store the object when the final result of policy evaluation is CACHE. The content group must exist before being mentioned here. Use the "show cache contentgroup" command to view the list of existing content groups.

<b>invalGroups</b>
Content group(s) to be invalidated when the INVAL action is applied. Maximum number of content groups that can be specified is 16.

<b>invalObjects</b>
Content groups(s) in which the objects will be invalidated if the action is INVAL.

<b>undefAction</b>
Action to be performed when the result of rule evaluation is undefined.
Possible values: NOCACHE, RESET



##rm cache policy

Removes the specified caching policy. Make sure that the policy is not bound globally or to a virtual server. A bound policy cannot be removed.


##Synopsys

rm cache policy &lt;policyName>


##Arguments

<b>policyName</b>
Name of the cache policy to be removed.



##set cache policy

Modifies the specified attributes of an existing cache policy. The rule, flow type, can be changed only if action and undefAction (if present) are of NEUTRAL flow type.


##Synopsys

set cache policy &lt;policyName> [-rule &lt;expression>] [-action &lt;action>] [-storeInGroup &lt;string>] [-invalGroups &lt;string> ...] [-invalObjects &lt;string> ...] [-undefAction ( NOCACHE | RESET )]


##Arguments

<b>policyName</b>
Name for the policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the policy is created.

<b>rule</b>
Expression against which the traffic is evaluated.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Action to apply to content that matches the policy. 
* CACHE or MAY_CACHE action - positive cachability policy
* NOCACHE or MAY_NOCACHE action - negative cachability policy
* INVAL action - Dynamic Invalidation Policy
Possible values: CACHE, NOCACHE, MAY_CACHE, MAY_NOCACHE, INVAL

<b>storeInGroup</b>
Name of the content group in which to store the object when the final result of policy evaluation is CACHE. The content group must exist before being mentioned here. Use the "show cache contentgroup" command to view the list of existing content groups.

<b>invalGroups</b>
Content group(s) to be invalidated when the INVAL action is applied. Maximum number of content groups that can be specified is 16.

<b>invalObjects</b>
Content groups(s) in which the objects will be invalidated if the action is INVAL.

<b>undefAction</b>
Action to be performed when the result of rule evaluation is undefined.
Possible values: NOCACHE, RESET



##Example

set cache policy pol9 -rule "http.req.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset cache policy

Use this command to remove cache policy settings.Refer to the set cache policy command for meanings of the arguments.


##Synopsys

unset cache policy &lt;policyName> [-storeInGroup] [-invalGroups] [-invalObjects] [-undefAction]


##show cache policy

Displays all configured cache policies. To display details about a particular cache policy, specify the name of the policy. When all caching policies are displayed, the order of the displayed policies within each group is the same as the evaluation order of the policies. There are three groups: request policies, response policies, and dynamic invalidation policies.


##Synopsys

show cache policy [&lt;policyName>]show cache policy stats - alias for 'stat cache policy'


##Arguments

<b>policyName</b>
Name of the cache policy about which to display details.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
The request/response rule that will trigger the specified action.

<b>action</b>
The integrated cache action to be applied when the system sees content that matches the rules.

<b>storeInGroup</b>
The content group that will store the object when the action directive is CACHE.

<b>invalGroups</b>
The content group(s) to be invalidated when the action directive is INVAL.

<b>invalObjects</b>
The content group(s) whose objects will be invalidated when the action directive is INVAL.

<b>priority</b>
Priority.

<b>hits</b>
Hits.

<b>undefAction</b>
A CACHE action, to be used by the policy when the rule evaluation turns out to be undefined.

<b>undefHits</b>
Number of Undef hits.

<b>flags</b>
Flag.

<b>precedeDefRules</b>
Override default request/response cacheability rules.NOTE: This attribute is deprecated.Since pre-builtin, built-in and post-built-in policies are in same policy bank, this is no longer needed

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>builtin</b>

<b>devno</b>

<b>count</b>



##stat cache policy

Displays a summary of cache policy statistics.


##Synopsys

stat cache policy [&lt;policyName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>policyName</b>
Name of the cache policy for which to display statistics. If you do not set this parameter, statistics are shown for all cache policies.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b>count</b>

<b>devno</b>

<b>stateflag</b>



##Outputs

<b>Policy hits (Hits)</b>
Number of hits on the policy

<b>Policy undef hits (Undefhits)</b>
Number of undef hits on the policy



##Example

stat cache policy

##Related Commands

<ul><li><a href="../../..//">stat cache</a></li><li><a href="../../../html#stat-cache-policy/html#stat-cache-policy">stat cache policylabel</a></li><li><a href="../../../.html#stat-cache-content/.html#stat-cache-content">stat cache contentGroup</a></li></ul>



##rename cache policy

Renames an existing cache policy.


##Synopsys

rename cache policy &lt;policyName>@ &lt;newName>@


##Arguments

<b>policyName</b>
Existing name of the cache policy.

<b>newName</b>
New name for the cache policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rename cache policy oldname newname

