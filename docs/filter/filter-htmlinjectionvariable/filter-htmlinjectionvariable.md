#filter htmlinjectionvariable

The following operations can be performed on "filter htmlinjectionvariable":


[add](#add-filter-htmlinjectionvariable) | [rm](#rm-filter-htmlinjectionvariable) | [set](#set-filter-htmlinjectionvariable) | [unset](#unset-filter-htmlinjectionvariable) | [show](#show-filter-htmlinjectionvariable)

##add filter htmlinjectionvariable

Creates an HTML injection variable. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Arguments

<b>variable</b>
Name for the HTML injection variable to be added.

<b>value</b>
Value to be assigned to the new variable.



##Example

add htmlinjectionvariable EDGESIGHT_SERVER_IP -value 1.1.1.1

##rm filter htmlinjectionvariable

Removes an HTML injection variable. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Arguments

<b>variable</b>
Name of the HTML injection variable to be removed.



##Example

rm htmlinjectionvariable EDGESIGHT_SERVER_IP

##set filter htmlinjectionvariable

Modifies the value of an HTML injection variable. NOTE: This command is deprecated.


##Synopsys




##Arguments

<b>variable</b>
Name of the HTML injection variable to be modified.

<b>value</b>
Value to be assigned to the new variable.



##Example

set htmlinjectionvariable EDGESIGHT_SERVER_IP -value 2.2.2.2

##unset filter htmlinjectionvariable

Use this command to remove filter htmlinjectionvariable settings.Refer to the set filter htmlinjectionvariable command for meanings of the arguments.NOTE: This command is deprecated.


##Synopsys




##show filter htmlinjectionvariable

Displays information about HTML injection variables. NOTE: This command is deprecated.Deprecated in favour of Client Side Measurements that can be enabled on an appflow action


##Synopsys




##Arguments

<b>variable</b>
Name of the HTML injection variable to be displayed. If a name is not provided, information about all the HTML injection variables is shown.



##Outputs

<b>value</b>
Value of the HTML injection variable

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>type</b>
Type of the HTML injection variable

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show htmlinjectionvariable EDGESIGHT_SERVER_IP

