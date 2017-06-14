#system session

The following operations can be performed on "system session":


[show](#show-system-session) | [kill](#kill-system-session)

##show system session

Displays information about all current system sessions, or about the specified session. The system might reclaim sessions with no active connections before expiry time.


##Synopsys

show system session [&lt;sid>]


##Arguments

<b>sid</b>
ID of the system session about which to display information.
Minimum value: 1

<b>summary</b>

<b>fullValues</b>



##Outputs

<b>userName</b>
user name of the session

<b>logintime</b>
logged-in time of this session

<b>lastactivitytime</b>
last activity time of on this session

<b>expirytime</b>
Time left in expire the session in seconds

<b>numOfconnections</b>
number of connection using this token

<b>currentconn</b>
True if the token is used for current session

<b>devno</b>

<b>count</b>

<b>stateflag</b>



##kill system session

Kills one system session, or all system sessions except the current session.


##Synopsys

kill system session (&lt;sid> | -all)


##Arguments

<b>sid</b>
ID of the system session to terminate.
CLI users: You can get the session ID by using the show system session command.
Minimum value: 1

<b>all</b>
Terminate all the system sessions except the current session.



