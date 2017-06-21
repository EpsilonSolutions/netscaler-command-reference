#authentication radiusPolicy

The following operations can be performed on "authentication radiusPolicy":


[add](#add-authentication-radiuspolicy) | [rm](#rm-authentication-radiuspolicy) | [set](#set-authentication-radiuspolicy) | [unset](#unset-authentication-radiuspolicy) | [show](#show-authentication-radiuspolicy)

##add authentication radiusPolicy

Adds a RADIUS authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the RADIUS server.


##Synopsys

add authentication radiusPolicy &lt;name> &lt;rule> [&lt;reqAction>]


##Arguments

<b>name</b>
Name for the RADIUS authentication policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after RADIUS policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the RADIUS server.

<b>reqAction</b>
Name of the RADIUS action to perform if the policy matches.



##rm authentication radiusPolicy

Removes a RADIUS authentication policy.


##Synopsys

rm authentication radiusPolicy &lt;name>


##Arguments

<b>name</b>
Name of the RADIUS authentication policy to remove.



##set authentication radiusPolicy

Configures the specified RADIUS authentication policy.


##Synopsys

set authentication radiusPolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the RADIUS authentication policy.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the RADIUS server.

<b>reqAction</b>
Name of the RADIUS action to perform if the policy matches.



##unset authentication radiusPolicy

Use this command to remove authentication radiusPolicy settings.Refer to the set authentication radiusPolicy command for meanings of the arguments.


##Synopsys

unset authentication radiusPolicy &lt;name> [-rule] [-reqAction]


##show authentication radiusPolicy

Displays the current settings for the specified RADIUS authentication policy.If no policy name is provided, displays a list of all RADIUS authentication policies currently configured on the NetScaler appliance.


##Synopsys

show authentication radiusPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the RADIUS authentication policy.



##Outputs

<b>rule</b>
The new rule associated with the policy.

<b>reqAction</b>
The new RADIUS action associated with the policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



