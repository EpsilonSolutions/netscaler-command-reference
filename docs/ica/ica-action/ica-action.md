#ica action

The following operations can be performed on "ica action":


[add](#add-ica-action) | [rm](#rm-ica-action) | [set](#set-ica-action) | [rename](#rename-ica-action) | [show](#show-ica-action)

##add ica action

Creates an ICA action, which is used to specify the ICA accessprofile.The action can be associated with an ICA policy by using the add ica policy command


##Synopsys

add ica action &lt;name> -accessProfileName &lt;string>


##Arguments

<b>name</b>
Name for the ICA action. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the ICA action is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my ica action" or 'my ica action').

<b>accessProfileName</b>
Name of the ica accessprofile to be associated with this action.



##Example

add ica action ica_action_1 -accessprofileName profile1

##rm ica action

This command removes the ica action specified


##Synopsys

rm ica action &lt;name>


##Arguments

<b>name</b>
Name of the action to be removed.



##Example

rm ica action ica_action_1

##set ica action

This command modifies the specified parameters of the specified ica action.


##Synopsys

set ica action &lt;name> -accessProfileName &lt;string>


##Arguments

<b>name</b>
Name of the action that you want to modify.

<b>accessProfileName</b>
Name of the ica accessprofile to be associated with this action.



##Example

set ica action ica_action_1 -accessprofileName profile2

##rename ica action

This command renames an ICA action.


##Synopsys

rename ica action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Name of the existing action.

<b>newName</b>
New name for the ICA action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#),period (.), space, colon (:), at (@), equals (=), and hyphen (-) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks ( for example, "my ica action" or 'my ica action').



##Example

rename ica action old_name new_name

##show ica action

This command displays details of the specified ica action. If no profile is specified, displays a list of ica actions on the NetScaler appliance.


##Synopsys

show ica action [&lt;name>]


##Arguments

<b>name</b>
Name of the ICA action.



##Outputs

<b>stateflag</b>

<b>accessProfileName</b>
Name of the ica accessprofile to be associated with this action.

<b>hits</b>
The number of times the action has been taken.

<b>referenceCount</b>
The number of references to the action.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>builtin</b>
Indicates that the ICA action is a built-in (SYSTEM INTERNAL) type.

<b>isDefault</b>
A value of true is returned if it is a default action

<b>devno</b>

<b>count</b>



##Example

sh ica action ica_action_1

