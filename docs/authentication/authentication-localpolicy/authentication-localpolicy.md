#authentication localPolicy

The following operations can be performed on "authentication localPolicy":


[add](#add-authentication-localpolicy) | [rm](#rm-authentication-localpolicy) | [set](#set-authentication-localpolicy) | [show](#show-authentication-localpolicy)

##add authentication localPolicy

Adds a policy for the NetScaler appliance to locally authenticate a user. The policy contains criteria that specify when and how to authenticate a user.


##Synopsys

add authentication localPolicy &lt;name> &lt;rule>


##Arguments

<b>name</b>
Name for the local authentication policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after local policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my authentication policy? or ?my authentication policy?).

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to perform the authentication.



##rm authentication localPolicy

Removes the specified local authentication policy.


##Synopsys

rm authentication localPolicy &lt;name>


##Arguments

<b>name</b>
Name of the local policy to remove.



##set authentication localPolicy

Configures the specified local authentication policy.


##Synopsys

set authentication localPolicy &lt;name> -rule &lt;expression>


##Arguments

<b>name</b>
Name of the local authentication policy.

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to perform the authentication.



##show authentication localPolicy

Displays the current settings for the specified local authentication policy.If no policy name is provided, displays a list of all local authentication policies currently configured on the NetScaler appliance.


##Synopsys

show authentication localPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the local authentication policy.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>rule</b>
The new rule associated with the policy.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>reqAction</b>
The name of the RADIUS action the policy uses

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



