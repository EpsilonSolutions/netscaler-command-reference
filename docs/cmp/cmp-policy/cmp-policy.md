#cmp policy

The following operations can be performed on "cmp policy":


[add](#add-cmp-policy) | [rm](#rm-cmp-policy) | [set](#set-cmp-policy) | [show](#show-cmp-policy) | [stat](#stat-cmp-policy) | [rename](#rename-cmp-policy)

##add cmp policy

Creates a classic or default syntax HTTP compression policy. When the policy matches an HTTP request or response, the action specified in the policy is performed on the transaction. The policy can be bound globally or to an entity. For the policy to have an effect, compression must be enabled on the service.


##Synopsys

add cmp policy &lt;name> -rule &lt;expression> -resAction &lt;string>


##Arguments

<b>name</b>
Name of the HTTP compression policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
Can be changed after the policy is created. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp policy" or 'my cmp policy').

<b>rule</b>
Expression that determines which HTTP requests or responses match the compression policy. Can be a classic expression or a default-syntax expression.  
Note:
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
* If the expression includes one or more spaces, enclose the entire expression in double quotation marks.
* If the expression itself includes double quotation marks, escape the quotations by using the \\ character. 
* Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>resAction</b>
The built-in or user-defined compression action to apply to the response when the policy matches a request or response.



##Example

Example 1:add cmp policy pdf_cmp -rule "RES.HTTP.HEADER Content-Type CONTAINS application/pdf" -resAction COMPRESSAfter creating the above compression policy, you must activate it by binding it globally:bind cmp global pdf_cmpThe NetScaler system will use the configured pdf_cmp compression policy to perform compression of pdf files.Example 2:The following command disables compression for all the access from the specific subnet.add cmp policy local_sub_nocmp -rule "SOURCEIP == 10.1.1.0 -netmask 255.255.255.0" -resAction NOCOMPRESSbind cmp global local_sub_nocmp

##rm cmp policy

Removes a user-defined HTTP compression policy.


##Synopsys

rm cmp policy &lt;name>


##Arguments

<b>name</b>
Name of the HTTP compression policy to be removed.



##Example

rm cmp policy cmp_policy_nameThe "show cmp policy" command shows all currently defined HTTP compression policies.

##set cmp policy

Modifies the specified parameters of an HTTP compression policy. Note: Use the show cmp policy command to view all configured HTTP compression policies.


##Synopsys

set cmp policy &lt;name> [-rule &lt;expression>] [-resAction &lt;string>]


##Arguments

<b>name</b>
Name of the HTTP compression policy to be modified.

<b>rule</b>
New rule to be associated with the HTTP compression policy. You can modify the existing rule or create a new rule.

<b>resAction</b>
The built-in or user-defined compression action to be associated with the policy.



##Example

Example 1:add cmp policy pdf_cmp -rule "RES.HTTP.HEADER Content-Type CONTAINS application/pdf" -resAction COMPRESSAfter creating the above compression policy, you must activate it by binding it globally:bind cmp global pdf_cmpThe NetScaler system will use the configured pdf_cmp compression policy to perform compression for pdf files.To disable pdf compression for Internet Explorer, you can change the above compression policy by issuing the following command:set cmp policy pdf_cmp -rule "RES.HTTP.HEADER Content-Type CONTAINS application/pdf && RES.HTTP.HEADER User-Agent NOTCONTAINS MSIE"To view the changed cmp policy, enter the following command:&gt;show cmp policy pdf_cmp        Name: pdf_cmp   Rule: (RES.HTTP.HEADER Content-Type CONTAINS application/pdf && REQ.HTTP.HEADER User-Agent NOTCONTAINS MSIE)        Response action: COMPRESS       Hits: 2        Bytes In:...609284      Bytes Out:... 443998        Bandwidth saving...27.13%       Ratio 1.37:1 Done

##show cmp policy

Displays details of all HTTP compression policies.


##Synopsys

show cmp policy [&lt;name>]show cmp policy stats - alias for 'stat cmp policy'


##Arguments

<b>name</b>
Name of the HTTP compression policy for which to display details.



##Outputs

<b>stateflag</b>

<b>expressionType</b>
Type of policy (Classic/Advanced)

<b>rule</b>
The request/response rule that will trigger the specified compression action.

<b>reqAction</b>
The compression action to be performed on requests.

<b>resAction</b>
The compression action to be performed on responses.

<b>hits</b>
Number of hits.

<b>txbytes</b>
Number of bytes transferred.

<b>rxbytes</b>
Number of bytes received.

<b>clientTTLB</b>
Total client TTLB value.

<b>clientTransactions</b>
Number of client transactions.

<b>serverTTLB</b>
Total server TTLB value.

<b>serverTransactions</b>
Number of server transactions.

<b>piHits</b>
Number of hits.

<b>piTxBytes</b>
Number of bytes transferred.

<b>piRxBytes</b>
Number of bytes received.

<b>piCltTTLB</b>
Total client TTLB value.

<b>piCltTransactions</b>
Number of client transactions.

<b>piSvrTTLB</b>
Total server TTLB value.

<b>piSvrTransactions</b>
Number of server transactions.

<b>boundTo</b>
The name of the entity to which the policy is bound.

<b>activePolicy</b>

<b>priority</b>

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>description</b>
Description of the policy

<b>bindPolicyType</b>

<b>policyType</b>

<b>vserverType</b>

<b>builtin</b>
Flag to determine if compression policy is builtin or not

<b>isDefault</b>
A value of true is returned if it is a default policy

<b>devno</b>

<b>count</b>



##Example

&gt; show cmp policy        4 Compression policies:1)      Name: ns_cmp_content_type       Rule: ns_content_type        Response action: COMPRESS       Hits: 1        Bytes In:...4325        Bytes Out:... 1530        Bandwidth saving...64.62%       Ratio 2.83:12)      Name: ns_cmp_msapp      Rule: (ns_msie && ns_msword || (ns_msexcel || ns_msppt))        Response action: COMPRESS       Hits: 7        Bytes In:...796160      Bytes Out:... 197730        Bandwidth saving...75.16%       Ratio 4.03:13)      Name: ns_cmp_mscss      Rule: (ns_msie && ns_css)        Response action: COMPRESS       Hits: 04)      Name: ns_nocmp_mozilla_47       Rule: (ns_mozilla_47 && ns_css)        Response action: NOCOMPRESS     Hits: 0 DoneYou can also view an individual cmp policy by giving the cmp policy name as an argument:&gt; show cmp policy ns_cmp_msapp        Name: ns_cmp_msapp      Rule: (ns_msie && ns_msword || (ns_msexcel || ns_msppt))        Response action: COMPRESS       Hits: 7        Bytes In:...796160      Bytes Out:... 197730        Bandwidth saving...75.16%       Ratio 4.03:1 Done

##stat cmp policy

Displays compression statistics for all advanced compression policies, or for only the specified policy.


##Synopsys

stat cmp policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the advanced compression policy for which to display statistics. If no name is specified, statistics for all advanced compression polices are shown.

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

<b>Policy hits (Hits)</b>
Number of hits on the policy

<b>Policy undef hits (Undefhits)</b>
Number of undef hits on the policy



##Example

stat cmp policy

##Related Commands

<ul><li><a href="../../..//">stat cmp</a></li><li><a href="../../../#stat-cmp-policy/#stat-cmp-policy">stat cmp policylabel</a></li></ul>



##rename cmp policy

Renames a compression policy.


##Synopsys

rename cmp policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the policy.

<b>newName</b>
New name for the compression policy. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
Choose a name that reflects the function that the policy performs. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my cmp policy" or 'my cmp policy').



##Example

rename cmp policy oldname newname

