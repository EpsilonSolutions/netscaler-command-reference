#appfw fieldType

The following operations can be performed on "appfw fieldType":


[add](#add-appfw-fieldtype) | [rm](#rm-appfw-fieldtype) | [set](#set-appfw-fieldtype) | [show](#show-appfw-fieldtype)

##add appfw fieldType

Adds a field type to the list of field types used by the field format security check. A field type is a regular expression defining the type of data that can appear in a web form field. The Learning engine also uses the field types list to generate appropriate field type assignments for the field formats check.


##Synopsys

add appfw fieldType &lt;name> &lt;regex> &lt;priority> [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the field type.
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at \\(\\@\\), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the field type is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my field type" or 'my field type'\\).

<b>regex</b>
PCRE - format regular expression defining the characters and length allowed for this field type.

<b>priority</b>
Positive integer specifying the priority of the field type. A lower number specified a higher priority. Field types are checked in the order of their priority numbers.
Maximum value: 64000

<b>comment</b>
Comment describing the type of field that this field type is intended to match.



##rm appfw fieldType

Removes an application firewall field type.


##Synopsys

rm appfw fieldType &lt;name>


##Arguments

<b>name</b>
Name of the field type.



##set appfw fieldType

Modifies the properties of the specified application firewall field type.


##Synopsys

set appfw fieldType &lt;name> &lt;regex> &lt;priority> [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the field type.
Must begin with a letter, number, or the underscore character \\(_\\), and must contain only letters, numbers, and the hyphen \\(-\\), period \\(.\\) pound \\(\\#\\), space \\( \\), at \\(\\@\\), equals \\(=\\), colon \\(:\\), and underscore characters. Cannot be changed after the field type is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks \\(for example, "my field type" or 'my field type'\\).

<b>regex</b>
PCRE - format regular expression defining the characters and length allowed for this field type.



##show appfw fieldType

Displays the regular expression that defines the specified field type and its priority. If no field type is specified, displays all form field types currently configured on the NetScaler appliance.


##Synopsys

show appfw fieldType [&lt;name>]


##Arguments

<b>name</b>
Name of the field type.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>regex</b>
PCRE - format regular expression defining the characters and length allowed for this field type.

<b>priority</b>
Positive integer specifying the priority of the field type. A lower number specified a higher priority. Field types are checked in the order of their priority numbers.

<b>comment</b>
Comment describing the type of field that this field type is intended to match.

<b>builtin</b>
Flag to determine if fieldtype is built-in or not

<b>devno</b>

<b>count</b>

<b>stateflag</b>



