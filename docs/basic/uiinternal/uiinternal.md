#uiinternal

The following operations can be performed on "uiinternal":


[set](#set-uiinternal) | [unset](#unset-uiinternal) | [show](#show-uiinternal)

##set uiinternal

set uiinternal data for the entities


##Synopsys

set uiinternal &lt;entityType> &lt;name> [-template &lt;string>] [-comment &lt;string>] [-rule &lt;string>]


##Arguments

<b>entityType</b>
The entitiy type of UI internal data
Possible values: LBVSERVER, GSLBVSERVER, CRVSERVER, VPNVSERVER, CSVSERVER, AUTHENTICATIONVSERVER, SERVER, SERVICE, SERVICEGROUP, GSLBSERVICE, EXPRESSION, VPNURL

<b>name</b>
The entity name

<b>template</b>
The application template associated with entity

<b>comment</b>
The application template associated with entity

<b>rule</b>
rules associated with entity



##Example

set uiinternal lbvserver v1 -template app1

##unset uiinternal

unset uiinternal for the entities.Refer to the set  uiinternal command for meanings of the arguments.


##Synopsys

unset uiinternal &lt;entityType> &lt;name> [-template] [-comment] [-rule] [-all]


##Example

unset uiinternal lbvserver v1 -template app1

##show uiinternal

display all UI internal data information for the entities


##Synopsys

show uiinternal [&lt;entityType>] [&lt;name>]


##Arguments

<b>entityType</b>
The entitiy type of UI internal data
Possible values: LBVSERVER, GSLBVSERVER, CRVSERVER, VPNVSERVER, CSVSERVER, AUTHENTICATIONVSERVER, SERVER, SERVICE, SERVICEGROUP, GSLBSERVICE, EXPRESSION, VPNURL

<b>name</b>
The entity name



##Outputs

<b>template</b>
The template associated with the entity

<b>comment</b>
The comment associated with the entity

<b>uiinfo</b>
The uiinfo associated with the entity

<b>rule</b>
The rule associated with the entity

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show uiinternal LBVSERVER v1

