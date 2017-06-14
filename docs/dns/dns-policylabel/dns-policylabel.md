#dns policylabel

The following operations can be performed on "dns policylabel":


[add](#add-dns-policylabel) | [rm](#rm-dns-policylabel) | [bind](#bind-dns-policylabel) | [unbind](#unbind-dns-policylabel) | [show](#show-dns-policylabel) | [stat](#stat-dns-policylabel) | [rename](#rename-dns-policylabel)

##add dns policylabel

Add a dns policy label.


##Synopsys

add dns policylabel &lt;labelName> &lt;transform>


##Arguments

<b>labelName</b>
Name of the dns policy label.

<b>transform</b>
The type of transformations allowed by the policies bound to the label.
Possible values: dns_req, dns_res



##Example

add dns policylabel trans_dns dns_req

##rm dns policylabel

Remove a dns policy label.


##Synopsys

rm dns policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the dns policy label.



##Example

rm dns policylabel trans_dns

##bind dns policylabel

Bind the dns policy to one of the labels.


##Synopsys

bind dns policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the dns policy label.

<b>policyName</b>
The dns policy name.



##Example

	i)	bind dns policylabel trans_dns pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind rewrite policylabel trans_http_url pol_2 2

##unbind dns policylabel

Unbind entities from dns label.


##Synopsys

unbind dns policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name of the dns policy label.

<b>policyName</b>
The dns policy name.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind dns policylabel trans_dns pol_1

##show dns policylabel

Display policy label or policies bound to dns policylabel.


##Synopsys

show dns policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the dns policy label.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>transform</b>
The type of transformations allowed by the policies bound to the label.

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
The dns policy name.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>invoke</b>
Invoke flag.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>flowType</b>
Flowtype of the bound dns policy.

<b>description</b>
Description of the policylabel

<b>isDefault</b>
A value of true is returned if it is a default dns policylabel.

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show dns policylabel trans_dns	ii)	show dns policylabel

##stat dns policylabel

Display statistics of dns policylabel(s).


##Synopsys

stat dns policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
The name of the dns policy label for which statistics will be displayed.  If not given statistics are shown for all dns policylabels.

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

<ul><li><a href="../../..//">stat dns</a></li><li><a href="../../../t-dns-re/t-dns-re">stat dns records</a></li></ul>



##rename dns policylabel

Rename a dns policy label.


##Synopsys

rename dns policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
The name of the dns policylabel.

<b>newName</b>
The new name of the dns policylabel.



##Example

rename dns policylabel oldname newname

