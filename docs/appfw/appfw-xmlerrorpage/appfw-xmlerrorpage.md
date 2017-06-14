#appfw xmlerrorpage

The following operations can be performed on "appfw xmlerrorpage":


[rm](#rm-appfw-xmlerrorpage) | [show](#show-appfw-xmlerrorpage) | [import](#import-appfw-xmlerrorpage) | [update](#update-appfw-xmlerrorpage)

##rm appfw xmlerrorpage

Removes the object imported by import xmlerrorpage.


##Synopsys

rm appfw xmlerrorpage &lt;name>


##Arguments

<b>name</b>
Indicates name of the imported xml error page to be removed.



##Example

rm xmlerrorpage &lt;name&gt;

##show appfw xmlerrorpage

Displays the specified XML error object.If no XML error page object is specified, displays a list of all XML error objects on the NetScaler appliance.


##Synopsys

show appfw xmlerrorpage [&lt;name>]


##Arguments

<b>name</b>
Name of the XML error object.



##Outputs

<b>response</b>



##Example

show appfw xmlerrorpage

##import appfw xmlerrorpage

Imports the specified XML error page to the NetScaler appliance and assigns it the specified name.


##Synopsys

import appfw xmlerrorpage &lt;src> &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
URL (protocol, host, path, and name) for the location at which to store the imported XML error object.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the XML error object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the XML error object.

<b>overwrite</b>
Overwrite any existing XML error object of the same name.



##Example

import xmlerrorpage http://www.example.com/errorpage.xml my-xml-error-page 

##update appfw xmlerrorpage

Updates the specified XML error object from the source.


##Synopsys

update appfw xmlerrorpage &lt;name>


##Arguments

<b>name</b>
Name of the XML error object.



##Example

update xmlerrorpage my-xml-error-page

