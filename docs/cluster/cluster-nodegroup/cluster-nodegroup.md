#cluster nodegroup

The following operations can be performed on "cluster nodegroup":


[add](#add-cluster-nodegroup) | [show](#show-cluster-nodegroup) | [set](#set-cluster-nodegroup) | [unset](#unset-cluster-nodegroup) | [bind](#bind-cluster-nodegroup) | [unbind](#unbind-cluster-nodegroup) | [rm](#rm-cluster-nodegroup)

##add cluster nodegroup

Adds a nodegroup to the cluster. A nodegroup is a set of cluster nodes to which entities can be bound. Entities that are bound to a specific nodegroup are active on all the nodes of the group and not active on the nodes that are not part of the group.


##Synopsys

add cluster nodegroup &lt;name>@ [-strict ( YES | NO )] [-sticky ( YES | NO )]


##Arguments

<b>name</b>
Name of the nodegroup. The name uniquely identifies the nodegroup on the cluster.

<b>strict</b>
Specifies whether cluster nodes, that are not part of the nodegroup, will be used as backup for the nodegroup.
  * Enabled - When one of the nodes goes down, no other cluster node is picked up to replace it. When the node comes up, it will continue being part of the nodegroup.
  * Disabled - When one of the nodes goes down, a non-nodegroup cluster node is picked up and acts as part of the nodegroup. When the original node of the nodegroup comes up, the backup node will be replaced.
Possible values: YES, NO
Default value: NO

<b>sticky</b>
Only one node can be bound to nodegroup with this option enabled. It specifies whether to prempt the traffic for the entities bound to nodegroup when owner node goes down and rejoins the cluster.
  * Enabled - When owner node goes down, backup node will become the owner node and takes the traffic for the entities bound to the nodegroup. When bound node rejoins the cluster, traffic for the entities bound to nodegroup will not be steered back to this bound node. Current owner will have the ownership till it goes down.
  * Disabled - When one of the nodes goes down, a non-nodegroup cluster node is picked up and acts as part of the nodegroup. When the original node of the nodegroup comes up, the backup node will be replaced.
Possible values: YES, NO
Default value: NO



##Example

add cluster nodegroup ng1 -strict yes

##show cluster nodegroup

Displays information about the available nodegroups.


##Synopsys

show cluster nodegroup [&lt;name>]


##Arguments

<b>name</b>
Name of the nodegroup to be displayed. If a name is not provided, information about all nodegroups is displayed.

<b>format</b>

<b>level</b>



##Outputs

<b>node</b>
Nodes in the nodegroup

<b>strict</b>
Specifies whether cluster nodes, that are not part of the nodegroup, will be used as backup for the nodegroup.
  * Enabled - When one of the nodes goes down, no other cluster node is picked up to replace it. When the node comes up, it will continue being part of the nodegroup.
  * Disabled - When one of the nodes goes down, a non-nodegroup cluster node is picked up and acts as part of the nodegroup. When the original node of the nodegroup comes up, the backup node will be replaced.

<b>sticky</b>
Only one node can be bound to nodegroup with this option enabled. It specifies whether to prempt the traffic for the entities bound to nodegroup when owner node goes down and rejoins the cluster.
  * Enabled - When owner node goes down, backup node will become the owner node and takes the traffic for the entities bound to the nodegroup. When bound node rejoins the cluster, traffic for the entities bound to nodegroup will not be steered back to this bound node. Current owner will have the ownership till it goes down.
  * Disabled - When one of the nodes goes down, a non-nodegroup cluster node is picked up and acts as part of the nodegroup. When the original node of the nodegroup comes up, the backup node will be replaced.

<b>vServer</b>
vserver that need to be bound to this nodegroup.

<b>currentNodeMask</b>
Bitmap of current nodes in this nodegroup

<b>backupNodeMask</b>
Bitmap of backup nodes in this nodegroup

<b>boundedEntitiesCntFromPE</b>
Count of bounded entities to this nodegroup accoding to PE

<b>activeList</b>
Active node list of this nodegroup

<b>backupList</b>
Backup node list of this nodegroup

<b>identifierName</b>
stream identifier  and rate limit identifier that need to be bound to this nodegroup.

<b>gslbSite</b>
vserver that need to be bound to this nodegroup.

<b>service</b>
name of the service bound to this nodegroup.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##set cluster nodegroup

Modifies the attributes of a cluster nodegroup.


##Synopsys

set cluster nodegroup &lt;name>@ [-strict ( YES | NO )]


##Arguments

<b>name</b>
Name of the nodegroup to be modified.

<b>strict</b>
Specifies whether cluster nodes, that are not part of the nodegroup, will be used as backup for the nodegroup.
  * Enabled - When one of the nodes goes down, no other cluster node is picked up to replace it. When the node comes up, it will continue being part of the nodegroup.
  * Disabled - When one of the nodes goes down, a non-nodegroup cluster node is picked up and acts as part of the nodegroup. When the original node of the nodegroup comes up, the backup node will be replaced.
Possible values: YES, NO
Default value: NO



##Example

set cluster nodegroup ng1 -strict yes

##unset cluster nodegroup

Unset nodes from the given nodegroup or unset strict option.Refer to the set cluster nodegroup command for meanings of the arguments.


##Synopsys

unset cluster nodegroup &lt;name>@ [-strict]


##Example

unset cluster nodegroup ng1 -strict

##bind cluster nodegroup

Binds a cluster node or an entity to the given nodegroup. A node can be bound to more than one nodegroup.


##Synopsys

bind cluster nodegroup &lt;name> (-node &lt;positive_integer>@ | -vServer &lt;string> | -identifierName &lt;string> | -gslbSite &lt;string> | -service &lt;string>)


##Arguments

<b>name</b>
Name of the nodegroup to which you want to bind a cluster node or an entity.

<b>node</b>
ID of the node to be bound to the nodegroup.
Default value: VAL_NOT_SET
Minimum value: 0
Maximum value: 31

<b>vServer</b>
Name of the virtual server to be bound to the nodegroup.

<b>identifierName</b>
Name of stream or limit identifier to be bound to the nodegroup.

<b>gslbSite</b>
Name of the GSLB site to be unbound from the nodegroup.

<b>service</b>
Name of the service to be unbound from the nodegroup.



##Example

bind cluster nodegroup ng1 -vserver v1

##unbind cluster nodegroup

Unbinds a cluster node or an entity from a given nodegroup.


##Synopsys

unbind cluster nodegroup &lt;name> (-node &lt;positive_integer>@ | -vServer &lt;string> | -identifierName &lt;string> | -gslbSite &lt;string> | -service &lt;string>)


##Arguments

<b>name</b>
Name of the nodegroup from which you want to unbind a cluster node or an entity.

<b>node</b>
ID of the node to be unbound from the nodegroup.
Default value: VAL_NOT_SET
Minimum value: 0
Maximum value: 31

<b>vServer</b>
Name of the virtual server to be unbound from the nodegroup.

<b>identifierName</b>
Name of stream or limit identifier to be unbound from the nodegroup.

<b>gslbSite</b>
Name of the GSLB site to be unbound from the nodegroup.

<b>service</b>
Name of the service to be unbound from the nodegroup.



##Example

unbind cluster nodegroup ng1 -vserver v1

##rm cluster nodegroup

Removes a nodegroup from the cluster.


##Synopsys

rm cluster nodegroup &lt;name>@


##Arguments

<b>name</b>
Name of the nodegroup to be removed.



##Example

rm cluster nodegroup ng1

