#authentication ldapPolicy

The following operations can be performed on "authentication ldapPolicy":


[add](#add-authentication-ldappolicy) | [rm](#rm-authentication-ldappolicy) | [set](#set-authentication-ldappolicy) | [unset](#unset-authentication-ldappolicy) | [show](#show-authentication-ldappolicy)

##add authentication ldapPolicy

Adds an LDAP authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified LDAP server.


##Synopsys

add authentication ldapPolicy &lt;name> &lt;rule> [&lt;reqAction>]


##Arguments

<b>name</b>
Name for the LDAP policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after LDAP policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the LDAP server.

<b>reqAction</b>
Name of the LDAP action to perform if the policy matches.



##rm authentication ldapPolicy

Removes an LDAP policy.


##Synopsys

rm authentication ldapPolicy &lt;name>


##Arguments

<b>name</b>
Name of the LDAP policy to remove.



##set authentication ldapPolicy

Configures the specified LDAP policy.


##Synopsys

set authentication ldapPolicy &lt;name> [-rule &lt;string>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the LDAP policy.

<b>rule</b>
The new rule to associate with the policy.

<b>reqAction</b>
The new LDAP action to associate with the policy.



##unset authentication ldapPolicy

Use this command to remove authentication ldapPolicy settings.Refer to the set authentication ldapPolicy command for meanings of the arguments.


##Synopsys

unset authentication ldapPolicy &lt;name> [-rule] [-reqAction]


##show authentication ldapPolicy

Displays the current settings for the specified LDAP policy.If no policy name is provided, displays a list of all LDAP policies currently configured on the NetScaler appliance.


##Synopsys

show authentication ldapPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the LDAP policy.



##Outputs

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the LDAP server.

<b>reqAction</b>
Name of the LDAP action to perform if the policy matches.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



