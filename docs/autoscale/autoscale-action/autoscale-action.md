#autoscale action

The following operations can be performed on "autoscale action":


[add](#add-autoscale-action) | [rm](#rm-autoscale-action) | [set](#set-autoscale-action) | [unset](#unset-autoscale-action) | [show](#show-autoscale-action)

##add autoscale action

Create a AutoScale action.


##Synopsys

add autoscale action &lt;name> -type ( SCALE_UP | SCALE_DOWN ) -profileName &lt;string> -parameters &lt;string> [-vmDestroyGracePeriod &lt;positive_integer>] [-quietTime &lt;positive_integer>] -vServer &lt;string>


##Arguments

<b>name</b>
ActionScale action name.

<b>type</b>
The type of action.
Possible values: SCALE_UP, SCALE_DOWN

<b>profileName</b>
AutoScale profile name.

<b>parameters</b>
Parameters to use in the action

<b>vmDestroyGracePeriod</b>
Time in minutes a VM is kept in inactive state before destroying
Default value: 10

<b>quietTime</b>
Time in seconds no other policy is evaluated or action is taken
Default value: 300

<b>vServer</b>
Name of the vserver on which autoscale action has to be taken.



##rm autoscale action

Remove a AutoScale action.


##Synopsys

rm autoscale action &lt;name>


##Arguments

<b>name</b>
ActionScale action name.



##set autoscale action

Set a AutoScale action.


##Synopsys

set autoscale action &lt;name> [-profileName &lt;string>] [-parameters &lt;string>] [-vmDestroyGracePeriod &lt;positive_integer>] [-quietTime &lt;positive_integer>] [-vServer &lt;string>]


##Arguments

<b>name</b>
ActionScale action name.

<b>profileName</b>
AutoScale profile name.

<b>parameters</b>
Parameters to use in the action

<b>vmDestroyGracePeriod</b>
Time in minutes a VM is kept in inactive state before destroying
Default value: 10

<b>quietTime</b>
Time in seconds no other policy is evaluated or action is taken
Default value: 300

<b>vServer</b>
Name of the vserver on which autoscale action has to be taken.



##unset autoscale action

Use this command to remove autoscale action settings.Refer to the set autoscale action command for meanings of the arguments.


##Synopsys

unset autoscale action &lt;name> [-vmDestroyGracePeriod] [-quietTime]


##show autoscale action

Display the autoscale actions.


##Synopsys

show autoscale action [&lt;name>]


##Arguments

<b>name</b>
ActionScale action name.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>type</b>
The type of action.

<b>profileName</b>
AutoScale profile name.

<b>parameters</b>
Parameters to use in the action

<b>vmDestroyGracePeriod</b>
Time in minutes a VM is kept in inactive state before destroying

<b>quietTime</b>
Time in seconds no other policy is evaluated or action is taken

<b>vServer</b>
Name of the vserver on which autoscale action has to be taken.

<b>destIP</b>
IP Address on which provisioning server daemon is running

<b>destPort</b>
Port on which provisioning server daemon is running

<b>devno</b>

<b>count</b>

<b>stateflag</b>



