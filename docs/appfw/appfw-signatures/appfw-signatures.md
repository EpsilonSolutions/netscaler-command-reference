#appfw signatures

The following operations can be performed on "appfw signatures":


[rm](#rm-appfw-signatures) | [show](#show-appfw-signatures) | [import](#import-appfw-signatures) | [update](#update-appfw-signatures)

##rm appfw signatures

Removes the specified signature object from the application firewall.


##Synopsys

rm appfw signatures &lt;name>


##Arguments

<b>name</b>
Name of the signature object.



##Example

rm signatures &lt;name&gt;

##show appfw signatures

Displays the specified signatures object. If no signatures object is specified, displays all signatures objects defined on the NetScaler appliance.


##Synopsys

show appfw signatures [&lt;name>]


##Arguments

<b>name</b>
Name of the signature object.



##Outputs

<b>response</b>



##Example

show appfw signatures

##import appfw signatures

Imports the specified signatures object to the NetScaler appliance and assigns it the specified name.


##Synopsys

import appfw signatures &lt;src> &lt;name> [-xslt &lt;string>] [-comment &lt;string>] [-overwrite] [-merge] [-sha1 &lt;string>]


##Arguments

<b>src</b>
URL (protocol, host, path, and file name) for the location at which to store the imported signatures object.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the signatures object on the NetScaler appliance.

<b>xslt</b>
XSLT file source.

<b>comment</b>
Any comments to preserve information about the signatures object.

<b>overwrite</b>
Overwrite any existing signatures object of the same name.

<b>merge</b>
Merges the existing Signature with new signature rules

<b>sha1</b>
File path for sha1 file to validate signature file



##Example

import signatures http://www.example.com/ns/signatures.xml my-signature

##update appfw signatures

Updates the specified signatures object from the source.


##Synopsys

update appfw signatures &lt;name> [-mergeDefault]


##Arguments

<b>name</b>
Name of the signatures object to update.

<b>mergeDefault</b>
Merges signature file with default signature file.



##Example

update signatures my-signatures

