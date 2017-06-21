#appfw confidField

The following operations can be performed on "appfw confidField":


[add](#add-appfw-confidfield) | [rm](#rm-appfw-confidfield) | [set](#set-appfw-confidfield) | [unset](#unset-appfw-confidfield) | [show](#show-appfw-confidfield)

##add appfw confidField

Defines the specified web form field as confidential.Form fields designated as confidential have the information that is provided in those fields x'd out in the audit logs.


##Synopsys

add appfw confidField &lt;fieldName> &lt;url> [-isRegex ( REGEX | NOTREGEX )] [-comment &lt;string>] [-state ( ENABLED | DISABLED )]


##Arguments

<b>fieldName</b>
Name of the form field to designate as confidential.

<b>url</b>
URL of the web page that contains the web form.

<b>isRegex</b>
Method of specifying the form field name. Available settings function as follows:
* REGEX. Form field is a regular expression.
* NOTREGEX. Form field is a literal string.
Possible values: REGEX, NOTREGEX
Default value: NOTREGEX

<b>comment</b>
Any comments to preserve information about the form field designation.

<b>state</b>
Enable or disable the confidential field designation.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##rm appfw confidField

Removes a confidential field designation.


##Synopsys

rm appfw confidField &lt;fieldName> &lt;url>


##Arguments

<b>fieldName</b>
Name of the web form field.

<b>url</b>
URL of the web page that contains the web form in which the field appears.



##set appfw confidField

Modifies the specified parameters of a confidential field setting. Form fields designated as confidential have the information that is provided in those fields x'd out in the audit logs.


##Synopsys

set appfw confidField &lt;fieldName> &lt;url> [-comment &lt;string>] [-isRegex ( REGEX | NOTREGEX )] [-state ( ENABLED | DISABLED )]


##Arguments

<b>fieldName</b>
Name of the field to modify.

<b>url</b>
URL of the web page that contains the web form.

<b>comment</b>
Any comments to preserve information about the form field designation.

<b>isRegex</b>
Method of specifying the form field name. Available settings function as follows:
* REGEX. Form field is a regular expression.
* NOTREGEX. Form field is a literal string.
Possible values: REGEX, NOTREGEX
Default value: NOTREGEX

<b>state</b>
Enable or disable the confidential field designation.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##unset appfw confidField

Use this command to remove appfw confidField settings.Refer to the set appfw confidField command for meanings of the arguments.


##Synopsys

unset appfw confidField &lt;fieldName> &lt;url> [-comment] [-isRegex] [-state]


##show appfw confidField

Displays the current settings for the specified application firewall confidential field designation.If no confidential field designation is specified, displays a list of all application firewall confidential field designations on the NetScaler appliance.


##Synopsys

show appfw confidField [&lt;fieldName>  &lt;url>]


##Arguments

<b>fieldName</b>
Name of the web form field.

<b>url</b>
URL of the web page that contains the web form with the form field.



##Outputs

<b>isRegex</b>
Method of specifying the form field name. Available settings function as follows:
* REGEX. Form field is a regular expression.
* NOTREGEX. Form field is a literal string.

<b>comment</b>
Any comments to preserve information about the form field designation.

<b>state</b>
Enable or disable the confidential field designation.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



