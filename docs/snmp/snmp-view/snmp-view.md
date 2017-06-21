#snmp view

The following operations can be performed on "snmp view":


[add](#add-snmp-view) | [rm](#rm-snmp-view) | [set](#set-snmp-view) | [show](#show-snmp-view)

##add snmp view

Adds an SNMPv3 view. Used to implement access control for the SNMPv3 user, SNMPv3 views restrict user access to specific portions of the MIB. The NetScaler appliance can have multiple SNMPv3 views with the same name, differentiated by subtree parameter settings. You can add a maximum of 1000 SNMPv3 views.


##Synopsys

add snmp view &lt;name> &lt;subtree> -type ( included | excluded )


##Arguments

<b>name</b>
Name for the SNMPv3 view. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters. You should choose a name that helps identify the SNMPv3 view.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose it in double or single quotation marks (for example, "my view" or 'my view').

<b>subtree</b>
A particular branch (subtree) of the MIB tree that you want to associate with this SNMPv3 view. You must specify the subtree as an SNMP OID.

<b>type</b>
Include or exclude the subtree, specified by the subtree parameter, in or from this view. This setting can be useful when you have included a subtree, such as A, in an SNMPv3 view and you want to exclude a specific subtree of A, such as B, from the SNMPv3 view.
Possible values: included, excluded



##rm snmp view

Removes an SNMPv3 view entry from the NetScaler appliance. The appliance can have multiple SNMPv3 views with the same name, differentiated by the subtree parameter setting. Therefore, to identify an SNMPv3 group subtree that you want to remove, you have to specify both the name and subtree of the SNMPv3 view.


##Synopsys

rm snmp view &lt;name> &lt;subtree>


##Arguments

<b>name</b>
Name of the SNMPv3 view. Note: If multiple views have the same name, specify the subtree to identify the view to be removed.

<b>subtree</b>
A MIB subtree of the SNMPv3 view.



##set snmp view

Modifies the type (Type) parameter of an SNMPv3 view configured on the NetScaler appliance.


##Synopsys

set snmp view &lt;name> &lt;subtree> -type ( included | excluded )


##Arguments

<b>name</b>
The name specified in the SNMPv3 view entry. This parameter cannot be modified.

<b>subtree</b>
A MIB subtree of the SNMPv3 view entry. This parameter cannot be modified.

<b>type</b>
Include or exclude the subtree, specified by the subtree parameter, in or from this view. This setting can be useful when you have included a subtree, such as A, in an SNMPv3 view and you want to exclude a specific subtree of A, such as B, from the SNMPv3 view.
Possible values: included, excluded



##show snmp view

Displays the settings of all SNMPv3 views or of the specified SNMPv3 view. To display the settings of all the SNMPv3 views, run the command without any parameters. To display the settings of a particular SNMPv3 view, specify the name of the SNMPv3 view and subtree (the associated subtree of the MIB).  The NetScaler appliance can have multiple SNMPv3 views with the same name, differentiated by the subtree parameter settings.


##Synopsys

show snmp view [&lt;name>  [&lt;subtree>]]


##Arguments

<b>name</b>
Name of the SNMPv3 view.

<b>subtree</b>
A MIB subtree of the SNMPv3 view.



##Outputs

<b>type</b>
The type of sutree.

<b>storageType</b>
The storage type for this view.

<b>status</b>
The status of this view.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



