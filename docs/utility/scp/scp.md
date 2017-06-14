#scp

The following operations can be performed on "scp":


##scp

Securely copies data from one computer to another, in SSH protocol.


##Synopsys

scp [-r] [-C] [-q] &lt;sourceString> &lt;destString>


##Arguments

<b>r</b>
Recursively copy subdirectories.

<b>C</b>
Enable compression.

<b>q</b>
Quiet output. Disable the progress meter.

<b>sourceString</b>
Source user, host, and file path, specified as &lt;user&gt;@&lt;host&gt;:&lt;path_to_copy_from&gt;. The user and host parts are optional.

<b>destString</b>
Destination user, host, and file path, specified as
&lt;user&gt;@&lt;host&gt;:&lt;path_to_copy_to&gt;. The user and host parts are optional.



##Example

scp /nsconfig/ns.conf nsroot@10.102.4.107:/nsconfig/

