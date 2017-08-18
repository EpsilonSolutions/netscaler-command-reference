#sc policy

The following operations can be performed on "sc policy":


[add](#add-sc-policy) | [rm](#rm-sc-policy) | [set](#set-sc-policy) | [unset](#unset-sc-policy) | [show](#show-sc-policy) | [stat](#stat-sc-policy)

##add sc policy

Creates a new SureConnect policy. NOTE: This command is deprecated.SureConnect feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>name</b>
Name for the policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.

<b>url</b>
URL against which to match incoming client request.

<b>rule</b>
Expression against which the traffic is evaluated. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's URL or rule. If the delay statistics gathered for the matching request exceed the specified delay, SureConnect is triggered for that request.
Minimum value: 1
Maximum value: 599999999

<b>maxConn</b>
Maximum number of concurrent connections that can be open for requests that match the policy's URL or rule.
Minimum value: 1
Maximum value: 4294967294

<b>action</b>
Action to be taken when the delay or maximum-connections threshold is reached. Available settings function as follows:
ACS - Serve content from an alternative content service.
NS - Serve alternative content from the NetScaler appliance.
NO ACTION - Serve no alternative content. However, delay statistics are still collected for the configured URLs, and, if the Maximum Client Connections parameter is set, the number of connections is limited to the value specified by that parameter. (However, alternative content is not served even if the maxConn threshold is met).
Possible values: ACS, NS, NOACTION

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS action.

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS action.



##Example

add sc policy scpol_ns -delay 1000000 -url /delay.asp -action NSadd policy expression exp_acs "url == /mc_acs.asp"add service svc_acs 10.110.100.253 http 80add scpolicy scpol_acs -maxconn 10 -rule exp_acs -action ACS svc_acs /altcont.htm

##rm sc policy

Removes the specified SureConnect policy. NOTE: This command is deprecated.SureConnect feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>name</b>
Name of the policy to be removed.



##Example

rm sc policy scpol_nsrm sc policy scpol_acs

##set sc policy

Modifies the specified settings of a SureConnect policy. NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
Name of the policy to be modified.

<b>url</b>
URL against which to match requests. URLs take precedence over rules in SureConnect policies.

<b>rule</b>
Expression against which the traffic is evaluated. 
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the  character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's URL or rule. If the delay statistics gathered for the matching request exceed the specified delay, SureConnect is triggered for that request.
Minimum value: 1
Maximum value: 599999999

<b>maxConn</b>
Maximum number of concurrent connections that can be open for the configured URL or rule.
Minimum value: 1
Maximum value: 4294967294

<b>action</b>
Action to be taken when the delay or maximum-connections threshold is reached. Available settings function as follows:
ACS - Serve content from an alternative content service.
NS - Serve alternative content from the NetScaler appliance.
NO ACTION - Serve no alternative content. However, delay statistics are still collected for the configured URLs, and, if the Maximum Client Connections parameter is set, the number of connections is limited to the value specified by that parameter. (However, alternative content is not served even if the maxConn threshold is met).
Possible values: ACS, NS, NOACTION

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS action.

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS action.



##Example

set sc policy scpol_ns -delay 2000000set sc policy scpol_acs -maxconn 100

##unset sc policy

Use this command to remove sc policy settings.Refer to the set sc policy command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show sc policy

Displays information about the SureConnect policies. NOTE: This command is deprecated.SureConnect feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>name</b>
Name of a policy about which to display detailed information. To display information about all the SureConnect policies, do not set this parameter.



##Outputs

<b>url</b>
The URL name. The  system matches the incoming client request against the URL you enter here.

<b>rule</b>
The rule that the system matches with the incoming request.
The system matches the incoming request against the rules you enter here. Before matching against the configured rules, the NetScaler 9000 system matches the requests with any of the configured URLs. Thus, URLs have a higher precedence over rules. If the incoming request does not match any of the configured URLs or the rules that have been configured, then SureConnect does not trigger.
Expression logic is expression names, separated by the logical operators || and && , and possibly grouped using parenthesis. If the expression contains blanks (for example, between an expression name and a logical operator), then the entire argument must be enclosed in double quotes.The following are valid expression logic:
ns_ext_cgi||ns_ext_asp
ns_non_get && (ns_header_cookie||ns_header_pragma)

<b>delay</b>
Delay threshold, in microseconds, for requests that match the policy's URL or rule. If the delay statistics gathered for the matching request exceed the specified delay, SureConnect is triggered for that request.

<b>maxConn</b>
Maximum number of concurrent connections that can be open for requests that match the policy's URL or rule.

<b>action</b>
The action to be taken when the thresholds are met. The valid options are ACS , NS and NOACTION .
  ACS - Specifies that alternate content is to be served from altContSvcName with the path altContPath .
  NS - Specifies that alternate content is to be served from the NetScaler 9000 system. See the set sc parameter command to customize the response served from the system.
  NOACTION - Specifies that no alternate content is to be served. However, delay statistics are still collected for the configured URLs. If the - maxconn argument is specified, the number of connections is limited to that specified value for that configured URL or rule (alternate content will not served even if the - maxconn threshold is met).

<b>altContentSvcName</b>
Name of the alternative content service to be used in the ACS action.

<b>altContentPath</b>
Path to the alternative content service to be used in the ACS action.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

&gt; show sc policy        2 monitored Sure Connect Policies:1)      Name: scpol_ns        RULE: exp1        Delay: 1000000 microsecs        Alternate Content from NS2)      Name: scpol_acs        RULE: exp_acs        Max Conn: 10        Alternate Content from ACS, svc_acs        /delay/alcont.htm Done

##stat sc policy

Displays statistics about SureConnect policies. NOTE: This command is deprecated.SureConnect feature has been deprecated in favour of AppQoE


##Synopsys




##Arguments

<b>name</b>
Name of the policy about which to display statistics. To display statistics about all SureConnect policies, do not set this parameter.

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

<b>Server TTLB (SvrTTLB)</b>
Server Time-To-Last-Byte in seconds calculated for this SureConnect policy.

<b>Average server TTLB</b>
Average server transaction time in seconds for this SureConnect Policy.

<b>Average client TTLB (AvClTTLB)</b>
Average value of the client Time-To-Last-Byte in seconds for this SureConnect policy.

<b>Physical service IP (SvcIP)</b>
IP address of the service in dotted notation for which these statistics are maintained.

<b>Physical service port (SvcPort)</b>
Port of the service for which these statistics are maintained.

<b>Current client connections (CurClts)</b>
Number of clients currently  allowed a server connection by this SureConnect policy.

<b>Current SC queue length (WaitClts)</b>
Current number of SureConnect priority clients that are waiting for a server connection.

<b>Current server connections (CurSvrs)</b>
Current number of open connections to the servers matching this policy.

<b>Estimated waiting time (Sec) (WaitTime)</b>
Value of the currently estimated waiting time in seconds for the configured URL.

<b>Client TCP connections (TotClt)</b>
Total number of clients that were allowed a server connection by this SureConnect policy.

<b>Server TCP connections (TotSvr)</b>
Total number of server connections that were established through this SureConnect policy.

<b>Client HTTP transactions</b>
Total number of client transactions processed by this SureConnect policy.

<b>Server HTTP transactions (SrvTrans)</b>
Number of 200 OK responses received from the web server by this SureConnect policy.

<b>Requests received (TotReq)</b>
Total number of requests received by this SureConnect policy.

<b>Request bytes received (ReqBytes)</b>
Total number of request bytes received by this SureConnect policy.

<b>Server responses received (TotResp)</b>
Total number of server responses received by this SureConnect policy.

<b>Response bytes received (RspBytes)</b>
Total number of response bytes received by this SureConnect policy.



##Related Commands

<ul><li><a href="../../..//">stat sc</a></li></ul>



