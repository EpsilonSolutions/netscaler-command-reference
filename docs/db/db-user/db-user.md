#db user

The following operations can be performed on "db user":


[add](#add-db-user) | [rm](#rm-db-user) | [set](#set-db-user) | [show](#show-db-user)

##add db user

Adds a database user. The user name and password that you specify in this command are added to the nsconfig file and used to authenticate the user.


##Synopsys

add db user &lt;userName> {-password }


##Arguments

<b>userName</b>
Name of the database user. Must be the same as the user name specified in the database.

<b>password</b>
Password for logging on to the database. Must be the same as the password specified in the database.



##Example

add db user johndoe -password secret

##rm db user

Removes a database user from the NetScaler appliance. Requests from the user are no longer authenticated or routed to the database server.


##Synopsys

rm db user &lt;userName>


##Arguments

<b>userName</b>
Name of the database user to remove.



##set db user

Modifies the password of an existing database user.


##Synopsys

set db user &lt;userName>


##Arguments

<b>userName</b>
Name of the database user.

<b>password</b>
The database users password. If you use the CLI, you are prompted for this password after specifying the user name.



##Example

set db user johndoeThe above command sets the password for johndoe to abcd (Password to be suplied on prompt)

##show db user

Displays the specified database user or, if no user is specified, all the database users configured on the appliance.


##Synopsys

show db user [&lt;userName>] [-loggedIn]


##Arguments

<b>userName</b>
Name of the database user.

<b>loggedIn</b>
Display the names of all database users currently logged on to the NetScaler appliance.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>password</b>
Password for logging on to the database. Must be the same as the password specified in the database.

<b>devno</b>

<b>count</b>

<b>stateflag</b>



