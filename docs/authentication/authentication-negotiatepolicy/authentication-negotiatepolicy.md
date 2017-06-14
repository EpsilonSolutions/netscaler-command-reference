#authentication negotiatePolicy

The following operations can be performed on "authentication negotiatePolicy":


[add](#add-authentication-negotiatepolicy) | [rm](#rm-authentication-negotiatepolicy) | [set](#set-authentication-negotiatepolicy) | [unset](#unset-authentication-negotiatepolicy) | [show](#show-authentication-negotiatepolicy)

##add authentication negotiatePolicy

Adds an Active Directory (AD) Kerberos Key  Distribution Center (KCD) authentication policy (negotiate policy). The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified AD KCD server.


##Synopsys

add authentication negotiatePolicy &lt;name> &lt;rule> &lt;reqAction>


##Arguments

<b>name</b>
Name for the negotiate authentication policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after AD KCD (negotiate) policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication policy? or ?my authentication policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the AD KCD server.

<b>reqAction</b>
Name of the negotiate action to perform if the policy matches.



##rm authentication negotiatePolicy

Removes the specified AD KCD (negotiate) policy.


##Synopsys

rm authentication negotiatePolicy &lt;name>


##Arguments

<b>name</b>
Name of the negotiate policy to remove.



##set authentication negotiatePolicy

Modifies the specified AD KCD (negotiate) policy.


##Synopsys

set authentication negotiatePolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the negotiate policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the AD KCD server.

<b>reqAction</b>
Name of the negotiate action to perform if the policy matches.



##unset authentication negotiatePolicy

Use this command to remove authentication negotiatePolicy settings.Refer to the set authentication negotiatePolicy command for meanings of the arguments.


##Synopsys

unset authentication negotiatePolicy &lt;name> [-rule] [-reqAction]


##show authentication negotiatePolicy

Displays the current settings for the specified AD KCD (negotiate) policy.If no policy name is provided, displays a list of all negotiate policies currently configured on the NetScaler appliance.


##Synopsys

show authentication negotiatePolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the negotiate policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
The name of the new rule associated with the policy.

<b>reqAction</b>
The name of the Negotiate action associated with the policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



