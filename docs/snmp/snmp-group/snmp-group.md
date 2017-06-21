#snmp group

The following operations can be performed on "snmp group":


[add](#add-snmp-group) | [rm](#rm-snmp-group) | [set](#set-snmp-group) | [show](#show-snmp-group)

##add snmp group

Adds an SNMPv3 user group on the NetScaler appliance. SNMPv3 groups are logical aggregations of SNMPv3 users. SNMPv3 groups are used to implement access control and define the security levels for the users. You can add a maximum of 1000 SNMPv3 groups to the NetScaler appliance.


##Synopsys

add snmp group &lt;name> &lt;securityLevel> -readViewName &lt;string>


##Arguments

<b>name</b>
Name for the SNMPv3 group. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.  You should choose a name that helps identify the SNMPv3 group. 
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose it in double or single quotation marks (for example, "my name" or 'my name').

<b>securityLevel</b>
Security level required for communication between the NetScaler appliance and the SNMPv3 users who belong to the group. Specify one of the following options:
noAuthNoPriv. Require neither authentication nor encryption.
authNoPriv. Require authentication but no encryption.
authPriv. Require authentication and encryption.
Note: If you specify authentication, you must specify an encryption algorithm when you assign an SNMPv3 user to the group. If you also specify encryption, you must assign both an authentication and an encryption algorithm for each group member.
Possible values: noAuthNoPriv, authNoPriv, authPriv

<b>readViewName</b>
Name of the configured SNMPv3 view that you want to bind to this SNMPv3 group. An SNMPv3 user bound to this group can access the subtrees that are bound to this SNMPv3 view as type INCLUDED, but cannot access the ones that are type EXCLUDED. If the NetScaler appliance has multiple SNMPv3 view entries with the same name, all such entries are associated with the SNMPv3 group.



##rm snmp group

Removes an SNMPv3 group entry from the NetScaler appliance. The appliance can have multiple SNMPv3 groups with the same name, differentiated by the securityLevel (Security level) parameter setting. Therefore, to identify an SNMPv3 group entry that you want to remove, you have to specify both the name and security level of the SNMPv3 group.


##Synopsys

rm snmp group &lt;name> &lt;securityLevel>


##Arguments

<b>name</b>
Name of the SNMPv3 group.

<b>securityLevel</b>
Security level of the SNMPv3 group.
Possible values: noAuthNoPriv, authNoPriv, authPriv



##set snmp group

Modifies the specified parameters of an SNMPv3 group entry on the NetScaler appliance.


##Synopsys

set snmp group &lt;name> &lt;securityLevel> -readViewName &lt;string>


##Arguments

<b>name</b>
The name specified in the SNMPv3 group entry that you want to modify. This parameter cannot be modified.

<b>securityLevel</b>
Security level required for communication between the NetScaler appliance and the SNMPv3 users who belong to the group. Specify one of the following options:
noAuthNoPriv. Require neither authentication nor encryption.
authNoPriv. Require authentication but no encryption.
authPriv. Require authentication and encryption.
Note: If you specify authentication, you must specify an encryption algorithm when you assign an SNMPv3 user to the group. If you also specify encryption, you must assign both an authentication and an encryption algorithm for each group member.
Possible values: noAuthNoPriv, authNoPriv, authPriv

<b>readViewName</b>
Name of the configured SNMPv3 view that you want to bind to this SNMPv3 group. An SNMPv3 user bound to this group can access the subtrees that are bound to this SNMPv3 view as type INCLUDED, but cannot access the ones that are type EXCLUDED. If the NetScaler appliance has multiple SNMPv3 view entries with the same name, all such entries are associated with the SNMPv3 group.



##show snmp group

Displays the settings of all SNMPv3 groups or of the specified SNMPv3 group. To display the settings of all SNMPv3 groups, run the command without any parameters. To display the settings of a particular SNMPv3 group, specify the name of the SNMPv3 group and securityLevel (Security level). The NetScaler appliance can have multiple SNMPv3 groups with the same name, differentiated by the securityLevel (Security level) parameter setting.


##Synopsys

show snmp group [&lt;name>  &lt;securityLevel>]


##Arguments

<b>name</b>
Name of the SNMPv3 group whose details you want the NetScaler appliance to display.

<b>securityLevel</b>
Security level of the SNMPv3 group whose details you want the NetScaler appliance to display.
Possible values: noAuthNoPriv, authNoPriv, authPriv



##Outputs

<b>readViewName</b>
Name of the configured SNMPv3 view that you want to bind to this SNMPv3 group. An SNMPv3 user bound to this group can access the subtrees that are bound to this SNMPv3 view as type INCLUDED, but cannot access the ones that are type EXCLUDED. If the NetScaler appliance has multiple SNMPv3 view entries with the same name, all such entries are associated with the SNMPv3 group.

<b>storageType</b>
The storage type for this group.

<b>status</b>
The status of this group.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



