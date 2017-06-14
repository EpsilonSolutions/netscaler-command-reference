#authentication samlPolicy

The following operations can be performed on "authentication samlPolicy":


[add](#add-authentication-samlpolicy) | [rm](#rm-authentication-samlpolicy) | [set](#set-authentication-samlpolicy) | [unset](#unset-authentication-samlpolicy) | [show](#show-authentication-samlpolicy)

##add authentication samlPolicy

Adds a SAML authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified SAML server.


##Synopsys

add authentication samlPolicy &lt;name> &lt;rule> &lt;reqAction>


##Arguments

<b>name</b>
Name for the SAML policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after SAML policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication policy? or ?my authentication policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the SAML server.

<b>reqAction</b>
Name of the SAML authentication action to be performed if the policy matches.



##rm authentication samlPolicy

Removes the specified SAML policy.


##Synopsys

rm authentication samlPolicy &lt;name>


##Arguments

<b>name</b>
Name of the policy to remove.



##set authentication samlPolicy

Modifies the specified parameters of a SAML policy.


##Synopsys

set authentication samlPolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the SAML policy to modify.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the SAML server.

<b>reqAction</b>
Name of the SAML authentication action to be performed if the policy matches.



##unset authentication samlPolicy

Use this command to remove authentication samlPolicy settings.Refer to the set authentication samlPolicy command for meanings of the arguments.


##Synopsys

unset authentication samlPolicy &lt;name> [-rule] [-reqAction]


##show authentication samlPolicy

Displays the current settings for the specified SAML policy.If no policy name is provided, displays a list of all SAML policies currently configured on the NetScaler appliance.


##Synopsys

show authentication samlPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the SAML policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
The name of the new rule associated with the policy.

<b>reqAction</b>
The name of the SAML action associated with the policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



