#authentication certPolicy

The following operations can be performed on "authentication certPolicy":


[add](#add-authentication-certpolicy) | [rm](#rm-authentication-certpolicy) | [set](#set-authentication-certpolicy) | [unset](#unset-authentication-certpolicy) | [show](#show-authentication-certpolicy)

##add authentication certPolicy

Adds a client certificate (cert) authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified client cert authentication server.


##Synopsys

add authentication certPolicy &lt;name> &lt;rule> [&lt;reqAction>]


##Arguments

<b>name</b>
Name for the client certificate authentication policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after cert authentication policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the authentication server.

<b>reqAction</b>
Name of the client cert authentication action to be performed if the policy matches.



##rm authentication certPolicy

Removes a client cert authentication policy.


##Synopsys

rm authentication certPolicy &lt;name>


##Arguments

<b>name</b>
Name of the client cert policy to remove.



##set authentication certPolicy

Configures the specified client cert authentication policy.


##Synopsys

set authentication certPolicy &lt;name> [-rule &lt;expression>] [-reqAction &lt;string>]


##Arguments

<b>name</b>
Name of the client cert policy.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the authentication server.

<b>reqAction</b>
Name of the client cert authentication action to be performed if the policy matches.



##unset authentication certPolicy

Use this command to remove authentication certPolicy settings.Refer to the set authentication certPolicy command for meanings of the arguments.


##Synopsys

unset authentication certPolicy &lt;name> [-rule] [-reqAction]


##show authentication certPolicy

Displays the current settings for the specified client cert authentication policy.If no policy name is provided, displays a list of all client cert authentication policies currently configured on the NetScaler appliance.


##Synopsys

show authentication certPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the client cert authentication policy.



##Outputs

<b>rule</b>
The rule associated with the policy.

<b>reqAction</b>
The cert action associated with the policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



