#snmp user

The following operations can be performed on "snmp user":


[add](#add-snmp-user) | [rm](#rm-snmp-user) | [set](#set-snmp-user) | [unset](#unset-snmp-user) | [show](#show-snmp-user)

##add snmp user

Adds an SNMPv3 user who can send SNMP queries to the NetScaler appliance. You can add a maximum of 1000 SNMPv3 users.


##Synopsys

add snmp user &lt;name> -group &lt;string> [-authType ( MD5 | SHA )  {-authPasswd }  [-privType ( DES | AES )  {-privPasswd }]]


##Arguments

<b>name</b>
Name for the SNMPv3 user. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the name includes one or more spaces, enclose it in double or single quotation marks (for example, "my user" or 'my user').

<b>group</b>
Name of the configured SNMPv3 group to which to bind this SNMPv3 user. The access rights (bound SNMPv3 views) and security level set for this group are assigned to this user.

<b>authType</b>
Authentication algorithm used by the NetScaler appliance and the SNMPv3 user for authenticating the communication between them. You must specify the same authentication algorithm when you configure the SNMPv3 user in the SNMP manager.
Possible values: MD5, SHA

<b>authPasswd</b>
Plain-text pass phrase to be used by the authentication algorithm specified by the authType (Authentication Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the pass phrase includes one or more spaces, enclose it in double or single quotation marks (for example, "my phrase" or 'my phrase').

<b>privType</b>
Encryption algorithm used by the NetScaler appliance and the SNMPv3 user for encrypting the communication between them. You must specify the same encryption algorithm when you configure the SNMPv3 user in the SNMP manager.
Possible values: DES, AES

<b>privPasswd</b>
Encryption key to be used by the encryption algorithm specified by the privType (Encryption Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the key includes one or more spaces, enclose it in double or single quotation marks (for example, "my key" or 'my key').



##rm snmp user

Removes an SNMPv3 user entry from the NetScaler appliance.


##Synopsys

rm snmp user &lt;name>


##Arguments

<b>name</b>
Name of the SNMPv3 user.



##set snmp user

Modifies the specified parameters of an SNMPv3 user entry on the NetScaler appliance.


##Synopsys

set snmp user &lt;name> [-group &lt;string>] [-authType ( MD5 | SHA )  {-authPasswd }] [-privType ( DES | AES )  {-privPasswd }]


##Arguments

<b>name</b>
Name specified in the SNMPv3 user entry that you want to modify. Because this parameter is used for identifying the SNMPv3 user entry, it cannot be modified after the entry has been created.

<b>group</b>
Name of the configured SNMPv3 group to which to bind this SNMPv3 user. The access rights (bound SNMPv3 views) and security level set for this group are assigned to this user.

<b>authType</b>
Authentication algorithm used by the NetScaler appliance and the SNMPv3 user for authenticating the communication between them. You must specify the same authentication algorithm when you configure the SNMPv3 user in the SNMP manager.
Possible values: MD5, SHA

<b>authPasswd</b>
Plain-text pass phrase to be used by the authentication algorithm specified by the authType (Authentication Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the pass phrase includes one or more spaces, enclose it in double or single quotation marks (for example, "my phrase" or 'my phrase').

<b>privType</b>
Encryption algorithm used by the NetScaler appliance and the SNMPv3 user for encrypting the communication between them. You must specify the same encryption algorithm when you configure the SNMPv3 user in the SNMP manager.
Possible values: DES, AES

<b>privPasswd</b>
Encryption key to be used by the encryption algorithm specified by the privType (Encryption Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the key includes one or more spaces, enclose it in double or single quotation marks (for example, "my key" or 'my key').



##unset snmp user

Resets the specified parameters of an SNMPv3 user entry to their default settings..Refer to the set snmp user command for meanings of the arguments.


##Synopsys

unset snmp user &lt;name> (-authType | -privType) [-authPasswd] [-privPasswd]


##show snmp user

Displays the settings of all SNMPv3 users or of the specified SNMPv3 user. To display the settings of all the SNMPv3 users, run the command without any parameters. To display the settings of a particular SNMPv3 user, specify the name of the SNMPv3 user.


##Synopsys

show snmp user [&lt;name>]


##Arguments

<b>name</b>
Name of the SNMPv3 user whose details you want the NetScaler appliance to display.



##Outputs

<b>group</b>
Name of the configured SNMPv3 group to which to bind this SNMPv3 user. The access rights (bound SNMPv3 views) and security level set for this group are assigned to this user.

<b>authType</b>
Authentication algorithm used by the NetScaler appliance and the SNMPv3 user for authenticating the communication between them. You must specify the same authentication algorithm when you configure the SNMPv3 user in the SNMP manager.

<b>authPasswd</b>
Plain-text pass phrase to be used by the authentication algorithm specified by the authType (Authentication Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the pass phrase includes one or more spaces, enclose it in double or single quotation marks (for example, "my phrase" or 'my phrase').

<b>privType</b>
Encryption algorithm used by the NetScaler appliance and the SNMPv3 user for encrypting the communication between them. You must specify the same encryption algorithm when you configure the SNMPv3 user in the SNMP manager.

<b>privPasswd</b>
Encryption key to be used by the encryption algorithm specified by the privType (Encryption Type) parameter. Can consist of 1 to 31 characters that include uppercase and lowercase letters, numbers, and the hyphen (-), period (.) pound (#), space ( ), at sign (@), equals (=), colon (:), and underscore (_) characters.
The following requirement applies only to the NetScaler CLI:
If the key includes one or more spaces, enclose it in double or single quotation marks (for example, "my key" or 'my key').

<b>engineID</b>
The context engine ID of the user.

<b>storageType</b>
The storage type for this user.

<b>status</b>
The status of this user.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



