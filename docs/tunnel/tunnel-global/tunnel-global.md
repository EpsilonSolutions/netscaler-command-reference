#tunnel global

The following operations can be performed on "tunnel global":


[bind](#bind-tunnel-global) | [unbind](#unbind-tunnel-global) | [show](#show-tunnel-global)

##bind tunnel global

Activates an existing tunnel traffic policy globally.


##Synopsys

bind tunnel global (&lt;policyName>  [-priority &lt;positive_integer>]) [-state ( ENABLED | DISABLED )]


##Arguments

<b>policyName</b>
Name of the tunnel traffic policy to activate or bind.



##Example

add tunnel trafficpolicy cmp_all_destport "REQ.TCP.DESTPORT == 0-65535" GZIPAfter creating above tunnel policy, it can be activated by binding it globally:bind tunnel global cmp_all_destportAfter binding cmp_all_destport compression policy globally, the policy gets activated and the NetScaler will compress all TCP traffic accessed through ssl-vpn tunnel.Globally active tunnel policies can be seen using command:&gt; show tunnel global   1 Globally Active Tunnel Policies:1) Policy Name: cmp_all_destport    Priority: 0 Done

##unbind tunnel global

Deactivates an active tunnel traffic policy.


##Synopsys

unbind tunnel global &lt;policyName>


##Arguments

<b>policyName</b>
Name of the tunnel traffic policy to unbind or deactivate.



##Example

Globally active tunnel policies can be seen using command:&gt; show tunnel global  1 Globally Active Tunnel Policies:1) Policy Name: cmp_all_destport    Priority: 0 DoneThe globally active tunnel traffic policy can be deactivated on the NetScaler system by issuing the command:unbind tunnel global cmp_all_destport

##show tunnel global

Displays globally active tunnel policies.


##Synopsys

show tunnel global


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>policyName</b>
Policy name.

<b>priority</b>
Priority.

<b>state</b>
Current state of the binding. If the binding is enabled, the policy is active.

<b>builtin</b>
Indicates that a variable is a built-in (SYSTEM INTERNAL) type.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

&gt; sh tunnel global1) Policy Name: cmp_all_destport   Priority: 02) Policy Name: local_sub_nocmp    Priority: 500 Done

