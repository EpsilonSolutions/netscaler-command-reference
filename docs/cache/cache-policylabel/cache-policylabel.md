#cache policylabel

The following operations can be performed on "cache policylabel":


[add](#add-cache-policylabel) | [rm](#rm-cache-policylabel) | [bind](#bind-cache-policylabel) | [unbind](#unbind-cache-policylabel) | [show](#show-cache-policylabel) | [stat](#stat-cache-policylabel) | [rename](#rename-cache-policylabel)

##add cache policylabel

Creates a user-defined cache policy label. A policy label is a bind point of a group of policies.


##Synopsys

add cache policylabel &lt;labelName> -evaluates &lt;evaluates>


##Arguments

<b>labelName</b>
Name for the label. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the label is created.

<b>evaluates</b>
When to evaluate policies bound to this label: request-time or response-time.
Possible values: REQ, RES, MSSQL_REQ, MSSQL_RES, MYSQL_REQ, MYSQL_RES



##Example

add cache policylabel cache_http_url -evaluates REQ

##rm cache policylabel

Removes the specified integrated caching policy label.


##Synopsys

rm cache policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the label to be removed.



##Example

rm cache policylabel cache_http_url

##bind cache policylabel

Binds a cache policy to a policy label.


##Synopsys

bind cache policylabel &lt;labelName> -policyName &lt;string> -priority &lt;positive_integer> [-gotoPriorityExpression &lt;expression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the cache policy label to which to bind the policy.

<b>policyName</b>
Name of the cache policy to bind to the policy label.



##Example

	i)	bind cache policylabel cache_http_url pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind cache policylabel cache_http_url pol_2 2

##unbind cache policylabel

Unbinds a policy from a cache-policy label.


##Synopsys

unbind cache policylabel &lt;labelName> -policyName &lt;string> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the cache policy label from which to unbind the policy.

<b>policyName</b>
Name of the policy to unbind from the label.

<b>priority</b>
Required only if you want to unbind a NOPOLICY that might have been bound to this policy label.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind cache policylabel cache_http_url pol_1

##show cache policylabel

Displays information about all cache-policy labels or about the specified cache-policy label.


##Synopsys

show cache policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the cache-policy label about which to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>flags</b>

<b>evaluates</b>
When to evaluate policies bound to this label: request-time or response-time.

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the cache policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke policies bound to a virtual server or a user-defined policy label. After the invoked policies are evaluated, the flow returns to the policy with the next-lower priority.

<b>labelType</b>
Type of policy label to invoke: an unnamed label associated with a virtual server, or user-defined policy label.

<b>labelName</b>
Name of the policy label to invoke if the current policy rule evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound cache policy.

<b>builtin</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show cache policylabel cache_http_url	ii)	show cache policylabel

##stat cache policylabel

Displays statistics of cache policy label(s).


##Synopsys

stat cache policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the cache-policy label for which to display statistics. If you do not set this parameter statistics are shown for all cache-policy labels.

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

<ul><li><a href="../../..//">stat cache</a></li><li><a href="../../../stat-cache-p/stat-cache-p">stat cache policy</a></li><li><a href="../../../.html#stat-cache-content/.html#stat-cache-content">stat cache contentGroup</a></li></ul>



##rename cache policylabel

Renames a cache-policy label.


##Synopsys

rename cache policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Existing name of the cache-policy label.

<b>newName</b>
New name for the cache-policy label. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.



##Example

rename cache policylabel oldname newname

