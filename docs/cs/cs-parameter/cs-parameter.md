#cs parameter

The following operations can be performed on "cs parameter":


[set](#set-cs-parameter) | [unset](#unset-cs-parameter) | [show](#show-cs-parameter)

##set cs parameter

Sets the status of the state update parameter for the server. By default, the content switching virtual server is always UP, regardless of the state of the load balancing virtual servers bound to it. This command enables the virtual server to check the status of the attached load balancing server for state information.


##Synopsys

set cs parameter -stateupdate ( ENABLED | DISABLED )


##Arguments

<b>stateupdate</b>
Specifies whether the virtual server checks the attached load balancing server for state information.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set cs parameter -stateupdate (ENABLED|DISABLED)

##unset cs parameter

Use this command to remove cs parameter settings.Refer to the set cs parameter command for meanings of the arguments.


##Synopsys

unset cs parameter -stateupdate


##show cs parameter

Show CS parameters


##Synopsys

show cs parameter


##Arguments

<b>format</b>

<b>level</b>



##Outputs

<b>stateupdate</b>
Specifies whether the virtual server checks the attached load balancing server for state information.



##Example

show cs parameter

