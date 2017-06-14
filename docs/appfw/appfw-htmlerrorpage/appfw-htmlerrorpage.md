#appfw htmlerrorpage

The following operations can be performed on "appfw htmlerrorpage":


[rm](#rm-appfw-htmlerrorpage) | [show](#show-appfw-htmlerrorpage) | [import](#import-appfw-htmlerrorpage) | [update](#update-appfw-htmlerrorpage)

##rm appfw htmlerrorpage

Removes the specified XML error object.


##Synopsys

rm appfw htmlerrorpage &lt;name>


##Arguments

<b>name</b>
Name of the XML error object to remove.



##Example

rm htmlerrorpage &lt;name&gt;

##show appfw htmlerrorpage

Displays the specified HTML error object.If no HTML error object is specified, lists all HTML error objects on the NetScaler appliance.


##Synopsys

show appfw htmlerrorpage [&lt;name>]


##Arguments

<b>name</b>
Name of the HTML error object.



##Outputs

<b>response</b>



##Example

show appfw htmlerrorpage

##import appfw htmlerrorpage

Imports the specified HTML error page to the NetScaler appliance and assigns it the specified name.


##Synopsys

import appfw htmlerrorpage &lt;src> &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
URL (protocol, host, path, and name) for the location at which to store the imported HTML error object.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the HTML error object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the HTML error object.

<b>overwrite</b>
Overwrite any existing HTML error object of the same name.



##Example

import htmlerrorpage http://www.example.com/errorpage.html my-html-error-page 

##update appfw htmlerrorpage

Updates the specified HTML error object from the source.


##Synopsys

update appfw htmlerrorpage &lt;name>


##Arguments

<b>name</b>
Name of the HTML error page object to update.



##Example

update htmlerrorpage my-html-error-page

