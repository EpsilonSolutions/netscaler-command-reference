#snmp community

The following operations can be performed on "snmp community":


[add](#add-snmp-community) | [rm](#rm-snmp-community) | [show](#show-snmp-community)

##add snmp community

Creates an SNMP community, which is a password (string) used to authenticate SNMP queries from SNMP managers. You can associate it with any of the following SNMP query types: GET, GET NEXT, ALL, GET BULK.You can associate one or more community strings with each query type. For example, if you associate two community strings, such as Example and Test, with the query type GET NEXT, the NetScaler appliance considers only those GET NEXT SNMP query packets that contain Example or Test as the community string.


##Synopsys

add snmp community &lt;communityName> &lt;permissions>


##Arguments

<b>communityName</b>
The SNMP community string. Can consist of 1 to 31 characters that include uppercase and lowercase letters,numbers and special characters.
The following requirement applies only to the NetScaler CLI:
If the string includes one or more spaces, enclose the name in double or single quotation marks (for example, "my string" or 'my string').

<b>permissions</b>
The SNMP V1 or V2 query-type privilege that you want to associate with this SNMP community.
Possible values: GET, GET_NEXT, GET_BULK, SET, ALL



##Example

add snmp community public ALLadd snmp community a#12ab GET_BULK

##rm snmp community

Removes an SNMP community from the NetScaler appliance. After you remove the SNMP community, the appliance does not respond to any SNMP queries that contain that community string.


##Synopsys

rm snmp community &lt;communityName>


##Arguments

<b>communityName</b>
The name of the SNMP community.



##Example

rm snmp community public

##show snmp community

Displays the SNMP v1 or v2 query-type privileges (such as GET, GET NEXT, ALL, or GET BULK) that have been set for all SNMP communities or for the specified SNMP community. To display the settings of all the SNMP communities, run the command without any parameters. To display the settings of a particular SNMP community, specify the name of the SNMP community.


##Synopsys

show snmp community [&lt;communityName>]


##Arguments

<b>communityName</b>
The name of the SNMP community whose SNMP v1 or v2 query type privilege setting, such as GET, GET NEXT, ALL, or GET BULK, you want the NetScaler appliance to display.



##Outputs

<b>permissions</b>
The SNMP V1 or V2 query-type privilege that you want to associate with this SNMP community.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##Example

show snmp community

