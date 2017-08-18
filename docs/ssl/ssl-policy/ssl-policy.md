#ssl policy

The following operations can be performed on "ssl policy":


[add](#add-ssl-policy) | [rm](#rm-ssl-policy) | [set](#set-ssl-policy) | [unset](#unset-ssl-policy) | [show](#show-ssl-policy)

##add ssl policy

Adds an SSL policy. An SSL policy evaluates incoming traffic and applies a predefined action to requests that match a rule (expression). You have to configure the actions before creating the policies, so that you can specify an action when you create a policy.


##Synopsys

add ssl policy &lt;name> -rule &lt;expression> [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the new SSL policy. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.  Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in or user-defined action to perform on the request. Available built-in actions are NOOP, RESET, DROP, CLIENTAUTH and NOCLIENTAUTH.

<b>undefAction</b>
Name of the action to be performed when the result of rule evaluation is undefined. Possible values for control policies: CLIENTAUTH, NOCLIENTAUTH, NOOP, RESET, DROP. Possible values for data policies: NOOP, RESET, DROP.

<b>comment</b>
Any comments associated with this policy.



##Example

	add ssl action certInsert_act -clientCert ENABLED -certHeader CERT	add ssl policy certInsert_pol -rule 'HTTP.REQ.URL.STARTSWITH("/secure/")' -reqAction certInsert_actThe above example adds an SSL policy to do Client certificate insertion into the HTTP requests for any web-objects under /secure/.

##rm ssl policy

Removes an SSL policy.


##Synopsys

rm ssl policy &lt;name>


##Arguments

<b>name</b>
Name of the SSL policy to be removed.



##Example

rm ssl policy certInsert_pol

##set ssl policy

Modifies the parameters of an SSL default syntax policy.


##Synopsys

set ssl policy &lt;name> [-rule &lt;expression>] [-action &lt;string>] [-undefAction &lt;string>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the SSL policy to modify.

<b>rule</b>
Expression, against which traffic is evaluated. Written in the classic or default syntax.
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
(Classic expressions are not supported in the cluster build.)
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in or user-defined action to perform on the request. Available built-in actions are NOOP, RESET, DROP, CLIENTAUTH and NOCLIENTAUTH.

<b>undefAction</b>
Name of the action to be performed when the result of rule evaluation is undefined. Possible values for control policies: CLIENTAUTH, NOCLIENTAUTH, NOOP, RESET, DROP. Possible values for data policies: NOOP, RESET, DROP.

<b>comment</b>
Any comments associated with this policy.



##Example

set ssl policy pol1 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset ssl policy

Removes the attributes of an SSL default syntax policy. Attributes for which a default value is available revert to their default values. Refer to the set ssl policy command for a description of the parameters..Refer to the set ssl policy command for meanings of the arguments.


##Synopsys

unset ssl policy &lt;name> [-undefAction] [-comment]


##Example

unset ssl policy pol1 -undefAction

##show ssl policy

Displays information about all the SSL policies configured on the appliance, or displays detailed information about the specified SSL policy.


##Synopsys

show ssl policy [&lt;name>]


##Arguments

<b>name</b>
Name of the SSL policy for which to display detailed information.



##Outputs

<b>stateflag</b>

<b>rule</b>
The expression that sets the condition for application of the SSL policy.

<b>action</b>
The name of the action to be performed on the request.

<b>undefAction</b>
Undef Action associated with the policy.

<b>hits</b>
Number of hits for this policy.

<b>piHits</b>
Number of hits.

<b>undefHits</b>
Number of Undef hits.

<b>activePolicy</b>

<b>boundTo</b>
The entity name to which policy is bound

<b>priority</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>comment</b>
Any comments associated with this policy.

<b>bindPolicyType</b>

<b>vserverType</b>

<b>policyType</b>

<b>peFlags</b>

<b>devno</b>

<b>count</b>



##Example

show ssl policy1 SSL policy:1)      Name: certInsert_pol    Rule: URL == /*        Action: certInsert_act      Hits: 0

