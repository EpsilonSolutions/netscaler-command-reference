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
Possible values: http_req, http_res, othertcp_req, othertcp_res, url, text, clientless_vpn_req, clientless_vpn_res, sipudp_req, sipudp_res, diameter_req, diameter_res

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
Name of the rewrite policy label to which to bind the policy.

<b>policyName</b>
Name of the rewrite policy to bind to the policy label.



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

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



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

