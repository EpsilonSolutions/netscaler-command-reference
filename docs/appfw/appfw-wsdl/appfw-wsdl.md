#appfw wsdl

The following operations can be performed on "appfw wsdl":


[rm](#rm-appfw-wsdl) | [show](#show-appfw-wsdl) | [import](#import-appfw-wsdl)

##rm appfw wsdl

Removes the specified imported WSDL file from the application firewall.


##Synopsys

rm appfw wsdl &lt;name>


##Arguments

<b>name</b>
Name of the WSDL file to remove.



##Example

rm wsdl &lt;name&gt;

##show appfw wsdl

Removes the specified imported WSDL file.


##Synopsys

show appfw wsdl [&lt;name>]


##Arguments

<b>name</b>
Name of the WSDL file to display.



##Outputs

<b>response</b>



##Example

show appfw wsdl

##import appfw wsdl

Imports the specified WSDL file to the application firewall.


##Synopsys

import appfw wsdl &lt;src> &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
URL (protocol, host, path, and name) of the WSDL file to be imported is stored.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the WSDL on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the WSDL.

<b>overwrite</b>
Overwrite any existing WSDL of the same name.



##Example

import appfw wsdl http://www.webservicex.net/stockquote.asmx?wsdl stockquote

