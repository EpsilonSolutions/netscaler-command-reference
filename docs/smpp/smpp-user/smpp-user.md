#smpp user

The following operations can be performed on "smpp user":


[add](#add-smpp-user) | [rm](#rm-smpp-user) | [set](#set-smpp-user) | [show](#show-smpp-user)

##add smpp user

Adds an SMPP user. The user name and password that you specify in this command are added to the configuration file and used to authenticate the user.


##Synopsys

add smpp user &lt;userName> {-password }


##Arguments

<b>userName</b>
Name of the SMPP user. Must be the same as the user name specified in the SMPP server.

<b>password</b>
Password for binding to the SMPP server. Must be the same as the password specified in the SMPP server.



##Example

add smpp user johndoe -password secret

##rm smpp user

Removes an SMPP user from the NetScaler appliance.


##Synopsys

rm smpp user &lt;userName>


##Arguments

<b>userName</b>
Name of the SMPP user to remove.



##set smpp user

Modifies the password of an existing SMPP user.


##Synopsys

set smpp user &lt;userName> {-password }


##Arguments

<b>userName</b>
Name of the SMPP user.

<b>password</b>
The SMPP users password.



##Example

set smpp user johndoe supersecret

##show smpp user

Displays the specified SMPP user or, if no user is specified, all the SMPP users configured on the appliance.


##Synopsys

show smpp user [&lt;userName>]


##Arguments

<b>userName</b>
Name of the SMPP user.



##Outputs

<b>password</b>
Password for binding to the SMPP server. Must be the same as the password specified in the SMPP server.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



