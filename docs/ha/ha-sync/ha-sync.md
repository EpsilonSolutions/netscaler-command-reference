#HA sync

The following operations can be performed on "HA sync":


##force HA sync

Forces duplication of the primary node's configuration on the secondary node. Can be executed from either node.Note: This command fails under any of the following conditions:* Synchronization is already in progress.* The secondary node is disabled.* Synchronization is disabled on either node* The secondary node is not accessible from the primary.* You run the command on a standalone appliance.


##Synopsys

force HA sync [-force  [-save ( YES | NO )]]


##Arguments

<b>force</b>
Force synchronization regardless of the state of HA propagation and HA synchronization on either node.

<b>save</b>
After synchronization, automatically save the configuration in the secondary node configuration file (ns.conf) without prompting for confirmation.
Possible values: YES, NO
Default value: VAL_NOT_SET



##Example

Can be used in following formats:					&gt;force sync &lt;cr&gt;					&gt;force sync -force &lt;cr&gt;					&gt;force sync -force -save [yes|no]&lt;cr&gt;

