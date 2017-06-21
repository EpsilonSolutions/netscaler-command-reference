#transform profile

The following operations can be performed on "transform profile":


[add](#add-transform-profile) | [rm](#rm-transform-profile) | [set](#set-transform-profile) | [unset](#unset-transform-profile) | [show](#show-transform-profile)

##add transform profile

Creates a URL transformation profile, which contains a list of actions that define how the URLs in a request or response are to be modified. NOTE: In the URL Transformation feature (unlike all other NetScaler features), ?profile? and ?action? are not synonymous but refer to distinct entities. You must create the profile first, and then the actions.


##Synopsys

add transform profile &lt;name> [-type URL]


##Arguments

<b>name</b>
Name for the URL transformation profile. Must begin with a letter, number, or the underscore character (_), and must contain only letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at (@), equals (=), colon (:), and underscore characters. Cannot be changed after the URL transformation profile is added.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my transform profile? or ?my transform profile?).

<b>type</b>
Type of transformation. Always URL for URL Transformation profiles.
Possible values: URL



##rm transform profile

Removes a URL Transformation profile.


##Synopsys

rm transform profile &lt;name>


##Arguments

<b>name</b>
Name of the profile to remove.



##set transform profile

Modifies the settings of a URL Transformation profile.


##Synopsys

set transform profile &lt;name> [-type URL] [-onlyTransformAbsURLinBody ( ON | OFF )] [-comment &lt;string>]


##Arguments

<b>name</b>
Name of the profile to be modified.

<b>type</b>
Type of transformation. Always URL for URL Transformation profiles.
Possible values: URL

<b>onlyTransformAbsURLinBody</b>
In the HTTP body, transform only absolute URLs. Relative URLs are ignored.
Possible values: ON, OFF

<b>comment</b>
Any comments to preserve information about this URL Transformation profile.



##unset transform profile

Use this command to remove transform profile settings.Refer to the set transform profile command for meanings of the arguments.


##Synopsys

unset transform profile &lt;name> [-type] [-onlyTransformAbsURLinBody] [-comment]


##show transform profile

Displays the current settings for the specified URL Transformation profile.If no URL Transformation profile name is specified, displays a list of all URL Transformation profiles currently configured on the NetScaler appliance.


##Synopsys

show transform profile [&lt;name>]


##Arguments

<b>name</b>
Name of the profile.



##Outputs

<b>actionName</b>
URL Transformation action name.

<b>stateflag</b>

<b>type</b>
Type of transformation. Always URL for URL Transformation profiles.

<b>RegexForFindingURLinJavaScript</b>
Patclass having regexes to find the URLs in JavaScript.

<b>RegexForFindingURLinCSS</b>
Patclass having regexes to find the URLs in CSS.

<b>RegexForFindingURLinXComponent</b>
Patclass having regexes to find the URLs in X-Component.

<b>RegexForFindingURLinXML</b>
Patclass having regexes to find the URLs in XML.

<b>additionalReqHeadersList</b>
Patclass having a list of additional request header names that should transformed.

<b>additionalRespHeadersList</b>
Patclass having a list of additional response header names that should transformed.

<b>onlyTransformAbsURLinBody</b>
In the HTTP body, transform only absolute URLs. Relative URLs are ignored.

<b>comment</b>
Any comments to preserve information about this URL Transformation profile.

<b>priority</b>
Priority of the Action within the Profile.

<b>state</b>
Enabled flag.

<b>profileName</b>
URL Transformation profile name.

<b>reqUrlFrom</b>
Pattern of original request URLs. It corresponds to the way external users view the server, and acts as a source for request transformations.

<b>reqUrlInto</b>
Pattern of transformed request URLs. It corresponds to internal addresses and indicates how they are created.

<b>resUrlFrom</b>
Pattern of original response URLs. It corresponds to the way external users view the server, and acts as a source for response transformations.

<b>resUrlInto</b>
Pattern of transformed response URLs. It corresponds to internal addresses and indicates how they are created.

<b>cookieDomainFrom</b>
Pattern of the original domain in Set-Cookie headers.

<b>cookieDomainInto</b>
Pattern of the transformed domain in Set-Cookie headers.

<b>actionComment</b>
Comments.

<b>devno</b>

<b>count</b>



