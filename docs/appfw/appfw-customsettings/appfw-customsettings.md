#appfw customSettings

The following operations can be performed on "appfw customSettings":


[export](#export-appfw-customsettings) | [rm](#rm-appfw-customsettings) | [show](#show-appfw-customsettings) | [import](#import-appfw-customsettings) | [update](#update-appfw-customsettings)

##export appfw customSettings

 NOTE: This command is deprecated.Changed CLI commands for Appfw "customSettings" to "signatures"


##Synopsys




##Arguments

<b>name</b>

<b>target</b>



##rm appfw customSettings

Removes the object imported by import customsettings. NOTE: This command is deprecated.Changed CLI commands for Appfw "customSettings" to "signatures"


##Synopsys




##Arguments

<b>name</b>
Indicates name of custom-settings object.



##Example

rm customsettings &lt;name&gt;

##show appfw customSettings

Displays the object imported by import customsettings. NOTE: This command is deprecated.Changed CLI commands for Appfw "customSettings" to "signatures"


##Synopsys




##Arguments

<b>name</b>



##Outputs

<b>response</b>



##Example

show appfw customsettings

##import appfw customSettings

Downloads the Application Firewall Custom Settings XML configuration to the NetScaler Box with the given object name NOTE: This command is deprecated.Changed CLI commands for Appfw "customSettings" to "signatures"


##Synopsys




##Arguments

<b>src</b>
Indicates the source of the custom settings file as a URL
of the form
    &lt;protocol&gt;://&lt;host&gt;[:&lt;port&gt;][/&lt;path&gt;]
&lt;protocol&gt; is http or https.
&lt;host&gt; is the DNS name or IP address of the http or https server.
&lt;port&gt; is the port number of the server. If omitted, the
default port for http or https will be used.
&lt;path&gt; is the path of the file on the server.
Import will fail if an https server requires client
certificate authentication.

<b>name</b>
Indicates name of custom-settings object.

<b>comment</b>
Comments.

<b>overwrite</b>
Overwrites the existing file

<b>xslt</b>
XSLT file URL.

<b>merge</b>
Merges the existing Signature with new signature rules

<b>sha1</b>
File path for sha1 file to validate signature file



##Example

import customsettings http://www.example.com/ns/customsettings.xml my-settings

##update appfw customSettings

Updates the Application Firewall Custom Settings XML configuration to the NetScaler Box with the given object name NOTE: This command is deprecated.Changed CLI commands for Appfw "customSettings" to "signatures"


##Synopsys




##Arguments

<b>name</b>
Indicates name of the custom-settings object to update.

<b>mergeDefault</b>
Merges signature file with default signature file.



##Example

update customsettings my-settings

