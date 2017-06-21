#tunnel trafficPolicy

The following operations can be performed on "tunnel trafficPolicy":


[add](#add-tunnel-trafficpolicy) | [rm](#rm-tunnel-trafficpolicy) | [set](#set-tunnel-trafficpolicy) | [unset](#unset-tunnel-trafficpolicy) | [show](#show-tunnel-trafficpolicy)

##add tunnel trafficPolicy

Creates a tunnel traffic policy. A tunnel traffic policy defines the type of compression to be used for the tunneled traffic.


##Synopsys

add tunnel trafficPolicy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the tunnel traffic policy.
Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters. Cannot be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy)'.

<b>rule</b>
Expression, against which traffic is evaluated. Written in classic or default syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
*  If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in compression action to associate with the policy.



##Example

Example 1:add tunnel trafficpolicy cmp_all_destport "REQ.TCP.DESTPORT == 0-65535" GZIPAfter creating above tunnel policy, it can be activated by binding it globally:bind tunnel global cmp_all_destportThe policy is evaluated for all traffic flowing through the ssl-vpn tunnel, and compresses traffic for all TCP application ports.Example 2:The following tunnel policy disables compression for all access from a specific subnet:add tunnel trafficpolicy local_sub_nocmp "SOURCEIP == 10.1.1.0 -netmask 255.255.255.0" NOCOMPRESSbind tunnel global local_sub_nocmp

##rm tunnel trafficPolicy

Removes a tunnel traffic policy.


##Synopsys

rm tunnel trafficPolicy &lt;name>


##Arguments

<b>name</b>
Name of the tunnel traffic policy to remove.



##Example

rm tunnel trafficpolicy tunnel_policy_nameThe "show tunnel trafficpolicy" command shows all tunnel policies that are currently defined.

##set tunnel trafficPolicy

Modifies the specified parameters of an existing tunnel traffic policy.


##Synopsys

set tunnel trafficPolicy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the tunnel traffic policy to modify.

<b>rule</b>
Expression, against which traffic is evaluated. Written in classic or default syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters&gt;" + "&lt;string of 245 characters&gt;"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
*  If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in compression action to associate with the policy.



##Example

	add tunnel trafficpolicy cmp_all_destport "REQ.TCP.DESTPORT == 0-65535" GZIP	set tunnel trafficpolicy cmp_all_destport -action NOCOMPRESS	Above 'set' command changes action for policy cmp_all_destport from GZIP to NOCOMPRESS

##unset tunnel trafficPolicy

Use this command to remove tunnel trafficPolicy settings.Refer to the set tunnel trafficPolicy command for meanings of the arguments.


##Synopsys

unset tunnel trafficPolicy &lt;name> [-rule] [-action]


##show tunnel trafficPolicy

Displays information about all the configured tunnel traffic policies, or displays detailed information about the specified tunnel traffic policy.


##Synopsys

show tunnel trafficPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the tunnel traffic policy for which to show detailed information.



##Outputs

<b>rule</b>
Expression, against which traffic is evaluated. Written in classic or default syntax.
Maximum length of a string literal in the expression is 255 characters. A longer string can be split into smaller strings of up to 255 characters each, and the smaller strings concatenated with the + operator. For example, you can create a 500-character string as follows: '"&lt;string of 255 characters>" + "&lt;string of 245 characters>"'
The following requirements apply only to the NetScaler CLI:
*  If the expression includes blank spaces, the entire expression must be enclosed in double quotation marks.
*  If the expression itself includes double quotation marks, you must escape the quotations by using the \\ character. 
*  Alternatively, you can use single quotation marks to enclose the rule, in which case you do not have to escape the double quotation marks.

<b>action</b>
Name of the built-in compression action to associate with the policy.

<b>hits</b>
No of hits.

<b>txbytes</b>
Number of bytes transmitted.

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

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>flags</b>

<b>bindPolicyType</b>

<b>isDefault</b>
A value of true is returned if it is a default tunnelpolicy.

<b>policyType</b>

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

&gt; show tunnel trafficpolicy        2 Tunnel policies:1) Name: local_sub_nocmp   Rule: SOURCEIP == 10.1.1.0 -netmask 255.255.255.0   Action: NOCOMPRESS   Hits: 32) Name: cmp_all   Rule: REQ.TCP.DESTPORT == 0-65535   Action: GZIP   Hits: 57125   Bytes In:...796160      	Bytes Out:... 197730   Bandwidth saving...75.16%   Ratio 4.03:1 Done

