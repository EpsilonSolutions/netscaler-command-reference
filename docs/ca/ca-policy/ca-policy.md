#ca policy

The following operations can be performed on "ca policy":


[add](#add-ca-policy) | [show](#show-ca-policy) | [rm](#rm-ca-policy) | [set](#set-ca-policy) | [unset](#unset-ca-policy) | [rename](#rename-ca-policy)

##add ca policy

Creates a content adaptation policy. This policy must later be invoked globally or at a content switching or load balancing virtual server.


##Synopsys

add ca policy &lt;name> -rule &lt;expression> -action &lt;string> [-undefAction &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the content adaptation policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Can be changed after the policy is created.

<b>rule</b>
Expression that determines which requests or responses match the content adaptation policy. When specifying the rule in the CLI, the description must be enclosed within double quotes.

<b>action</b>
Name of content adaptation action to be executed when the rule is evaluated to true.

<b>undefAction</b>

<b>comment</b>
Information about the content adaptation policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.



##show ca policy

Displays information about a content adaptation policy. If no name is specified, this command displays information of all available content adaptation policies.


##Synopsys

show ca policy [&lt;name>]


##Arguments

<b>name</b>
Name of the content adaptation policy to be displayed.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>undefAction</b>
Undef Action associated with the policy.

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>boundTo</b>
Location where policy is bound

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>vserverType</b>

<b>action</b>
Content adaptation action associated with the policy.

<b>rule</b>
Rule of the policy.

<b>hits</b>
Number of hits.

<b>undefHits</b>
Number of Undef hits.

<b>isDefault</b>
A value of true is returned if it is a default ContentAdaptationpolicy.

<b>priority</b>
Specifies the priority of the policy.

<b>bindPolicyType</b>

<b>comment</b>
Information about the content adaptation policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.

<b>devno</b>

<b>count</b>



##Example

show ca policy

##rm ca policy

Removes a content adaptation policy.


##Synopsys

rm ca policy &lt;name>


##Arguments

<b>name</b>
Name of the content adaptation policy to be removed.



##Example

rm ca policy pol9

##set ca policy

Modifies the parameters of a content adaptation policy.


##Synopsys

set ca policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-comment &lt;string>] [-logAction &lt;string>] [-undefAction &lt;string>]


##Arguments

<b>name</b>
Name of the content accelerator policy to be modified.

<b>rule</b>
Expression that determines which requests or responses match the content adaptation policy. When specifying the rule in the CLI, the description must be enclosed within double quotes.

<b>action</b>
Name of content adaptation action to be executed when the rule is evaluated to true.

<b>comment</b>
Information about the content adaptation policy.

<b>logAction</b>
Name of messagelog action to use when a request matches this policy.

<b>undefAction</b>



##Example

set ca policy pol9 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset ca policy

Removes the settings of an existing content accelerator policy. Attributes for which a default value is available revert to their default values. See the set content accelerator policy command for a description of the parameters..Refer to the set ca policy command for meanings of the arguments.


##Synopsys

unset ca policy &lt;name> [-comment] [-logAction] [-undefAction]


##Example

unset ca policy pol9 -undefAction

##rename ca policy

Renames content accelerator policy.


##Synopsys

rename ca policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the content accelerator policy.

<b>newName</b>
New name for the content accelerator policy



##Example

rename ca policy oldname newname

