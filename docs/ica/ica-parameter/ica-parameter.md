#ica parameter

The following operations can be performed on "ica parameter":


[set](#set-ica-parameter) | [unset](#unset-ica-parameter) | [show](#show-ica-parameter)

##set ica parameter

Sets the global ica configuration parameter


##Synopsys

set ica parameter -EnableSRonHAFailover ( YES | NO )


##Arguments

<b>EnableSRonHAFailover</b>
Enable/Disable Session Reliability on HA failover. The default value is No
Possible values: YES, NO
Default value: NO



##Example

set ica parameter -EnableSRonHAFailover YES

##unset ica parameter

Use this command to remove ica parameter settings.Refer to the set ica parameter command for meanings of the arguments.


##Synopsys

unset ica parameter -EnableSRonHAFailover


##show ica parameter

Displays the global ica configuration


##Synopsys

show ica parameter


##Outputs

<b>EnableSRonHAFailover</b>
Enable/Disable Session Reliability on HA failover. The default value is No



##Example

show ica parameter

