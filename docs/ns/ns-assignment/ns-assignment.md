#ns assignment

The following operations can be performed on "ns assignment":


[add](#add-ns-assignment) | [rm](#rm-ns-assignment) | [show](#show-ns-assignment) | [rename](#rename-ns-assignment)

##add ns assignment

Creates an assignment of a value to a variable. The variable (the left hand side) may be a singleton variable or a map with a key expression. The value (the right hand side) is computed from a default syntax expression and may be used to set the variable or may be added to or subtracted from the current value of a ulong variable or appended to a text variable. The key expression, if present, is evaluated before the value expression. The left hand side variable value may also be cleared, in which case there is no value expression.


##Synopsys

add ns assignment &lt;name> -variable &lt;expression> [-set &lt;expression> | -add &lt;expression> | -sub &lt;expression> | -append &lt;expression> | -clear] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the assignment. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the assignment is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my assignment" or ?my assignment?).

<b>variable</b>
Left hand side of the assigment, of the form $variable-name (for a singleton variabled) or $variable-name[key-expression], where key-expression is a default syntax expression that evaluates to a text string and provides the key to select a map entry

<b>set</b>
Right hand side of the assignment. The default syntax expression is evaluated and assigned to theleft hand variable.

<b>add</b>
Right hand side of the assignment. The default syntax expression is evaluated and added to the left hand variable.

<b>sub</b>
Right hand side of the assignment. The default syntax expression is evaluated and subtracted from the left hand variable.

<b>append</b>
Right hand side of the assignment. The default syntax expression is evaluated and appended to the left hand variable.

<b>clear</b>
Clear the variable value. Deallocates a text value, and for a map, the text key.

<b>comment</b>
Comment. Can be used to preserve information about this rewrite action.



##Example

add ns assignment set_user_privilege -var $user_privilege_map[client.ip.src.typecast_text_t]   -set sys.http.callout(get_user_privilege)

##rm ns assignment

Removes a rewrite action.


##Synopsys

rm ns assignment &lt;name>


##Arguments

<b>name</b>
Name for the assignment. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the assignment is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my assignment" or ?my assignment?).



##Example

rm ns assignment set_user_privilege

##show ns assignment

Displays configured assignements.


##Synopsys

show ns assignment [&lt;name>]


##Arguments

<b>name</b>
Name of the assignment

<b>format</b>

<b>level</b>



##Outputs

<b>stateflag</b>

<b>variable</b>
Left hand side of the assignment.

<b>set</b>
Right hand side of the assignment, variable set to expression value.

<b>add</b>
Right hand side of the assignment, expression value added to variable.

<b>sub</b>
Right hand side of the assignment, expression value subtracted from variable.

<b>append</b>
Right hand side of the assignment, expression value appended to vari        able.

<b>clear</b>
Variable cleared.

<b>hits</b>
The number of times the action has been taken.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>referenceCount</b>
The number of references to the action.

<b>comment</b>
Comment. Can be used to preserve information about this rewrite action.

<b>devno</b>

<b>count</b>



##Example

show ns assignment

##rename ns assignment

Renames an assignment.


##Synopsys

rename ns assignment &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the assignment.

<b>newName</b>
New name for the assignment.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) hash (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Can be changed after the rewrite policy is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my assignment" or ?my assignment?).



##Example

rename ns assignment oldname newname

