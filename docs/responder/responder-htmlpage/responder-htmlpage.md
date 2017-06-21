#responder htmlpage

The following operations can be performed on "responder htmlpage":


[import](#import-responder-htmlpage) | [rm](#rm-responder-htmlpage) | [update](#update-responder-htmlpage) | [show](#show-responder-htmlpage)

##import responder htmlpage

Imports the specified HTML page to the NetScaler appliance, assigns it the specified name, and stores it in the list of Responder HTML page objects. This page can be used as a HTTP response body using the responder respondwithhtmlpage action type.


##Synopsys

import responder htmlpage [&lt;src>] &lt;name> [-comment &lt;string>] [-overwrite]


##Arguments

<b>src</b>
Local path to and name of, or URL \\(protocol, host, path, and file name\\) for, the file in which to store the imported HTML page.
NOTE: The import fails if the object to be imported is on an HTTPS server that requires client certificate authentication for access.

<b>name</b>
Name to assign to the HTML page object on the NetScaler appliance.

<b>comment</b>
Any comments to preserve information about the HTML page object.

<b>overwrite</b>
Overwrites the existing file



##Example

import responder htmlpage http://www.example.com/page.html my-responder-page 

##rm responder htmlpage

Removes the specified HTML page object.


##Synopsys

rm responder htmlpage &lt;name>


##Arguments

<b>name</b>
Name of the HTML page object to remove.



##Example

rm responder htmlpage &lt;name&gt;

##update responder htmlpage

Updates the specified HTML page object from the source.


##Synopsys

update responder htmlpage &lt;name>


##Arguments

<b>name</b>
Name to assign to the HTML page object on the NetScaler appliance.



##Example

update responder htmlpage my-responder-page

##show responder htmlpage

Displays the specified HTML page object. If no HTML page object is specified, lists all HTML page objects on the NetScaler appliance.


##Synopsys

show responder htmlpage [&lt;name>]


##Arguments

<b>name</b>
Name of the HTML page object to display.



##Outputs

<b>response</b>



##Example

show responder htmlpage

