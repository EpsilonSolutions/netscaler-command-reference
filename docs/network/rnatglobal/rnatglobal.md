#rnatglobal

The following operations can be performed on "rnatglobal":


[show](#show-rnatglobal) | [bind](#bind-rnatglobal) | [unbind](#unbind-rnatglobal)

##show rnatglobal

Display the Reverse NAT configuration.


##Synopsys

show rnatglobal


##Outputs

<b>policy</b>
The policy Name.

<b>stateflag</b>

<b>priority</b>
The priority of the policy.

<b>devno</b>

<b>count</b>



##bind rnatglobal

Bind rnat to policy for logging purpose


##Synopsys

bind rnatglobal [-policy &lt;string>  [-priority &lt;positive_integer>]]


##Arguments

<b>policy</b>
Name of the policy getting bound to the RNAT globally. This policy will apply to all the RNATS present

<b>priority</b>
Priority of the policy
Minimum value: 0



##unbind rnatglobal

Unbind policy from rnat


##Synopsys

unbind rnatglobal (-policy &lt;string> | -all)


##Arguments

<b>policy</b>
Name of the policy to be unbound from the RNAT globally.

<b>all</b>
Remove all RNAT global config



