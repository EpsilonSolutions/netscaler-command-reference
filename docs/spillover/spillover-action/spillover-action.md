#spillover action

The following operations can be performed on "spillover action":


[add](#add-spillover-action) | [rm](#rm-spillover-action) | [show](#show-spillover-action) | [rename](#rename-spillover-action)

##add spillover action

Creating spillover action


##Synopsys

add spillover action &lt;name> -action SPILLOVER


##Arguments

<b>name</b>
Name of the spillover action.

<b>action</b>
Spillover action. Currently only type SPILLOVER is supported
Possible values: SPILLOVER



##rm spillover action

Removes a spillover policy.


##Synopsys

rm spillover action &lt;name>


##Arguments

<b>name</b>
Name of the spillover action.



##show spillover action

Displaying spillover actions


##Synopsys

show spillover action [&lt;name>]


##Arguments

<b>name</b>
Name of the spillover action.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>action</b>
Spillover action. Currently only type SPILLOVER is supported

<b>builtin</b>
Flag to determine whether compression is default or not

<b>gslbBindings</b>
Number of times action is used in a policy bound to a gslb vserver

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##rename spillover action

Renames a spillover action.


##Synopsys

rename spillover action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the action.

<b>newName</b>
New name for the spillover action. Must begin with an ASCII alphabetic or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at
(@), equals (=), and hyphen (-) characters. 
Choose a name that can be correlated with the function that the action performs. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my action" or 'my action').



##Example

rename spillover policy oldname newname

