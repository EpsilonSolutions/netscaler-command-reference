#authentication dfaPolicy

The following operations can be performed on "authentication dfaPolicy":


[add](#add-authentication-dfapolicy) | [rm](#rm-authentication-dfapolicy) | [set](#set-authentication-dfapolicy) | [show](#show-authentication-dfapolicy)

##add authentication dfaPolicy

Adds an DFA authentication policy. The policy defines the criteria under which the NetScaler appliance attempts to authenticate the user with the specified Web server.


##Synopsys

add authentication dfaPolicy &lt;name> -rule &lt;string> -action &lt;string>


##Arguments

<b>name</b>
Name for the DFA policy. 
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after DFA policy is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my authentication policy" or 'my authentication policy').

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the Web server.

<b>action</b>
Name of the DFA action to perform if the policy matches.



##rm authentication dfaPolicy

Removes an DFA policy.


##Synopsys

rm authentication dfaPolicy &lt;name>


##Arguments

<b>name</b>
Name of the DFA policy to remove.



##set authentication dfaPolicy

Configures the specified DFA policy.


##Synopsys

set authentication dfaPolicy &lt;name> [-rule &lt;string>] [-action &lt;string>]


##Arguments

<b>name</b>
Name of the DFA policy.

<b>rule</b>
The new rule to associate with the policy.

<b>action</b>
The new DFA action to associate with the policy.



##show authentication dfaPolicy

Displays the current settings for the specified DFA policy.If no policy name is provided, displays a list of all DFA policies currently configured on the NetScaler appliance.


##Synopsys

show authentication dfaPolicy [&lt;name>]


##Arguments

<b>name</b>
Name of the WebAuth policy.



##Outputs

<b>rule</b>
Name of the NetScaler named rule, or a default syntax expression, that the policy uses to determine whether to attempt to authenticate the user with the Web server.

<b>action</b>
Name of the DFA action to perform if the policy matches.

<b>boundTo</b>
The entity name to which policy is bound

<b>activePolicy</b>

<b>priority</b>

<b>bindPolicyType</b>

<b>policyType</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



