#appflow action

The following operations can be performed on "appflow action":


[add](#add-appflow-action) | [rm](#rm-appflow-action) | [set](#set-appflow-action) | [unset](#unset-appflow-action) | [rename](#rename-appflow-action) | [show](#show-appflow-action)

##add appflow action

Creates an AppFlow action. The action can be associated with an AppFlow policy by using the add appflow policy command.


##Synopsys

add appflow action &lt;name> -collectors &lt;string> ... [-clientSideMeasurements ( ENABLED | DISABLED )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow action" or 'my appflow action').

<b>collectors</b>
Name(s) of collector(s) to be associated with the AppFlow action.

<b>clientSideMeasurements</b>
On enabling this option, the NetScaler will collect the time required to load and render the mainpage on the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>comment</b>
Any comments about this action.  In the CLI, if including spaces between words, enclose the comment in quotation marks. (The quotation marks are not required in the configuration utility.)



##Example

add appflow action appflow_action_1 -collectors col1 col2

##rm appflow action

Removes a configured AppFlow action. You cannot remove an action that is associated with an AppFlow policy.


##Synopsys

rm appflow action &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##Example

rm appflow action appflow_action_1

##set appflow action

Modifies the specified parameters of an AppFlow action.


##Synopsys

set appflow action &lt;name> [-collectors &lt;string> ...] [-clientSideMeasurements ( ENABLED | DISABLED )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the action to be modified.

<b>collectors</b>
Name(s) of collector(s) to be associated with the AppFlow action.

<b>clientSideMeasurements</b>
On enabling this option, the NetScaler will collect the time required to load and render the mainpage on the client.
Possible values: ENABLED, DISABLED
Default value: DISABLED

<b>comment</b>
Any comments about this action.  In the CLI, if including spaces between words, enclose the comment in quotation marks. (The quotation marks are not required in the configuration utility.)



##Example

set appflow action appflow_action_1 -collectors col1 col2 col3

##unset appflow action

Use this command to remove appflow action settings.Refer to the set appflow action command for meanings of the arguments.


##Synopsys

unset appflow action &lt;name> [-clientSideMeasurements] [-comment]


##rename appflow action

Renames an AppFlow action.


##Synopsys

rename appflow action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the action.

<b>newName</b>
New name for the AppFlow action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at
(@), equals (=), and hyphen (-) characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my appflow action" or 'my appflow action').



##Example

rename appflow action old_name new_name

##show appflow action

Displays information about AppFlow action(s), or about the specified AppFlow action.


##Synopsys

show appflow action [&lt;name>]


##Arguments

<b>name</b>
Name of the action about which to display information.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>hits</b>
The number of times the action has been taken.

<b>collectors</b>
Name(s) of collector(s) to be associated with the AppFlow action.

<b>clientSideMeasurements</b>
On enabling this option, the NetScaler will collect the time required to load and render the mainpage on the client.

<b>referenceCount</b>
The number of references to the action.

<b>description</b>
Description of the action

<b>comment</b>
Comments associated with the AppFlow action.

<b>devno</b>

<b>count</b>



##Example

1. show appflow action	2. show appflow action appflow_action_1

