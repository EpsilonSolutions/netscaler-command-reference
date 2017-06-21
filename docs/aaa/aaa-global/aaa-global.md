#aaa global

The following operations can be performed on "aaa global":


[bind](#bind-aaa-global) | [unbind](#unbind-aaa-global) | [show](#show-aaa-global)

##bind aaa global

Binds a policy globally.


##Synopsys

bind aaa global [-policy &lt;string>  [-priority &lt;positive_integer>]] [-windowsProfile &lt;string>]


##Arguments

<b>policy</b>
Name of the policy to bind globally.

<b>priority</b>
Priority to assign to the policy, as an integer. A lower number indicates a higher priority. Policies are evaluated in the order of their priority numbers.
Minimum value: 0

<b>windowsProfile</b>
Name of the negotiate profile to bind globally.



##Example

 bind aaa global -pol pol1

##unbind aaa global

Unbind the policy from the global bind point.


##Synopsys

unbind aaa global [-policy &lt;string>] [-windowsProfile &lt;string>]


##Arguments

<b>policy</b>
Name of the policy to be unbound.

<b>windowsProfile</b>
Name of the negotiate profile to be bound.



##show aaa global

Displays a list of policies that are currently bound to Global on the NetScaler appliance.


##Synopsys

show aaa global


##Outputs

<b>policy</b>
Name of the policy to be unbound.

<b>windowsProfile</b>
Name of the negotiate profile to be bound.

<b>priority</b>
Priority of the bound policy

<b>bindPolicyType</b>
Bound policy type

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



