#filter global

The following operations can be performed on "filter global":


[bind](#bind-filter-global) | [unbind](#unbind-filter-global) | [show](#show-filter-global)

##bind filter global

Apply (bind) the specified filtering policy globally. Note: Filtering requires the content filtering license.


##Synopsys

bind filter global (&lt;policyName>  [-priority &lt;positive_integer>]) [-state ( ENABLED | DISABLED )]


##Arguments

<b>policyName</b>
Name of the filtering policy to be bound.



##Example

To send RESET for all the HTTP requests which are not get or head type, following filter policy can be created:add filter policy reset_invalid_req -rule "METHOD != GET  && METHOD != HEAD" -reqAction RESETThis filter policy can be activated globally for NetScaler system by giving command:bind filter global reset_invalid_reqGlobally active filter policies can be seen using command:show filter global1)      Policy Name: reset_invalid_req  Priority: 0 Done

##unbind filter global

Deactivate a globally bound filter policy.


##Synopsys

unbind filter global &lt;policyName>


##Arguments

<b>policyName</b>
Name of the filter policy to be unbound.



##Example

Globally active filter policies can be seen using command:show filter global1)      Policy Name: reset_invalid_req  Priority: 0 DoneThis globally active filter policy can be deactivated on NetScaler system by giving command:unbind filter global reset_invalid_req

##show filter global

Displays the globally activated filter policies.


##Synopsys

show filter global


##Arguments

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>policyName</b>
The name of the filter policy.

<b>priority</b>
The priority of the policy.

<b>state</b>
State of the binding.

<b>stateflag</b>

<b>devno</b>

<b>count</b>



##Example

show filter global1)      Policy Name: url_filter Priority: 02)      Policy Name: reset_invalid_req  Priority: 0 Done

