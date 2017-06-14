#gslb action

The following operations can be performed on "gslb action":


[add](#add-gslb-action) | [rm](#rm-gslb-action) | [set](#set-gslb-action) | [show](#show-gslb-action)

##add gslb action

Add GSLB action used in the GSLB policy NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the GSLB action

<b>preferredLocation</b>
The target site to be returned in the DNS response when a policy is successfully evaluated against the incoming DNS request. Target site is specified in dotted notation with up to 6 qualifiers. Wildcard `*' is accepted as a valid qualifier token.



##Example

add gslb action pref_site -preferredlocation NorthAmerica.US.*.*.*.*

##rm gslb action

Remove the gslb action configured in the system NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the action to be removed



##Example

rm gslb action redirect_asia

##set gslb action

Change the preferredlocation of the given gslb action NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the GSLB action

<b>preferredLocation</b>
The target site to be returned in the DNS response when a policy is successfully evaluated against the incoming DNS request. Target site is specified in dotted notation with up to 6 qualifiers. Wildcard `*' is accepted as a valid qualifier token.



##Example

set gslb action pref_site -preferredlocation NorthAmerica.US.*.*.*.*

##show gslb action

Display the GSLB actions configured NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>name</b>
The name of the action.

<b>format</b>

<b>level</b>



##Outputs

<b>preferredLocation</b>
The target site to be returned in the DNS response when a policy is successfully evaluated against the incoming DNS request. Target site is specified in dotted notation with up to 6 qualifiers. Wildcard `*' is accepted as a valid qualifier token.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show gslb action

