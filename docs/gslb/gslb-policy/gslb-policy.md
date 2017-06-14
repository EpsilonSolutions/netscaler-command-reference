#gslb policy

The following operations can be performed on "gslb policy":


[add](#add-gslb-policy) | [rm](#rm-gslb-policy) | [set](#set-gslb-policy) | [show](#show-gslb-policy)

##add gslb policy

Add GSLB policy NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the GSLB policy

<b>reqRule</b>
The expression rule

<b>action</b>
The GSLB action to be used when the reqrule is matched



##Example

add gslb policy gslb_redirect -reqRule client_Japan -action pref_site

##rm gslb policy

Remove the gslb policy configured in the system NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the policy  to be removed



##Example

rm gslb policy gslb_redirect

##set gslb policy

Change the action for the given gslb policy NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the gslb policy.

<b>action</b>
The action to be taken for the given gslb policy



##Example

set gslb policy gslb_redirect -action redirect_asia

##show gslb policy

Display the configured GSLB policy NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the GSLB policy.

<b>format</b>

<b>level</b>



##Outputs

<b>reqRule</b>
The expression rule

<b>action</b>
The action taken for the given gslb policy.

<b>hits</b>
Number of policy hits for the gslb policy.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show gslb policy

