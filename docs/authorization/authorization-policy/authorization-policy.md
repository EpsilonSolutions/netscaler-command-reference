#authorization policy

The following operations can be performed on "authorization policy":


[add](#add-authorization-policy) | [rm](#rm-authorization-policy) | [set](#set-authorization-policy) | [rename](#rename-authorization-policy) | [show](#show-authorization-policy)

##add authorization policy

Creates an authorization policy. Authorization policies allow AAA users and AAA groups to access resources through SSL VPN/AAA-TM enabled virtual servers.


##Synopsys

add authorization policy &lt;name> &lt;rule> &lt;action>


##Arguments

<b>name</b>
Name for the new authorization policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the authorization policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authorization policy? or ?my authorization policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to perform the authentication.

<b>action</b>
Action to perform if the policy matches: either allow or deny the request.



##Example

Example: Consider the following authorization policy, "author-policy",	add authorization policy author-policy "URL == /*.gif" DENY	bind aaa user foo -policy author-policyIf the user "foo" now logs in through the SSL VPN and makes any other request except "gif", the rule will be evaluated to FALSE, and the negetion of DENY, i.e. ALLOW, will be applied. So all those resource will implicitly be allowed to access. If "foo" tries to accesss "abc.gif" this access will be denied.

##rm authorization policy

Removes an authorization policy.


##Synopsys

rm authorization policy &lt;name>


##Arguments

<b>name</b>
Name of the authorization policy to be removed.



##set authorization policy

Configures the specified parameters of an authorization policy.


##Synopsys

set authorization policy &lt;name> [-rule &lt;expression>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the authorization policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to perform the authentication.

<b>action</b>
Action to perform if the policy matches: either allow or deny the request.



##rename authorization policy

Rename a author policy.


##Synopsys

rename authorization policy &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
The name of the author policy.

<b>newName</b>
The new name of the author policy.



##Example

rename auth policy oldname newname

##show authorization policy

Displays the current settings for the specified authorization policy. If no policy name is provided, displays a list of all authorization policies currently configured on the NetScaler appliance.


##Synopsys

show authorization policy [&lt;name>]


##Arguments

<b>name</b>
Name of the authorization policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
Rule of the policy.

<b>action</b>
Authorization action associated with the policy. It can be either ALLOW or DENY.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>flag</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>vserverType</b>

<b>expressionType</b>
Type of policy (Classic/Advanced)

<b>devno</b>

<b>count</b>

<b>stateflag</b>



