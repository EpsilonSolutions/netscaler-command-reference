#transform action

The following operations can be performed on "transform action":


[add](#add-transform-action) | [rm](#rm-transform-action) | [set](#set-transform-action) | [unset](#unset-transform-action) | [show](#show-transform-action)

##add transform action

Creates a URL Transformation action, which defines how a specific element in URLs in the request or response is to be modified. NOTE: In the URL Transformation feature (unlike all other NetScaler features), ?profile? and ?action? are not synonymous but refer to distinct entities. You must create the profile first, and then the actions.


##Synopsys

add transform action &lt;name> &lt;profileName> &lt;priority> [-state ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the URL transformation action.
Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the URL Transformation action is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform action? or ?my transform action).

<b>profileName</b>
Name of the URL Transformation profile with which to associate this action.

<b>priority</b>
Positive integer specifying the priority of the action within the profile. A lower number specifies a higher priority. Must be unique within the list of actions bound to the profile. Policies are evaluated in the order of their priority numbers, and the first policy that matches is applied.
Minimum value: 1
Maximum value: 2147483647

<b>state</b>
Enable or disable this action.
Possible values: ENABLED, DISABLED
Default value: ENABLED



##rm transform action

Removes a URL Transformation action.


##Synopsys

rm transform action &lt;name>


##Arguments

<b>name</b>
Name of the action.



##set transform action

Modifies the settings of the specified URL Transformation action.


##Synopsys

set transform action &lt;name> [-priority &lt;positive_integer>] [-reqUrlFrom &lt;expression>] [-reqUrlInto &lt;expression>] [-resUrlFrom &lt;expression>] [-resUrlInto &lt;expression>] [-cookieDomainFrom &lt;expression>] [-cookieDomainInto &lt;expression>] [-state ( ENABLED | DISABLED )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the URL Transformation action to modify.

<b>priority</b>
Positive integer specifying the priority of the action within the profile. A lower number specifies a higher priority. Must be unique within the list of actions bound to the profile. Policies are evaluated in the order of their priority numbers, and the first policy that matches is applied.
Minimum value: 1
Maximum value: 2147483647

<b>reqUrlFrom</b>
PCRE-format regular expression that describes the request URL pattern to be transformed.

<b>reqUrlInto</b>
PCRE-format regular expression that describes the transformation to be performed on URLs that match the reqUrlFrom pattern.

<b>resUrlFrom</b>
PCRE-format regular expression that describes the response URL pattern to be transformed.

<b>resUrlInto</b>
PCRE-format regular expression that describes the transformation to be performed on URLs that match the resUrlFrom pattern.

<b>cookieDomainFrom</b>
Pattern that matches the domain to be transformed in Set-Cookie headers.

<b>cookieDomainInto</b>
PCRE-format regular expression that describes the transformation to be performed on cookie domains that match the cookieDomainFrom pattern. 
NOTE: The cookie domain to be transformed is extracted from the request.

<b>state</b>
Enable or disable this action.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>comment</b>
Any comments to preserve information about this URL Transformation action.



##unset transform action

Use this command to remove transform action settings.Refer to the set transform action command for meanings of the arguments.


##Synopsys

unset transform action &lt;name> [-reqUrlFrom] [-reqUrlInto] [-resUrlFrom] [-resUrlInto] [-cookieDomainFrom] [-cookieDomainInto] [-state] [-comment]


##show transform action

Displays a list of all URL Transformation actions currently assigned to the specified profile.


##Synopsys

show transform action [&lt;name>]


##Arguments

<b>name</b>
Name of the profile.



##Outputs

<b>stateflag</b>

<b>profileName</b>
Name of the URL Transformation profile with which to associate this action.

<b>priority</b>
Positive integer specifying the priority of the action within the profile. A lower number specifies a higher priority. Must be unique within the list of actions bound to the profile. Policies are evaluated in the order of their priority numbers, and the first policy that matches is applied.

<b>reqUrlFrom</b>
PCRE-format regular expression that describes the request URL pattern to be transformed.

<b>reqUrlInto</b>
PCRE-format regular expression that describes the transformation to be performed on URLs that match the reqUrlFrom pattern.

<b>resUrlFrom</b>
PCRE-format regular expression that describes the response URL pattern to be transformed.

<b>resUrlInto</b>
PCRE-format regular expression that describes the transformation to be performed on URLs that match the resUrlFrom pattern.

<b>cookieDomainFrom</b>
Pattern that matches the domain to be transformed in Set-Cookie headers.

<b>cookieDomainInto</b>
PCRE-format regular expression that describes the transformation to be performed on cookie domains that match the cookieDomainFrom pattern. 
NOTE: The cookie domain to be transformed is extracted from the request.

<b>continueMatching</b>
Continue transforming using the next rule in the list.

<b>state</b>
Enable or disable this action.

<b>comment</b>
Any comments to preserve information about this URL Transformation action.

<b>devno</b>

<b>count</b>



