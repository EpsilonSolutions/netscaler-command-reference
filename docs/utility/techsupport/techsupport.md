#techsupport

The following operations can be performed on "techsupport":


##show techsupport

Generates a tar of system configuration data and statistics. This file must be submitted to Citrix technical support with file name collector_&lt;NS IP>_&lt;P/S>_&lt;DateTime>.tgz. The archive is always pointed by the symbolic link /var/tmp/support/support.tgz for each invocation of the command.


##Synopsys

show techsupport [-scope ( NODE | CLUSTER )]


##Arguments

<b>scope</b>
Use this option to run showtechsupport on present node or all cluster nodes
Possible values: NODE, CLUSTER
Default value: NS_TECH_NODE



##Outputs

<b>response</b>
response as a text blob

<b>serverName</b>



##Example

show techsupport

