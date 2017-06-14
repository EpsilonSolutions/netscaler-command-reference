#cluster

The following operations can be performed on "cluster":


##join cluster

Joins the appliance to the cluster. You must execute this command from the NetScaler IP (NSIP) address of the node that you want to add to the cluster.This command is the second part of the two-step process of adding a cluster node. The first part is adding this node to the cluster by using the add cluster node command from the cluster IP address. This operation is not permitted if any node in the cluster is in the Sync state.


##Synopsys

join cluster -clip &lt;ip_addr> {-password }


##Arguments

<b>clip</b>
Cluster IP address to which to add the node.

<b>password</b>
Password for the nsroot account of the configuration coordinator (CCO).



