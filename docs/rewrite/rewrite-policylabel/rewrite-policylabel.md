#rewrite policylabel

The following operations can be performed on "rewrite policylabel":


[add](#add-rewrite-policylabel) | [rm](#rm-rewrite-policylabel) | [bind](#bind-rewrite-policylabel) | [unbind](#unbind-rewrite-policylabel) | [show](#show-rewrite-policylabel) | [stat](#stat-rewrite-policylabel) | [rename](#rename-rewrite-policylabel)

##add rewrite policylabel

Creates a user-defined rewrite policy label.


##Synopsys

add rewrite policylabel &lt;labelName> &lt;transform> [-comment &lt;string>]


##Arguments

<b>labelName</b>
Name for the rewrite policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rewrite policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite policy label" or ?my rewrite policy label?).

<b>transform</b>
Types of transformations allowed by the policies bound to the label. For Rewrite, the following types are supported:
* http_req - HTTP requests
* http_res - HTTP responses
* othertcp_req - Non-HTTP TCP requests
* othertcp_res - Non-HTTP TCP responses
* url - URLs
* text - Text strings
* clientless_vpn_req - NetScaler clientless VPN requests
* clientless_vpn_res - NetScaler clientless VPN responses
* sipudp_req - SIP requests
* sipudp_res - SIP responses
* diameter_req - DIAMETER requests
* diameter_res - DIAMETER responses
* radius_req - RADIUS requests
* radius_res - RADIUS responses
* dns_req - DNS requests
* dns_res - DNS responses
Possible values: http_req, http_res, othertcp_req, othertcp_res, url, text, clientless_vpn_req, clientless_vpn_res, sipudp_req, sipudp_res, siptcp_req, siptcp_res, diameter_req, diameter_res, radius_req, radius_res, dns_req, dns_res

<b>comment</b>
Any comments to preserve information about this rewrite policy label.



##Example

add rewrite policylabel trans_http_url http_req

##rm rewrite policylabel

Removes the specified rewrite policy label.


##Synopsys

rm rewrite policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the rewrite policy label to remove.



##Example

rm rewrite policylabel trans_http_url

##bind rewrite policylabel

Binds the specified rewrite policy to the specified policy label.


##Synopsys

bind rewrite policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
* If labelType is policylabel, name of the policy label to invoke. 
* If labelType is reqvserver or resvserver, name of the virtual server to which to forward the request or response.

<b>policyName</b>
Name of the rewrite policy to bind to the policy label.

<b>priority</b>
Positive integer specifying the priority of the policy. A lower number specifies a higher priority. Must be unique within the label. Policies are evaluated in the order of their priorities, and the first policy that matches the request or response is applied.
Minimum value: 1
Maximum value: 2147483647

<b>gotoPriorityExpression</b>
Expression or other value specifying the next policy to evaluate if the current policy evaluates to TRUE.  Specify one of the following values:
*  NEXT - Evaluate the policy with the next higher priority number.
*  END - End policy evaluation.
*  USE_INVOCATION_RESULT - Applicable if this policy invokes another policy label. If the final goto in the invoked policy label has a value of END, the evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.
* A default syntax or classic expression that evaluates to a number.
If you specify an expression, the number to which it evaluates determines the next policy to evaluate, as follows:
*  If the expression evaluates to a higher numbered priority, the policy with that priority is evaluated next.
*  If the expression evaluates to the priority of the current policy, the policy with the next higher numbered priority is evaluated next.
*  If the expression evaluates to a number that is larger than the largest numbered priority, policy evaluation ends.
An UNDEF event is triggered if:
*  The expression is invalid.
*  The expression evaluates to a priority number that is smaller than the current policy?s priority number.
*  The expression evaluates to a priority number that is between the current policy?s priority number (say, 30) and the highest priority number (say, 100), but does not match any configured priority number (for example, the expression evaluates to the number 85). This example assumes that the priority number increments by 10 for every successive policy, and therefore a priority number of 85 does not exist in the policy label.

<b>invoke</b>
Suspend evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* resvserver - Forward the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.
Possible values: reqvserver, resvserver, policylabel



##Example

	i)	bind rewrite policylabel trans_http_url pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind rewrite policylabel trans_http_url pol_2 2

##unbind rewrite policylabel

Unbinds the specified rewrite policy from the specified policy label. See the bind rewrite policylabel command for a description of the parameters.


##Synopsys

unbind rewrite policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name for the rewrite policy label. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the rewrite policy label is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my rewrite policy label" or ?my rewrite policy label?).

<b>policyName</b>
Name of the rewrite policy to bind to the policy label.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind rewrite policylabel trans_http_url pol_1

##show rewrite policylabel

Displays the current settings for the specified rewrite policy label.If no policy label is specified, displays a list of all rewrite policy labels currently configured on the NetScaler appliance.


##Synopsys

show rewrite policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the rewrite policy label.



##Outputs

<b>stateflag</b>

<b>transform</b>
Types of transformations allowed by the policies bound to the label. For Rewrite, the following types are supported:
* http_req - HTTP requests
* http_res - HTTP responses
* othertcp_req - Non-HTTP TCP requests
* othertcp_res - Non-HTTP TCP responses
* url - URLs
* text - Text strings
* clientless_vpn_req - NetScaler clientless VPN requests
* clientless_vpn_res - NetScaler clientless VPN responses
* sipudp_req - SIP requests
* sipudp_res - SIP responses
* diameter_req - DIAMETER requests
* diameter_res - DIAMETER responses
* radius_req - RADIUS requests
* radius_res - RADIUS responses
* dns_req - DNS requests
* dns_res - DNS responses

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the rewrite policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Suspend evaluation of policies bound to the current policy label, and then forward the request to the specified virtual server or evaluate the specified policy label.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Forward the request to the specified request virtual server.
* resvserver - Forward the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
* If labelType is policylabel, name of the policy label to invoke. 
* If labelType is reqvserver or resvserver, name of the virtual server to which to forward the request or response.

<b>flowType</b>
Flowtype of the bound rewrite policy.

<b>description</b>
Description of the policylabel

<b>isDefault</b>
A value of true is returned if it is a default rewritepolicylabel.

<b>flags</b>

<b>comment</b>
Any comments to preserve information about this rewrite policy label.

<b>builtin</b>
Flag to determine if rewrite policy label is built-in or not

<b>devno</b>

<b>count</b>



##Example

	i)	show rewrite policylabel trans_http_url	ii)	show rewrite policylabel

##stat rewrite policylabel

Displays statistics for the specified rewrite policy label.If no policy label name is provided, displays abbreviated statistics for all rewrite policy labels currently configured on the NetScaler appliance.


##Synopsys

stat rewrite policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the rewrite policy label.

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

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

<ul><li><a href="../../../tml#stat-rewrite-p/tml#stat-rewrite-p">stat rewrite policy</a></li></ul>



##rename rewrite policylabel

Renames a rewrite policy label.


##Synopsys

rename rewrite policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
Current name of the policy label.

<b>newName</b>
New name for the rewrite policy label. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy label" or ?my policy label?).



##Example

rename rewrite policylabel oldname newname

