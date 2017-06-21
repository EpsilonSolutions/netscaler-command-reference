#system cmdPolicy

The following operations can be performed on "system cmdPolicy":


[add](#add-system-cmdpolicy) | [rm](#rm-system-cmdpolicy) | [set](#set-system-cmdpolicy) | [show](#show-system-cmdpolicy)

##add system cmdPolicy

Adds a command policy to the system. A command policy specifies the access rights of the system user. By default, the appliance already has the following policies defined:* operator* read-only* network* superuser


##Synopsys

add system cmdPolicy &lt;policyName> &lt;action> &lt;cmdSpec>


##Arguments

<b>policyName</b>
Name for a command policy. Must begin with a letter, number, or the underscore (_) character, and must contain only alphanumeric, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), and underscore characters. Cannot be changed after the policy is created.
CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my policy" or 'my policy').

<b>action</b>
Action to perform when a request matches the policy.
Possible values: ALLOW, DENY

<b>cmdSpec</b>
Regular expression specifying the data that matches the policy.



##rm system cmdPolicy

Removes a command policy from the appliance.Note: You cannot remove command policies that are bound to a system user.


##Synopsys

rm system cmdPolicy &lt;policyName>


##Arguments

<b>policyName</b>
Name of the command policy to remove.



##set system cmdPolicy

Modifies the specified attributes of an existing command policy.


##Synopsys

set system cmdPolicy &lt;policyName> &lt;action> &lt;cmdSpec>


##Arguments

<b>policyName</b>
Name of the command policy to be modified.

<b>action</b>
Action to perform when a request matches the policy.
Possible values: ALLOW, DENY

<b>cmdSpec</b>
Regular expression specifying the data that matches the policy.



##show system cmdPolicy

Displays information about all configured system command policies, or about the specified policy.


##Synopsys

show system cmdPolicy [&lt;policyName>]


##Arguments

<b>policyName</b>
Name of the system command policy about which to display information.



##Outputs

<b>action</b>
The policy action.

<b>cmdSpec</b>
The matching rule that the policy will utilize.

<b>builtin</b>

<b>devno</b>

<b>count</b>

<b>stateflag</b>



