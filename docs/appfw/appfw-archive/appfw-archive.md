#appfw archive

The following operations can be performed on "appfw archive":


[show](#show-appfw-archive) | [export](#export-appfw-archive) | [import](#import-appfw-archive) | [rm](#rm-appfw-archive)

##show appfw archive




##Synopsys

show appfw archive


##Outputs

<b>response</b>



##Example

show appfw archive

##export appfw archive

Exports the archive file to the specified location


##Synopsys

export appfw archive &lt;name> &lt;target>


##Arguments

<b>name</b>
Name of tar archive

<b>target</b>
Path to the file to be exported



##Related Commands

<ul><li><a href="../../../#archive-appfw-pr/#archive-appfw-pr">archive appfw profile</a></li><li><a href="../../../#restore-appfw-pr/#restore-appfw-pr">restore appfw profile</a></li></ul>



##import appfw archive

Imports the archive file from specified location


##Synopsys

import appfw archive &lt;src> &lt;name> [-comment &lt;string>]


##Arguments

<b>src</b>
Indicates the source of the tar archive file as a URL
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
Indicates name of archive

<b>comment</b>
Comments associated with this archive.



##Related Commands

<ul><li><a href="../../../#archive-appfw-pr/#archive-appfw-pr">archive appfw profile</a></li><li><a href="../../../#restore-appfw-pr/#restore-appfw-pr">restore appfw profile</a></li></ul>



##rm appfw archive

Removes the archive created by archive command.


##Synopsys

rm appfw archive &lt;name>


##Arguments

<b>name</b>
Indicates name of the archive to be removed.



##Example

rm appfw archive &lt;name&gt;

