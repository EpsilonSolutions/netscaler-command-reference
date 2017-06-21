#authentication tacacsPolicy

The following operations can be performed on "authentication tacacsPolicy":


[add](#add-authentication-tacacspolicy) | [rm](#rm-authentication-tacacspolicy) | [set](#set-authentication-tacacspolicy) | [unset](#unset-authentication-tacacspolicy) | [show](#show-authentication-tacacspolicy)

##add authentication tacacsPolicy

Adds a TACACS+ authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified TACACS+ server.


##Synopsys

add authentication tacacsPolicy &lt;name> &lt;rule> [&lt;reqAction>]


##Arguments

<b>name</b>
Name for the TACACS+ policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after TACACS+ policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the TACACS+ server.

<b>reqAction</b>
Name of the TACACS+ action to perform if the policy matches.



##rm authentication tacacsPolicy

Removes the specified TACACS+ policy.


##Synopsys

rm authentication tacacsPolicy &lt;name>


##Arguments

<b>name</b>
Name of the TACACS+ policy to remove.



##set authentication tacacsPolicy

Configures the specified TACACS+ policy.


##Synopsys

set authentication tacacsPolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the TACACS+ policy.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the TACACS+ server.

<b>reqAction</b>
Name of the TACACS+ action to perform if the policy matches.



##unset authentication tacacsPolicy

Use this command to remove authentication tacacsPolicy settings.Refer to the set authentication tacacsPolicy command for meanings of the arguments.


##Synopsys

unset authentication tacacsPolicy &lt;name> [-rule] [-reqAction]


##show authentication tacacsPolicy

Displays the current settings for the specified TACACS+ policy.If no policy name is provided, displays a list of all TACACS+ policies currently configured on the NetScaler appliance.


##Synopsys

show authentication tacacsPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the TACACS+ policy.



##Outputs

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the TACACS+ server.

<b>reqAction</b>
Name of the TACACS+ action to perform if the policy matches.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



