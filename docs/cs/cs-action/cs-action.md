#cs action

The following operations can be performed on "cs action":


[add](#add-cs-action) | [rm](#rm-cs-action) | [set](#set-cs-action) | [unset](#unset-cs-action) | [show](#show-cs-action) | [rename](#rename-cs-action)

##add cs action

Creates an action that indicates the target load balancing virtual server. This action is used to specify the target load balancing virtual server while defining a policy to support multiple policy bind support.


##Synopsys

add cs action &lt;name> [-targetLBVserver &lt;string> | -targetVserver &lt;string> | -targetVserverExpr &lt;expression>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the content switching action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the content switching action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my action? or ?my action?).

<b>targetLBVserver</b>
Name of the load balancing virtual server to which the content is switched.

<b>targetVserver</b>
Name of the VPN virtual server to which the content is switched.

<b>targetVserverExpr</b>
Information about this content switching action.

<b>comment</b>
Comments associated with this cs action.



##Example

 add cs action -targetLBVserver act1 lb1 

##rm cs action

Removes a content switching action.


##Synopsys

rm cs action &lt;name>


##Arguments

<b>name</b>
Name of the cs action.



##Example

rm cs action act_before

##set cs action

Modifies the configuration settings of a content switching action.


##Synopsys

set cs action &lt;name> [-targetLBVserver &lt;string> | -targetVserver &lt;string> | -targetVserverExpr &lt;expression>] [-comment &lt;string>]


##Arguments

<b>name</b>
Name for the content switching action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Can be changed after the content switching action is created.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, ?my action? or ?my action?).

<b>targetLBVserver</b>
Name of the load balancing virtual server to which the content is switched.

<b>targetVserver</b>
Name of the VPN virtual server to which the content is switched.

<b>targetVserverExpr</b>
Information about this content switching action.

<b>comment</b>
Comments associated with this cs action.



##Example

set cs action act1 -targetLBVserver lb2 -comment 'for url'

##unset cs action

Use this command to remove cs action settings.Refer to the set cs action command for meanings of the arguments.


##Synopsys

unset cs action &lt;name> -comment


##show cs action

Displays the configuration settings of the specified content switching action or lists all the content switching actions configured on the appliance.


##Synopsys

show cs action [&lt;name>]


##Arguments

<b>name</b>
Name of the content switching action.



##Outputs

<b>stateflag</b>

<b>targetLBVserver</b>
Target LB vserver name.

<b>targetVserver</b>
Target VPN vserver name.

<b>targetVserverExpr</b>
Target LB vserver expression.

<b>hits</b>
The number of times the action has been taken.

<b>referenceCount</b>
The number of references to the action.

<b>undefHits</b>
The number of times the action resulted in UNDEF.

<b>builtin</b>

<b>comment</b>
Comments associated with this cs action.

<b>devno</b>

<b>count</b>



##Example

show cs action

##rename cs action

Renames a content switching action.


##Synopsys

rename cs action &lt;name>@ &lt;newName>@


##Arguments

<b>name</b>
Existing name of the content switching action.

<b>newName</b>
New name for the content switching action. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, my name or my name).



##Example

rename cs action oldname newname

