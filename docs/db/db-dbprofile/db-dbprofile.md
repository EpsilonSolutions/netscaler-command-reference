#db dbProfile

The following operations can be performed on "db dbProfile":


[add](#add-db-dbprofile) | [rm](#rm-db-dbprofile) | [set](#set-db-dbprofile) | [unset](#unset-db-dbprofile) | [show](#show-db-dbprofile)

##add db dbProfile

Add a new DB profile on the Netscaler


##Synopsys

add db dbProfile &lt;name> [-interpretQuery ( YES | NO )] [-stickiness ( YES | NO )] [-kcdAccount &lt;string>] [-conMultiplex ( ENABLED | DISABLED )] [-enableCachingConMuxOFF ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the database profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after the profile is created.
	    CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my profile" or 'my profile').

<b>interpretQuery</b>
If ENABLED, inspect the query and update the connection information, if required. If DISABLED, forward the query to the server.
Possible values: YES, NO
Default value: YES

<b>stickiness</b>
If the queries are related to each other, forward to the same backend server.
Possible values: YES, NO
Default value: NO

<b>kcdAccount</b>
Name of the KCD account that is used for Windows authentication.

<b>conMultiplex</b>
Use the same server-side connection for multiple client-side requests. Default is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>enableCachingConMuxOFF</b>
Enable caching when connection multiplexing is OFF.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

add dbprofile &lt;profile name&gt; -interpretQuery YES -stickyness YES -kcdaccount account

##rm db dbProfile

Remove a DB profile on the Netscaler


##Synopsys

rm db dbProfile &lt;name>


##Arguments

<b>name</b>
Name of the DB profile



##Example

rm dbprofile &lt;profile name&gt;

##set db dbProfile

Set/modify DB profile values


##Synopsys

set db dbProfile &lt;name> [-interpretQuery ( YES | NO )] [-stickiness ( YES | NO )] [-kcdAccount &lt;string>] [-conMultiplex ( ENABLED | DISABLED )] [-enableCachingConMuxOFF ( ENABLED | DISABLED )]


##Arguments

<b>name</b>
Name for the database profile. Must begin with an ASCII alphanumeric or underscore (_) character, and must contain only ASCII alphanumeric, underscore, hash (#), period (.), space, colon (:), at sign (@), equal sign (=), and hyphen (-) characters. Cannot be changed after the profile is created.
	    CLI Users: If the name includes one or more spaces, enclose the name in double or single quotation marks (for example, "my profile" or 'my profile').

<b>interpretQuery</b>
If ENABLED, inspect the query and update the connection information, if required. If DISABLED, forward the query to the server.
Possible values: YES, NO
Default value: YES

<b>stickiness</b>
If the queries are related to each other, forward to the same backend server.
Possible values: YES, NO
Default value: NO

<b>kcdAccount</b>
Name of the KCD account that is used for Windows authentication.

<b>conMultiplex</b>
Use the same server-side connection for multiple client-side requests. Default is enabled.
Possible values: ENABLED, DISABLED
Default value: ENABLED

<b>enableCachingConMuxOFF</b>
Enable caching when connection multiplexing is OFF.
Possible values: ENABLED, DISABLED
Default value: DISABLED



##Example

set dbprofile &lt;profile name&gt; -interpretQuery YES -stickyness YES

##unset db dbProfile

Unset DB profile values.Refer to the set db dbProfile command for meanings of the arguments.


##Synopsys

unset db dbProfile &lt;name> [-interpretQuery] [-stickiness] [-kcdAccount] [-conMultiplex] [-enableCachingConMuxOFF]


##show db dbProfile

Display all the configured DB profiles in the system. If a name is specified, then only that profile is shown.


##Synopsys

show db dbProfile [&lt;name>]


##Arguments

<b>name</b>
Name of the DB profile.

<b>summary</b>

<b>fullValues</b>

<b>format</b>

<b>level</b>



##Outputs

<b>interpretQuery</b>
Interpret Queries on NS

<b>stickiness</b>
Stickyness for Queries

<b>kcdAccount</b>
KCD account for windows authentication

<b>conMultiplex</b>
Enable/Disable Connection Multiplexing

<b>refCnt</b>
Profile Reference Count

<b>enableCachingConMuxOFF</b>
Enable Caching When Connection Multiplexing is OFF

<b>stateflag</b>
State flag

<b>devno</b>

<b>count</b>



##Example

show dbprofile [profile name]

