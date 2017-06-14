#authorization policylabel

The following operations can be performed on "authorization policylabel":


[add](#add-authorization-policylabel) | [rm](#rm-authorization-policylabel) | [bind](#bind-authorization-policylabel) | [unbind](#unbind-authorization-policylabel) | [rename](#rename-authorization-policylabel) | [show](#show-authorization-policylabel) | [stat](#stat-authorization-policylabel)

##add authorization policylabel

Creates a user-defined authorization policy label.


##Synopsys

add authorization policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name for the new authorization policy label. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the authorization policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authorization policy label? or ?authorization policy label?).



##Example

add authorization policylabel trans_http_url

##rm authorization policylabel

Removes an authorization policy label.


##Synopsys

rm authorization policylabel &lt;labelName>


##Arguments

<b>labelName</b>
Name of the authorization policy label to remove.



##Example

rm authorization policylabel trans_http_url

##bind authorization policylabel

Binds an authorization policy to a label.


##Synopsys

bind authorization policylabel &lt;labelName> &lt;policyName> &lt;priority> [&lt;gotoPriorityExpression>] [-invoke  (&lt;labelType>  &lt;labelName>) ]


##Arguments

<b>labelName</b>
Name of the authorization policy label to which to bind the policy.

<b>policyName</b>
Name of the authorization policy to bind to the policy label.



##Example

	i)	bind authorization policylabel trans_http_url pol_1 1 2 -invoke reqvserver CURRENT	ii)	bind authorization policylabel trans_http_url pol_2 2

##unbind authorization policylabel

Unbinds the specified policy from the specified authorization policy label.


##Synopsys

unbind authorization policylabel &lt;labelName> &lt;policyName> [-priority &lt;positive_integer>]


##Arguments

<b>labelName</b>
Name for the new authorization policy label. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the authorization policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authorization policy label? or ?authorization policy label?).

<b>policyName</b>
Name of the authorization policy to bind to the policy label.

<b>priority</b>
Priority of the NOPOLICY to be unbound.
Minimum value: 1
Maximum value: 2147483647



##Example

unbind authorization policylabel trans_http_url pol_1

##rename authorization policylabel

Rename a auth policy label.


##Synopsys

rename authorization policylabel &lt;labelName>@ &lt;newName>@


##Arguments

<b>labelName</b>
The name of the auth policy label

<b>newName</b>
The new name of the auth policy label



##Example

rename auth policy label oldname newname

##show authorization policylabel

Displays the current settings for the specified authorization policy label.If no policy name is provided, displays a list of all authorization policy labels currently configured on the NetScaler appliance.


##Synopsys

show authorization policylabel [&lt;labelName>]


##Arguments

<b>labelName</b>
Name of the authorization policy label.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>numpol</b>
Number of polices bound to label.

<b>hits</b>
Number of times policy label was invoked.

<b>policyName</b>
Name of the authorization policy to bind to the policy label.

<b>priority</b>
Specifies the priority of the policy.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of invocation. Available settings function as follows:
* reqvserver - Send the request to the specified request virtual server.
* resvserver - Send the response to the specified response virtual server.
* policylabel - Invoke the specified policy label.

<b>labelName</b>
Name of the policy label to invoke if the current policy evaluates to TRUE, the invoke parameter is set, and Label Type is set to Policy Label.

<b>flowType</b>
Flowtype of the bound authorization policy.

<b>description</b>
Description of the policylabel

<b>flags</b>

<b>devno</b>

<b>count</b>



##Example

	i)	show authorization policylabel trans_http_url	ii)	show authorization policylabel

##stat authorization policylabel

Displays statistics for the specified authorization policy label.If no authorization policy label is specified, displays a list of all authorization policy labels.


##Synopsys

stat authorization policylabel [&lt;labelName>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>labelName</b>
Name of the authorization policy label.

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



