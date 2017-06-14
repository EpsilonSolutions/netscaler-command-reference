#appfw xmlschema

The following operations can be performed on "appfw xmlschema":


[rm](#rm-appfw-xmlschema) | [show](#show-appfw-xmlschema) | [import](#import-appfw-xmlschema)

##rm appfw xmlschema

Removes the specified XML Schema object from the application firewall.


##Synopsys

rm appfw xmlschema &lt;name>


##Arguments

<b>name</b>
Name of the XML Schema object to remove.



##Example

rm xmlschema &lt;name&gt;

##show appfw xmlschema

Displays the specified XML Schema object. If no object is specified, displays all XML Schema objects on the NetScaler appliance.


##Synopsys

show appfw xmlschema [&lt;name>]


##Arguments

<b>name</b>
Name of the XML Schema object to display.



##Outputs

<b>response</b>



##Example

show appfw xmlschema

##import appfw xmlschema

Imports the specified XML Schema to the NetScaler appliance and assigns it the specified name.


##Synopsys

import appfw xmlschema &lt;src> &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
URL (protocol, host, path, and file name) for the location at which to store the imported XML Schema.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the XML Schema object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the XML Schema object.

<b>overwrite</b>
Overwrite any existing XML Schema object of the same name.



##Example

import xmlschema http://schemas.xmlsoap.org/soap/envelope/ soap

