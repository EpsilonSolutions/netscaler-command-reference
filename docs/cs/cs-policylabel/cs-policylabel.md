#cs policylabel

The following operations can be performed on "cs policylabel":


[add](#add-cs-policylabel) | [rm](#rm-cs-policylabel) | [bind](#bind-cs-policylabel) | [unbind](#unbind-cs-policylabel) | [show](#show-cs-policylabel) | [rename](#rename-cs-policylabel)

##add cs policylabel

Adds a content switching policy label.


##Synopsys

add cs policylabel &lt;labelName> &lt;cspolicylabeltype>


##Arguments

<b>labelName</b>
Name for the policy label. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. 
The label name must be unique within the list of policy labels for content switching.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, \\?my label\\? or \\?my policylabel\\?).

<b>cspolicylabeltype</b>
Protocol supported by the policy label. All policies bound to the policy label must either match the specified protocol or be a subtype of that protocol. Available settings function as follows:
* HTTP - Supports policies that process HTTP traffic. Used to access unencrypted Web sites. (The default.)
* SSL - Supports policies that process HTTPS/SSL encrypted traffic. Used to access encrypted Web sites.
* TCP - Supports policies that process any type of TCP traffic, including HTTP.
* SSL_TCP - Supports policies that process SSL-encrypted TCP traffic, including SSL.
* UDP - Supports policies that process any type of UDP-based traffic, including DNS.
* DNS - Supports policies that process DNS traffic.
* ANY - Supports all types of policies except HTTP, SSL, and TCP.             
* SIP_UDP - Supports policies that process UDP based Session Initiation Protocol (SIP) traffic. SIP initiates, manages, and terminates multimedia communications sessions, and has emerged as the standard for Internet telephony (VoIP).
* RTSP - Supports policies that process Real Time Streaming Protocol (RTSP) traffic. RTSP provides delivery of multimedia and other streaming data, such as audio, video, and other types of streamed media.
* RADIUS - Supports policies that process Remote Authentication Dial In User Service (RADIUS) traffic. RADIUS supports combined authentication, authorization, and auditing services for network management.
* MYSQL - Supports policies that process MYSQL traffic.
* MSSQL - Supports policies that process Microsoft SQL traffic.
Possible values: HTTP, TCP, RTSP, SSL, SSL_TCP, UDP, DNS, SIP_UDP, ANY, RADIUS, RDP, MYSQL, MSSQL, ORACLE, DIAMETER, SSL_DIAMETER, FTP, DNS_TCP



##Example

add cs policylabel trans_http_url HTTP

##rm cs policylabel

Removes a content switching policy label.


##Synopsys

rm cs policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the label to be removed.



##Example

rm cs policylabel trans_http_url

##bind cs policylabel

Binds a content switching policy to a content switching policy label.


##Synopsys

bind cs policylabel &lt;labelName> &lt;policyName> &lt;priority> [-targetVserver &lt;string> | (-invoke  (&lt;labelType>  &lt;labelName>) )] [-gotoPriorityExpression &lt;expression>]


##Arguments

<b>labelName</b>
Name of the policy label to which to bind a content switching policy.

<b>policyName</b>
Name of the content switching policy to bind to the content switching policy label.

<b>priority</b>
Unsigned integer that determines the priority of the policy relative to other policies in this policy label. Smaller the number, higher the priority.
Minimum value: 1
Maximum value: 2147483647

<b>targetVserver</b>
Name of the virtual server to which to forward requests that match the policy.

<b>gotoPriorityExpression</b>
Expression or other value specifying the priority of the next policy to be evaluated if the current policy rule evaluates to TRUE. Alternatively, you can specify one of the following values:
* NEXT - Go to the policy with the next higher priority.
* END - End evaluation. (This is the default. Evaluation stops if the gotoPriorityExpression parameter is not set.)
* USE_INVOCATION_RESULT - Applicable if this entry invokes another policy label. If the final goto in the invoked policy label has a value of END, evaluation stops. If the final goto is anything other than END, the current policy label performs a NEXT.    
If you specify an expression, its result must be a number. In that case, the next action is determined as follows:
* If the expression evaluates to the priority of a policy with a lower priority (larger priority number) than the current policy, that policy is evaluated next.
* If the expression evaluates to a priority of the current policy, policy with the next highest priority is evaluated.
An UNDEF event is triggered if:
* The expression cannot be evaluated.
* The expression evaluates to a number that is smaller than the highest priority in the policy bank but is not same as any policy's priority.
* The expression evaluates to a number that is smaller than the current policy's priority.

<b>invoke</b>
Invoke other policy labels. After evaluating the policies in the invoked policy label, the appliance continues to evaluate policies that are bound to the current policy label (the selected bind point).



##Example

       i)      bind cs policylabel cs_lab lbvs_1 pol_cs 1 2

##unbind cs policylabel

Unbinds a content switching policy from a content switching policy label.


##Synopsys

unbind cs policylabel &lt;labelName> &lt;policyName>


##Arguments

<b>labelName</b>
Name of the policy label from which to unbind a content switching policy.

<b>policyName</b>
Name of the content switching policy to unbind from the label.



##Example

unbind cs policylabel cs_lab pol_cs

##show cs policylabel

Displays all the content switching policy labels, or just the specified policy label.


##Synopsys

show cs policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the content switching policy label to display.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>cspolicylabeltype</b>
Protocol supported by the policy label. All policies bound to the policy label must either match the specified protocol or be a subtype of that protocol. Available settings function as follows:
* HTTP - Supports policies that process HTTP traffic. Used to access unencrypted Web sites. (The default.)
* SSL - Supports policies that process HTTPS/SSL encrypted traffic. Used to access encrypted Web sites.
* TCP - Supports policies that process any type of TCP traffic, including HTTP.
* SSL_TCP - Supports policies that process SSL-encrypted TCP traffic, including SSL.
* UDP - Supports policies that process any type of UDP-based traffic, including DNS.
* DNS - Supports policies that process DNS traffic.
* ANY - Supports all types of policies except HTTP, SSL, and TCP.             
* SIP_UDP - Supports policies that process UDP based Session Initiation Protocol (SIP) traffic. SIP initiates, manages, and terminates multimedia communications sessions, and has emerged as the standard for Internet telephony (VoIP).
* RTSP - Supports policies that process Real Time Streaming Protocol (RTSP) traffic. RTSP provides delivery of multimedia and other streaming data, such as audio, video, and other types of streamed media.
* RADIUS - Supports policies that process Remote Authentication Dial In User Service (RADIUS) traffic. RADIUS supports combined authentication, authorization, and auditing services for network management.
* MYSQL - Supports policies that process MYSQL traffic.
* MSSQL - Supports policies that process Microsoft SQL traffic.

<b>stateflag</b>

<b>numpol</b>
number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the content switching policy.

<b>priority</b>
Specifies the priority of the policy.

<b>targetVserver</b>
Name of the virtual server to which to forward requests that match the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>invoke</b>

<b>devno</b>

<b>count</b>



##Example

       i)      show cs policylabel cs_lab        ii)     show cs policylabel

##rename cs policylabel

Rename a content switching policy label.


##Synopsys

rename cs policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
The name of the content switching policylabel.

<b>newName</b>
The new name of the content switching policylabel.



##Example

rename cs policylabel oldname newname

