#appfw policy

The following operations can be performed on "appfw policy":


[add](#add-appfw-policy) | [rm](#rm-appfw-policy) | [set](#set-appfw-policy) | [unset](#unset-appfw-policy) | [show](#show-appfw-policy) | [stat](#stat-appfw-policy) | [rename](#rename-appfw-policy)

##add appfw policy

Creates an application firewall policy.


##Synopsys

add appfw policy &lt;name> &lt;rule> &lt;profileName> [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name for the policy. 
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at (@), equals \\(=\\), colon \\(:\\), and underscore characters. Can be changed after the policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my policy" or 'my policy'\\).

<b>rule</b>
Name of the NetScaler named rule, or a NetScaler default syntax expression, that the policy uses to determine whether to filter the connection through the application firewall with the designated profile.

<b>profileName</b>
Name of the application firewall profile to use if the policy matches.

<b>comment</b>
Any comments to preserve information about the policy for later reference.

<b>logAction</b>
Where to log information for connections that match this policy.



##rm appfw policy

Removes an application firewall policy.


##Synopsys

rm appfw policy &lt;name>


##Arguments

<b>name</b>
Name of the policy to remove.



##set appfw policy

Modifies the specified parameters of an application firewall policy.


##Synopsys

set appfw policy &lt;name> [-rule &lt;expression>] [-profileName &lt;string>] [-comment &lt;string>] [-logAction &lt;string>]


##Arguments

<b>name</b>
Name of the policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a NetScaler default syntax expression, that the policy uses to determine whether to filter the connection through the application firewall with the designated profile.

<b>profileName</b>
Name of the application firewall profile to use if the policy matches.

<b>comment</b>
Any comments to preserve information about the policy for later reference.

<b>logAction</b>
Where to log information for connections that match this policy.



##Example

set transform policy pol9 -rule "HTTP.REQ.HEADER(\\\\"header\\\\").CONTAINS(\\\\"qh2\\\\")"

##unset appfw policy

Removes the settings of an existing application firewall policy. Attributes for which a default value is available revert to their default values. See the set appfw policy command for a description of the parameters..Refer to the set appfw policy command for meanings of the arguments.


##Synopsys

unset appfw policy &lt;name> [-comment] [-logAction]


##Example

unset transform policy pol9 -undefAction

##show appfw policy

Displays the current settings for the specified application firewall policy.If no policy name is provided, displays a list of all application firewall policies currently configured on the NetScaler appliance.


##Synopsys

show appfw policy [&lt;name>]


##Arguments

<b>name</b>
Name of the policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>rule</b>
Name of the NetScaler named rule, or a NetScaler default syntax expression, that the policy uses to determine whether to filter the connection through the application firewall with the designated profile.

<b>profileName</b>
Name of the application firewall profile to use if the policy matches.

<b>hits</b>
Number of hits.

<b>piHits</b>
Number of hits.

<b>undefHits</b>
Number of Undef hits.

<b>gotoPriorityExpression</b>
Expression specifying the priority of the next policy which will get evaluated if the current policy rule evaluates to TRUE.

<b>labelType</b>
Type of policy label invocation.

<b>labelName</b>
Name of the label to invoke if the current policy rule evaluates to TRUE.

<b>comment</b>
Any comments to preserve information about the policy for later reference.

<b>logAction</b>
Where to log information for connections that match this policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>
Indicates whether policy is bound or not.

<b>priority</b>
Specifies the priority of the policy.

<b>bindPolicyType</b>

<b>policyType</b>

<b>vserverType</b>

<b>devno</b>

<b>count</b>



##stat appfw policy

Displays statistics for the specified application firewall policy. If no application firewall policy is specified, displays abbreviated statistics for all application firewall policies.


##Synopsys

stat appfw policy [&lt;name>] [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>name</b>
Name of the application firewall policy.

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

stat appfw policy

##Related Commands

<ul><li><a href="../../..//">stat appfw</a></li><li><a href="../../../#stat-appfw-pr/#stat-appfw-pr">stat appfw profile</a></li><li><a href="../../../html#stat-appfw-policy/html#stat-appfw-policy">stat appfw policylabel</a></li></ul>



##rename appfw policy

Renames an application firewall policy.


##Synopsys

rename appfw policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the application firewall policy.

<b>newName</b>
New name for the policy. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').



##Example

rename appfw policy oldname newname

