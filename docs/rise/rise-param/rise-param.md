#rise param

The following operations can be performed on "rise param":


[set](#set-rise-param) | [unset](#unset-rise-param) | [show](#show-rise-param)

##set rise param

Sets the global parameters for RISE


##Synopsys

set rise param [-directMode ( ENABLED | DISABLED )] [-indirectMode ( ENABLED | DISABLED )]


##Arguments

<b>directMode</b>
RISE Direct attach mode
Possible values: ENABLED, DISABLED
Default value: GENENABLED

<b>indirectMode</b>
RISE Indirect attach mode
Possible values: ENABLED, DISABLED
Default value: GENDISABLED



##Example

set riseParam -directMode ENABLED

##unset rise param

Use this command to remove rise param settings.Refer to the set rise param command for meanings of the arguments.


##Synopsys

unset rise param [-directMode] [-indirectMode]


##show rise param

Display the global parameters for RISE


##Synopsys

show rise param


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>directMode</b>
RISE Direct attach mode

<b>indirectMode</b>
RISE Indirect attach mode



##Example

show riseParam

